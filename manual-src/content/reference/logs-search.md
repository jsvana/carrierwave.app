---
title: "Logs & Search"
description: "Query language, filters, QSO detail, and session browsing"
weight: 3
showToc: true
---

The Logs tab provides powerful search and filtering capabilities for exploring your QSO history, with full {{< term "ADIF" >}} metadata display and sync status tracking.

## Log List

The default view shows your most recent contacts in reverse chronological order. Each entry displays:

- **Callsign** (with nickname if available from callsign notes, and emoji if configured)
- **Contact count badge** (bronze at 10 QSOs, silver at 25, gold at 50)
- **Date and time** (UTC)
- **Frequency** (if logged)
- **Band and mode**
- **RST exchanged**
- **Park references** (POTA, with park names when available)
- **Sync status indicators** (one badge per service)

Tap any entry to view the full QSO detail.

## Search

The search bar supports two modes: simple callsign search and structured query language.

### Simple Search (Implicit Callsign Search)

When you enter plain text without field qualifiers, Carrier Wave treats it as a callsign prefix search:

```
W1AW
K6TEST
VE3
```

- Text is automatically uppercased
- Acts as `callsign:<text>*` wildcard search
- Searches across their call, your call, and operator call fields
- An info note appears when using implicit callsign search

### Query Language

For precise searches, use field-specific queries.

#### Field Queries

| Query | Meaning |
|-------|---------|
| `call:K6TEST` | Exact callsign match |
| `call:K6*` | Wildcard callsign (prefix) |
| `band:20m` | Contacts on 20 meters |
| `mode:cw` | CW mode contacts |
| `mode:ssb` | SSB mode contacts |
| `mode:ft8` | FT8 mode contacts |
| `state:CA` | California stations |
| `grid:CM87` | Grid square (4 or 6 char) |
| `park:US-0001` | Specific POTA park |
| `park:K-*` | Any US POTA park (wildcard) |
| `freq:14.074` | Specific frequency |
| `freq:>14.0` | Above 14 MHz |
| `power:>100` | Over 100W |

#### Source Filters

Filter by import or sync source:

| Query | Meaning |
|-------|---------|
| `source:clublog` | Imported from Club Log |
| `source:qrz` | Imported from QRZ |
| `source:pota` | Downloaded from POTA |
| `source:lofi` | Synced from Ham2K LoFi |
| `source:lotw` | Downloaded from LoTW |
| `source:logger` | Logged in Carrier Wave |

#### Date Queries

| Query | Meaning |
|-------|---------|
| `date:today` | Today's contacts (UTC) |
| `date:yesterday` | Yesterday's contacts |
| `after:7d` | Last 7 days |
| `after:30d` | Last 30 days |
| `after:2024-01-01` | Since January 1, 2024 |
| `before:2024-06-01` | Before June 1, 2024 |
| `date:2024-01` | Specific month (January 2024) |
| `date:2024` | Specific year |

#### Status Queries

| Query | Meaning |
|-------|---------|
| `confirmed` | Confirmed via LoTW |
| `confirmed:lotw` | LoTW confirmed |
| `confirmed:qrz` | QRZ QSL confirmed |
| `synced:pota` | Uploaded to POTA |
| `synced:qrz` | Uploaded to QRZ |
| `pending` | Awaiting sync to any service |
| `pending:yes` | Same as `pending` |

#### Combining Queries

Use **spaces** for **AND** (all conditions must match):

```
band:20m mode:cw after:30d
```

Finds CW contacts on 20 meters in the last 30 days.

Use **`|`** for **OR** (any condition matches):

```
call:W1AW | call:K1ABC
```

Finds contacts with either W1AW or K1ABC.

Use **`-`** for **NOT** (exclude matches):

```
-mode:ft8
```

Excludes FT8 contacts.

```
band:20m -state:CA
```

20 meter contacts excluding California.

#### Examples

**W1AW on 40 meters:**

```
call:W1AW band:40m
```

**SSB contacts with Colorado stations this year:**

```
state:CO mode:ssb after:2024-01-01
```

**All POTA contacts in the last week:**

```
park:* after:7d
```

**Park-to-park (P2P) contacts:**

```
park:* theirpark:*
```

**Confirmed but not yet uploaded to QRZ:**

```
confirmed:lotw -synced:qrz
```

### Quick Filters

The filter menu (three horizontal lines icon) provides common search presets:

- Last 7 days
- Last 30 days
- This year
- CW contacts
- FT8 contacts
- SSB contacts
- POTA activations
- LoTW confirmed
- Pending upload

Tap a quick filter to populate the search bar.

### Performance Warnings

Carrier Wave analyzes your query and warns about potentially slow searches. Warnings appear when:

- Searching a large log (>5,000 QSOs) without indexed field filters
- Using only non-indexed fields (e.g., notes, grid)
- Full-table scans are required

When warned:

- Click **Search Anyway** to proceed
- Click **Add Date Filter** to add `after:30d` and narrow results
- Add field-specific filters (callsign, band, mode, date) for better performance

**Performance note:** Field-specific queries use database predicates for efficient full-table search. Simple callsign searches and indexed field queries execute quickly even on large logs.

### Help Sheet

Tap the filter menu and select **Search Help** to view the syntax reference in-app.

## QSO Detail View

Tap any contact to view the full QSO record. The detail view shows:

### Header
- **Callsign** (large, monospaced)
- **Name** (if available)
- **Location** (QTH, state, country)
- **License class** (if known)

### Contact Section
- **Date and time** (UTC)
- **Band and mode**
- **Frequency** (if logged)
- **RST sent and received**
- **Power** (if logged)
- **Radio/rig** (if logged)

### Location Section
- **My grid** (Maidenhead locator)
- **Their grid**
- **My park** (POTA reference, with name)
- **Their park** (for P2P contacts)
- **SOTA reference** (if applicable)
- **DXCC entity** (country name and number)

### Notes Section
- **Notes** (free-form text, if present)

### Sync Status Section

Shows per-service sync indicators:

- **Service badges** (colored pills showing status)
- **Status text** (Present, Submitted, Rejected, Pending Upload)
- **Last confirmed date** (if available)
- **Confirmation stars** (LoTW, QRZ QSL)

**Badge colors:**

- **Green:** Present/synced
- **Blue:** Submitted, awaiting confirmation
- **Orange:** Pending upload (service configured)
- **Gray:** Pending upload (service not configured)

### Source Section
- **Import source** (Logger, LoFi, QRZ, POTA, etc.)
- **Imported date**
- **QRZ Log ID** (if synced from QRZ)
- **Raw {{< term "ADIF" >}}** (expandable disclosure for debugging)

### Actions

From the QSO detail view, you can:

- **Edit** — Modify any field (changes saved locally and re-queued for sync)
- **Delete** — Soft delete (hides QSO, prevents future sync)

## Editing QSOs

Tap **Edit** from the detail view to modify any field. Changes are:

1. **Saved locally** to your SwiftData store
2. **Re-queued for sync** to services that support updates (QRZ, POTA, Club Log)

**Note:** Some services don't support updating previously uploaded QSOs. Updates may only apply to future uploads.

## Deleting QSOs

Tap **Delete** from the detail view to remove a contact.

**Deletion behavior:**

- **Soft delete** — QSOs are hidden, not permanently removed from the database
- **Hidden QSOs** don't appear in lists, stats, maps, or activations
- **Sync prevention** — Hidden QSOs won't sync to cloud services
- **Reversible** — View and restore hidden QSOs in **Settings → Developer → Hidden QSOs**

**Important:** Deletion does NOT remove QSOs from cloud services. Most services (QRZ, POTA, LoTW) don't support remote deletion via API.

## Sessions Tab

The Sessions tab (within Logs) provides a browsable history of all completed logging sessions, grouped by month.

### Session List

Each session row shows:

- **Date and time**
- **Activation type** (POTA, Rove, Hunter, General)
- **Park reference(s)** (for POTA activations)
- **QSO count**
- **QSO timeline** (horizontal bar showing contact timing and band changes)
- **Conditions badges** (solar and weather indicators)
- **Equipment badges** (radio, antenna, key/mic)
- **Recording indicator** (microphone icon if WebSDR recording exists)
- **Upload status** (for POTA sessions: pending, completed, failed)

### Session Grouping

Sessions are grouped by month in reverse chronological order (most recent first).

### Recording Navigation

Sessions with WebSDR recordings show a microphone icon. Tap the session to:

- Navigate to the **Recording Player** (full-screen with transport controls)
- View the **QSO list** synced to recording timestamps
- **Share clips** (select range, export M4A)

See [WebSDR Recording](/reference/websdr/) for details.

### Session Detail

Tap any session to view:

- **Full equipment list**
- **Session photos** (with full-screen viewer)
- **Notes** (operator comments)
- **Persisted spots** (RBN and POTA spots captured during the session)
- **QSO list** (expandable rows with swipe-to-delete)
- **Edit button** (modify equipment, photos, notes)

For **POTA activations**, the detail view additionally shows:

- **Upload button** (submit to POTA)
- **Reject option** (mark QSOs as hidden, prevent upload)
- **Share card** (generate brag sheet with map and stats)
- **Export ADIF** (download activation log for offline use)
- **Activation statistics** (charts, distance histogram, rate analysis)

See [Service Sync Flow](/reference/sync-flow/) for POTA upload details.

## See Also

- [Dashboard & Statistics](/reference/dashboard/) — View aggregated stats and drilldown views
- [Service Sync Flow](/reference/sync-flow/) — Understand sync behavior and status indicators
- [Logger](/reference/logger/) — Log new contacts during activations
- [WebSDR Recording](/reference/websdr/) — Remote SDR integration and playback
