---
title: "Settings & Services"
description: "Configuration, service authentication, and preferences"
weight: 7
showToc: true
---

All application settings are accessed through the Settings tab or the gear icon in the navigation bar.

## Profile (About Me)

Your operator profile is used to populate {{< term "QSO" >}} fields and identify you in service uploads.

### Callsign

Your primary operating callsign. This field is auto-populated from QRZ on first successful connection.

### Callsign Aliases

Add current and previous callsigns. Carrier Wave automatically detects when your log data contains multiple callsigns and offers to add them as aliases. All configured callsigns are used when downloading confirmations from LoTW.

### Name, QTH, Grid Square

Your name, location (QTH), and {{< term "Grid Square" >}}. With location permission enabled, grid square is auto-populated from GPS.

### License Class

Select Technician, General, or Extra. Tap the search icon to look up your license class from HamDB.org.

### Portable Callsign Prefix/Suffix

Configure prefix or suffix for portable operations (e.g., `/P`, `/M`). This is appended to your callsign when logging portable {{< term "QSO" >}}s.

## Services

Carrier Wave integrates with multiple amateur radio services for callsign lookups, {{< term "QSO" >}} sync, and activation uploads.

### QRZ.com

**Authentication:** Username and password. Username is automatically uppercased since QRZ usernames are callsigns.

**Features:**
- Callsign lookups (name, QTH, grid square, license class)
- {{< term "QSO" >}} upload and download
- Bidirectional sync with QRZ Logbook

**Requirements:** QRZ XML Logbook Data subscription is required for callsign lookups.

### POTA

**Authentication:** OAuth via in-app web view. Carrier Wave stores credentials and performs headless re-authentication when tokens expire.

**Features:**
- Activation upload
- Park reference lookup
- Upload history and job status tracking

**Behavior:** Uploads are submitted as background jobs. Check job status in Settings > Developer > POTA Jobs.

### Ham2K LoFi

**Authentication:** Email-based device linking. Enter your email address, check your inbox, and tap the confirmation link.

**Features:**
- Bidirectional {{< term "QSO" >}} sync
- Cross-device synchronization
- Adaptive pagination with resumable downloads

**Behavior:** Ham2K LoFi sync is designed for efficient multi-device operation. Downloads resume automatically if interrupted.

### Logbook of The World (LoTW)

**Authentication:** Username and password.

**Features:**
- Download {{< term "QSO" >}} confirmations
- Fetches confirmations for all configured callsigns (current and aliases)

**Behavior:** Carrier Wave uses adaptive date windowing to respect LoTW rate limits. **Upload** is not supported; use TQSL for uploads.

### Club Log

**Status:** Coming soon. Club Log sync is not yet active — credentials can be configured but uploads and downloads are disabled until full integration is complete.

**Authentication:** Email, app password, callsign, and API key.

**Features (planned):**
- Bidirectional ADIF sync
- Batch upload
- Incremental date-based download
- Real-time single-{{< term "QSO" >}} upload

### eQSL

**Authentication:** Username and password.

**Features:**
- {{< term "QSO" >}} upload to eQSL
- Confirmation download
- Bidirectional sync with eQSL inbox

**Behavior:** eQSL confirmations appear as a separate confirmation source in QSO detail views. Confirmed contacts show an eQSL badge alongside LoTW and QRZ confirmations.

### HAMRS

**Authentication:** OAuth.

**Features:**
- Bidirectional {{< term "QSO" >}} sync

## Radio Control

Configure radio control for frequency and mode sync between your radio and Carrier Wave via BLE or WiFi.

### Transport Selection

Choose **BLE** (Bluetooth Low Energy) or **WiFi** as the connection transport.

- **BLE** — Works with all supported protocols via built-in Bluetooth or BLE-to-serial adapters
- **WiFi** — Connect to Icom radios with built-in WiFi (IC-705, etc.) via Access Point or Station mode

### Device Scanning (BLE)

Tap **Scan for Radios** to discover nearby BLE-enabled radios and interfaces. Carrier Wave displays:

- **Device name** and signal strength
- **Connection status** (available, paired, connected)
- **Protocol type** detected (if auto-detectable)

### WiFi Configuration

For WiFi transport:

1. Join your radio's WiFi network (AP mode) or ensure both devices are on the same network (Station mode)
2. Enter the radio's IP address
3. Select the protocol (Icom CI-V)

### Protocol Selection

Select the communication protocol matching your radio:

| Protocol | Radios | Transports |
|----------|--------|------------|
| **Icom CI-V** | Icom IC-705, IC-7300, IC-7610, and other CI-V radios | BLE, WiFi |
| **Kenwood/Elecraft** | Kenwood TS-890S, Elecraft KX2/KX3/K4 (text command protocol) | BLE |
| **Yaesu CAT** | Yaesu FT-891, FT-991A, FTDX10 (CAT command set) | BLE |

### CI-V Address Configuration

For Icom radios, configure the CI-V address (default `0x94` for IC-705). Enter the hex address matching your radio's CI-V setting.

See [Radio Control](/reference/radio-control/) for full details.

## iCloud Sync

Toggle iCloud synchronization to sync data across all your Apple devices.

**What syncs:**
- {{< term "QSO" >}} database
- App settings
- WebSDR favorites

**What doesn't sync:**
- Service credentials (stored in Keychain, per-device)

## Callsign Notes

Configure custom Polo-style notes files for displaying emojis or tags next to callsigns.

**Configuration:**
- Add sources by URL and title
- Enable/disable individual sources
- View entry count and last fetch status

**Behavior:**
- Sources are fetched and cached daily
- All matching emojis from enabled sources are combined and displayed
- Display mode: **Emoji mode** (show emojis) or **Source Names mode** (show source names)

## Logger Settings

Configure behavior and appearance of the {{< term "Logger" >}}.

### Always-Visible Fields

Toggle which fields are always visible in the logger: Notes, Grid, Park, Operator.

### Keep Screen On

Prevent the device from sleeping during logging sessions.

### Auto-Switch Mode for Frequency

Automatically suggest operating mode based on entered frequency.

### Keyboard Number Row Customization

Configure which symbols appear in the number row of the custom keyboard. Drag to reorder, toggle individual keys on or off.

### Command Row Buttons

Customize quick-access command buttons in the logger. Add, remove, and reorder buttons for your most-used commands.

### Auto-Upload Settings

Configure automatic upload behavior after ending sessions:

- **Upload immediately** - Upload to all configured services right after session end
- **Prompt first** - Show the upload sheet for review before uploading
- **Manual only** - Never auto-upload; require explicit action

## POTA Settings

Configure behavior specific to {{< term "POTA" >}} activations.

### Auto-Spotting Interval

Set the interval for automatic spot updates (e.g., every 15 minutes).

### QRT Spotting

Automatically post a "QRT" spot when ending an activation.

### Professional Statistician Mode

Enable detailed statistics tracking for activations.

### Equipment on Brag Sheet

Include equipment details when generating activation brag sheets.

### Hourly Solar Conditions Polling

Enable background polling for solar conditions ({{< term "SFI" >}}, {{< term "A-index" >}}, {{< term "K-index" >}}) every hour.

## Smart Spot Needs Configuration

Configure need categories for the [Smart Spot Needs](/reference/smart-needs/) system:

- **Enable/disable individual need categories** (DXCC, WAS, POTA, WWFF, Custom)
- **Custom patterns** - Define your own matching rules
- **Notification cooldown** - Set minimum time between alerts for the same need (default: 30 minutes)
- **HamAlert export** - Generate a HamAlert trigger list from your needs configuration

See [Smart Spot Needs](/reference/smart-needs/) for full details.

## Activity Log Settings

Configure the Activity Log feature for monitoring stations and spots.

### Station Profiles

Manage saved station profiles (radio, antenna, power configurations).

### Upload Service Info

Include station profile information in service uploads.

### Daily Goal

Set a daily {{< term "QSO" >}} goal for motivation tracking.

### Spot Age Filter

Filter spots by age: 5-30 minutes.

### Proximity Filter Radius

Filter spots by distance from your location: 100-2000 miles.

### Sort Order

Sort spots by **Recent** (newest first) or **Frequency** (band order).

## Navigation

Customize the app's navigation bar and default behavior.

### Tab Bar Configuration

Show, hide, or reorder tabs. Available tabs:
- Dashboard
- Logger
- Logs
- CW
- FT8
- Map
- Activity
- Activity Log

Hidden tabs remain accessible via the "More" menu. Drag handles allow reordering tabs to match your workflow.

### Default Tab

Select which tab appears when launching the app.

### iPad Sidebar

On iPad, all tabs are shown in the sidebar. Visibility changes are applied immediately. Settings has a dedicated entry in the sidebar.

## Appearance

### Theme

Select **System** (follows device), **Light**, **Dark**, or **Sunlight** mode.

**Sunlight mode** forces light theme with boosted contrast for outdoor visibility in bright conditions.

### Hunt Filter

Configure persistent filters for the HUNT spot command. All selections are saved and applied automatically when opening the HUNT panel:

- **Activity** - Filter by program (POTA, SOTA, or All)
- **Band** - Multi-select band filter
- **Mode** - Multi-select mode filter
- **Club** - Select one or more clubs to show only their members' spots
- **Friends** - Toggle to show only spots from your friends list

### P2P Filter

Configure persistent filters for the P2P (park-to-park) spot command:

- **Band** - Multi-select band filter
- **Mode** - Multi-select mode filter

## Units

Select **Imperial** or **Metric** system.

**Affects:**
- Distances (miles vs kilometers)
- Temperatures (Fahrenheit vs Celsius)
- Wind speed (mph vs km/h)
- Power density (watts per foot vs watts per meter)

## Dashboard Metrics

Configure which metrics appear on the Dashboard card (1-2 metrics).

**Streak types:**
- On-Air Streak
- Activation Streak
- Hunter Streak
- {{< term "CW" >}} Streak
- Phone Streak
- Digital Streak

**Count metrics:**
- {{< term "QSO" >}}s per week/month/year
- Activations per week/month/year
- Hunts per week/month/year
- New {{< term "DXCC" >}} entities

## Backup & Restore

### iCloud Drive Backup Mirroring

Enable automatic backup mirroring to iCloud Drive. When enabled, Carrier Wave periodically writes a complete ADIF export and settings snapshot to your iCloud Drive folder. This provides an additional layer of data protection beyond CKSyncEngine sync.

### Manual Backup

Generate an on-demand backup package containing:

- Full ADIF export of all QSOs
- Settings configuration (JSON)
- Equipment profiles
- Callsign notes sources

### Restore from Backup

Import a previous backup to restore your data. Carrier Wave merges imported QSOs with existing data, using duplicate detection to avoid creating duplicates.

## WebSDR

Manage WebSDR recordings and favorites.

### Recordings Management

Browse, share, and delete saved WebSDR recordings.

### Favorites Management

Manage favorite WebSDR receivers. Search and sort by proximity to your location.

### Manual Receiver Entry

Add custom WebSDR receivers by entering host and port (advanced mode).

## Experiments

Manage experimental features in **Settings -> Experiments**. Experimental features are in active development and may have rough edges.

### Feature List

Each feature shows:

- **Name and description**
- **Maturity badge** — Alpha (red) or Beta (orange)
- **Enable/disable toggle**

### Hidden Features

Some early-stage features are hidden by default and don't appear in the Experiments list until enabled. These are typically tab-based features (Events, CW Transcription) that require explicit opt-in.

### Maturity Levels

- **Beta** — Feature-complete but may have edge cases. Safe to try.
- **Alpha** — Under active development. May have missing functionality or data-loss risk.

### RST Parse Order

Option to parse sent RST first instead of received when entering quick-entry RST reports. Configure in **Settings -> Logger -> RST Parse Order**. Applies to both the Logger and Activity Log hunter entry.

## Developer / Advanced

Advanced settings for debugging, troubleshooting, and one-time repairs.

### Debug Mode

Enable verbose logging for troubleshooting.

### Sync Debug Logs

View and share detailed sync logs as text.

### POTA Jobs Viewer

View background upload job status for {{< term "POTA" >}} activations.

### Force Re-Download Per Service

Trigger a full re-download from QRZ, LoTW, Club Log, eQSL, or Ham2K LoFi.

### Bypass Maintenance Window

Override service maintenance windows (use with caution).

### One-Time Repairs

Run database repair tasks:
- WPM backfill (compute {{< term "WPM" >}} for historical {{< term "CW" >}} {{< term "QSO" >}}s)
- Conditions backfill (fetch missing solar conditions)
- Park reference extraction (re-parse park refs from notes)
- {{< term "K-index" >}} repair (fix invalid K-index values)

### Hidden QSOs Management

View, restore, or permanently delete hidden {{< term "QSO" >}}s.

### Community Account Deletion

Delete your Carrier Wave community account. This triggers a server-side cascade deletion of all associated data.

## Bug Reports

Generate a diagnostic report for troubleshooting.

**Contents:**
- Device information
- App version
- Error logs
- Database statistics

**Actions:**
- Copy to clipboard
- Upload to dpaste
- Share via Discord support channel

## External Data

### POTA Parks Cache

View status of local {{< term "POTA" >}} parks cache and trigger manual refresh.

### QRZ Callbook Login

Authenticate with QRZ Callbook (separate from QRZ Logbook API key).

## Attributions

View credits for third-party libraries used in Carrier Wave.

## See Also

- [Service Sync Flow](/reference/sync-flow/) - How and when syncing works
- [iCloud Sync](/reference/icloud/) - Cross-device synchronization
- [Radio Control](/reference/radio-control/) - Radio connection details
- [Logger](/reference/logger/) - QSO entry and session management
- [POTA Activations](/reference/pota/) - Park activation features
- [Smart Spot Needs](/reference/smart-needs/) - Need-based spot matching
- [Troubleshooting](/reference/troubleshooting/) - Common issues and solutions
