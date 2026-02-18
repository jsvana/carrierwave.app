---
title: "Dashboard & Statistics"
description: "Activity grid, statistics, streaks, conditions, and service status"
weight: 2
showToc: true
---

The Dashboard provides a comprehensive overview of your logging activity, streaks, propagation conditions, and service status.

## Activity Grid

A GitHub-style activity visualization appears at the top of the Dashboard, showing 26-52 weeks of history depending on screen width (full year on iPad or landscape orientation).

Each cell represents one day:

- **Green** - Day with {{< term "activation" >}} contacts
- **Blue** - Day with {{< term "Activity Log" >}} entries
- **Diagonal split** - Day with both activations and activity log entries
- **Gray** - No activity

Tap any cell to view contacts and activity for that day.

## Configurable Metrics Card

Choose 1-2 key metrics to display on your dashboard card. Configure the displayed metrics in Settings → Dashboard Metrics.

### Streak Metrics

- **On-Air** - Consecutive days with any {{< term "QSO" >}}
- **Activation** - Consecutive days with {{< term "POTA" >}} activations
- **Hunter** - Consecutive days worked {{< term "POTA" >}} activators
- **CW** - Consecutive days using CW mode
- **Phone** - Consecutive days using phone modes ({{< term "SSB" >}}, {{< term "FM" >}}, {{< term "AM" >}})
- **Digital** - Consecutive days using digital modes

### Count Metrics

- QSOs per week/month/year
- Activations per week/month/year
- Hunts per week/month/year
- New {{< term "DXCC" >}} entities this period

## Statistics Grid

The main statistics display shows your {{< term "QSO" >}} counts across multiple dimensions:

### By Band

Total contacts per amateur band:

- **HF bands:** 160m, 80m, 60m, 40m, 30m, 20m, 17m, 15m, 12m, 10m
- **VHF/UHF:** 6m, 2m, 1.25m, 70cm, 33cm, 23cm

### By Mode

Contacts grouped by operating mode:

- Voice: {{< term "SSB" >}}, {{< term "CW" >}}, {{< term "FM" >}}, {{< term "AM" >}}
- Digital: {{< term "FT8" >}}, {{< term "FT4" >}}, {{< term "RTTY" >}}, {{< term "PSK31" >}}, and more

### By Country/DXCC

Unique {{< term "DXCC" >}} entities worked. The count represents distinct entities, not total {{< term "QSO" >}}s.

### Additional Statistics

- **Grid Squares** - Unique {{< term "Maidenhead grid" >}} squares worked
- **States** - US states and Canadian provinces
- **Parks Activated** - {{< term "POTA" >}} parks with valid activations
- **Parks Worked** - {{< term "POTA" >}} parks contacted as hunter
- **QRZ QSL Confirmed** - Confirmations received via {{< term "QRZ.com" >}}
- **LoTW Confirmed** - Confirmations via {{< term "LoTW" >}}

## Drill-Down Views

Tap any statistic to see the underlying contacts:

- Tap a band count to see all {{< term "QSO" >}}s on that band
- Tap a mode count to filter by that mode
- Tap a country to see contacts with that {{< term "DXCC" >}} entity
- Tap any aggregated count to view matching records

Within drill-down views:

- Sort by date, callsign, frequency, or other fields
- Apply additional filters
- Expand individual rows to show full {{< term "QSO" >}} details

## Streaks

The Dashboard displays your current streak and all-time best for comparison.

### Streak Types

- **On-Air** - Any {{< term "QSO" >}} logged
- **Activation** - {{< term "POTA" >}} activations
- **Hunter** - Worked {{< term "POTA" >}} activators
- **CW** - Contacts using CW mode
- **Phone** - Contacts using voice modes
- **Digital** - Contacts using digital modes

All streaks use UTC day boundaries. Missing a day resets the counter to zero.

### Streak Detail View

Tap a streak to view:

- Mode and band breakdowns
- Historical date ranges for the streak
- All-time best streak comparison

## Conditions Card

A compact conditions card shows recent propagation and environmental data:

- **Sparkline** - Visual trend of recent solar and weather metrics
- **Latest values** - Current K-index, {{< term "SFI" >}}, A-index
- **Link to history** - Tap to view full conditions timeline

### Conditions History View

The full conditions view displays:

- **Timeline chart** - Hourly solar conditions over time
- **By-location chart** - Conditions logged at different operating locations

Hourly solar conditions are polled in the background when enabled in Settings.

## Activity Log Card

The Activity Log card displays:

- **Setup prompt** - Appears if {{< term "Activity Log" >}} not yet configured
- **Today's stats** - {{< term "QSO" >}} count and other metrics when active

Tap the card to open today's {{< term "Activity Log" >}} detail view.

## Service Status

All configured services appear in a compact vertical list:

| Status | Meaning |
|--------|---------|
| **Green** | Synced - all {{< term "QSO" >}}s uploaded |
| **Yellow** | Syncing - upload or download in progress |
| **Red** | Error - last sync failed |
| **Gray** | Not configured or disabled |

Pending upload counts display next to each service.

### Service Detail Sheet

Tap any service to open its detail sheet showing:

- Full statistics (total {{< term "QSO" >}}s, pending uploads)
- Manual sync trigger
- Force Re-download button
- {{< term "Sync report" >}} with reconciliation details
- Error details (if applicable)

Supported services: {{< term "QRZ.com" >}}, {{< term "POTA" >}}, {{< term "LoFi" >}}, {{< term "LoTW" >}}, {{< term "HAMRS" >}}, {{< term "Club Log" >}}

## Sync Reports

Per-service sync reports visualize the sync process as a funnel:

1. **Fetched** - Records downloaded from service
2. **Validated** - Records passing validation
3. **Changes Applied** - New or updated records imported
4. **Uploaded** - Local records sent to service

Each phase displays:

- Status badges (success, warning, error)
- Record counts
- Reconciliation details

Sync reports persist across app launches.

## Background Computation

Statistics are computed on a background thread to keep the app responsive:

1. Cached statistics display immediately on opening the Dashboard
2. A background task recomputes current totals
3. Display updates when computation completes

For large logs (thousands of {{< term "QSO" >}}s), a progress bar appears during recomputation.

## Pull to Refresh

Pull down on the Dashboard to trigger:

- Statistics recomputation
- Sync check for all services

## iPad Layout

On iPad or in landscape orientation:

- **Statistics grid** - All six primary stats display in a single row
- **Activity grid** - Shows up to 52 weeks (full year)

## See Also

- [Logs & Search](/reference/logs-search/) - Query your contacts directly
- [Service Sync Flow](/reference/sync-flow/) - Understand sync timing and behavior
- [Settings & Services](/reference/settings/) - Configure service connections
- [Activity Log](/reference/activity-log/) - Daily QSO tracking for hunters
