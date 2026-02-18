---
title: "Service Sync Flow"
description: "When and how QSOs sync to cloud services"
weight: 6
showToc: true
---

Carrier Wave syncs {{< term "QSO" >}} data bidirectionally with multiple cloud services, each with its own capabilities and timing characteristics.

## Sync Timing

Sync runs automatically in several scenarios:

- **After saving a QSO**: Near real-time upload to configured services
- **App foreground**: Checks for new data when returning to the app
- **Network restored**: Resumes sync when connectivity returns
- **Pull to refresh**: Manual trigger from Dashboard or QSO list

Sync operations batch multiple QSOs for efficiency and respect service-specific rate limits with adaptive backoff. Activity detection triggers automatically on both live logging and sync downloads, creating activity items for new operations.

## Sync Direction by Service

| Service | Upload | Download |
|---------|--------|----------|
| QRZ.com | ✓ QSOs | ✓ QSOs, Callsign info |
| POTA | ✓ Activations | ✗ |
| Ham2K LoFi | ✓ QSOs | ✓ QSOs |
| LoTW | ✗ | ✓ Confirmations |
| Club Log | ✓ QSOs | ✓ QSOs |
| HAMRS | ✗ | ✓ QSOs |

## Service-Specific Behavior

### QRZ.com

- **Format**: ADIF upload via API
- **Timing**: Near real-time after QSO save
- **Duplicate handling**: Server-side deduplication
- **Partial results**: Handles PARTIAL status with detailed response logging for debugging
- **Callsign lookups**: Fetches callsign details and caches locally

### POTA

- **Format**: ADIF files, one per park per UTC date
- **Upload timing**: After activation completion
- **Two-fer support**: QSOs automatically split to each park when activating multiple parks simultaneously
- **Upload status tracking**: Per-park progression through pending → submitted → accepted states
- **Job reconciliation**: Automatically reconciles uploads against POTA job log during sync
- **Orphan repair**: Resets submitted QSOs back to pending if POTA has dropped the upload
- **QSO-level gap repair**: Compares local vs POTA remote data and flags missing QSOs for re-upload
- **Maintenance window**: Skips uploads during POTA maintenance (2330-0400 UTC), shows countdown on Dashboard
- **Invalid references**: Marks QSOs with invalid park references (e.g., bare "US") as rejected to prevent infinite retry loops

### Ham2K LoFi

- **Format**: JSON via REST API
- **Direction**: Bidirectional, near real-time
- **Conflict resolution**: Latest timestamp wins
- **Initial sync**: Downloads entire QSO history on first connection
- **Adaptive pagination**: Adjusts batch size based on network conditions with resumable downloads surviving app restarts
- **Adaptive concurrency**: Uses 2-8 concurrent requests with automatic backoff on errors

### LoTW

- **Direction**: Download confirmations only
- **Callsigns**: Fetches for all configured callsigns (current + previous)
- **Rate limiting**: Adaptive date windowing automatically shrinks time windows on rate limit responses
- **Request spacing**: 3-second delay between requests to respect service limits

### Club Log

- **Format**: ADIF bidirectional sync
- **Authentication**: Email + app password + API key
- **Upload**: Batch upload via putlogs.php endpoint
- **Download**: Incremental date-based download via getadif.php endpoint
- **Real-time upload**: Supports single-QSO immediate upload
- **Query language**: Filter QSOs from Club Log using `source:clublog`

### HAMRS

- **Format**: JSON via REST API
- **Direction**: Download only (does not support uploads despite historical configuration options)

## Sync Reports

Each service generates structured sync reports showing:

- **Visual funnel**: Fetched → Validated → Changes Applied → Uploaded
- **Status badges**: Success, warning, error indicators
- **Phase indicators**: Current sync operation stage
- **Reconciliation details**: POTA job matching and gap repair results
- **Warnings**: Issues requiring attention

Reports persist across app launches via UserDefaults and are populated by both normal sync operations and force re-download actions.

## Callsign Filtering

Only QSOs matching your primary {{< term "callsign" >}} are uploaded to services:

- Import creates upload markers only for primary callsign QSOs
- Sync fetch applies defense-in-depth filtering during download
- Previous callsigns are excluded from upload queues
- Prevents pollution of contest logs and online records with guest operator QSOs

## Metadata Mode Filtering

{{< term "mode" >}} values `WEATHER`, `SOLAR`, and `NOTE` represent {{< term "POTA" >}} activation metadata and are **never synced or uploaded**:

- Filtered at source during import and logging
- Excluded from sync counts and statistics
- Existing metadata QSOs with pending flags are auto-repaired during sync

## Offline Operation

Carrier Wave works fully offline:

- QSOs save locally with pending sync status
- Sync queues accumulate offline changes
- Sync resumes automatically when network connectivity returns
- No data loss during offline periods

## Force Re-download

Available per service on service detail sheets (tap service card on Dashboard):

- Downloads and reprocesses all QSOs from the selected service
- Rebuilds local state from authoritative remote data
- Useful for recovering from sync inconsistencies
- No debug mode required

## Data Repair Steps

### Run During Sync

- **Callsign whitespace repair**: Normalizes callsign spacing
- **QRZ isSubmitted state repair**: Corrects sync status flags
- **Orphan repair**: Fixes dangling service presence records
- **POTA presence repair**: Rebuilds park activation tracking

### One-Time Repairs

- **WPM backfill**: Populates missing {{< term "WPM" >}} values
- **Conditions backfill**: Fills missing band conditions
- **Park ref extraction**: Extracts park references from comments
- **K-index repair**: Corrects geomagnetic index values
- **PHONE/SSB merge**: Consolidates legacy mode naming
- **Activity log QSO flagging**: Links QSOs to activity items

## Retry Logic

- **Transient errors**: Automatic retry with exponential backoff
- **Auth errors**: Prompt for re-authentication (POTA auto-re-authenticates with stored credentials)
- **Permanent errors**: Mark as failed and log for investigation
- **Rate limit errors**: Adaptive backoff with gradually increasing delays

## Conflict Resolution

Different services use different strategies:

- **LoFi**: Most recent modification timestamp wins
- **QRZ**: Remote data is authoritative for downloads
- **POTA**: Upload-only, no conflicts possible
- **Club Log**: Incremental date-based sync, server authoritative for downloads

## Sync Status Indicators

Service cards on the Dashboard show:

- **✓ Green**: All synced
- **↻ Yellow**: Sync in progress
- **! Red**: Sync error
- **○ Gray**: Service not configured
- **n Pending**: Count of QSOs awaiting upload

## Monitoring Sync

Enable detailed sync logging at **Settings → Advanced → Sync Debugging**:

- Request and response logs with full payloads
- Error details with stack traces
- Performance timing data
- Share sync debug log as text for troubleshooting
- **Action Required** log level (purple) highlights issues needing user intervention

## See Also

- [Settings & Services](/reference/settings/)
- [Troubleshooting](/reference/troubleshooting/)
- [iCloud Sync](/reference/icloud/)
- [Dashboard & Statistics](/reference/dashboard/)
