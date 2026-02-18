---
title: "Widgets & Live Activity"
description: "Home screen widgets, lock screen widgets, and Dynamic Island"
weight: 14
showToc: true
---

Carrier Wave provides iOS home screen widgets, lock screen widgets, and a Live Activity feature to surface key information without opening the app. All widgets use an App Group for shared data access, enabling real-time updates.

---

## Live Activity

Live Activity displays an active logging session on the lock screen and in the Dynamic Island. It appears automatically when you start a logging session and updates in real time as you log {{< term "QSO" >}}s.

### What It Shows

- Current {{< term "QSO" >}} count for the session
- Operating frequency and {{< term "mode" >}}
- Park reference (for {{< term "POTA" >}} activations)
- Last {{< term "callsign" >}} logged

### Real-Time Updates

The Live Activity updates immediately when:

- A {{< term "QSO" >}} is logged
- Frequency or {{< term "mode" >}} changes
- Session is paused or resumed

If the app is terminated and relaunched during an active session, the Live Activity reconnects automatically.

### Dynamic Island

On devices with Dynamic Island, the Live Activity provides:

- **Compact view:** Minimal session info ({{< term "QSO" >}} count and park reference)
- **Expanded view:** Full session details including frequency, {{< term "mode" >}}, and last {{< term "callsign" >}}

### Ending the Activity

The Live Activity clears automatically when:

- You end the logging session
- The session is deleted

---

## Solar Conditions Widget

The Solar Conditions widget displays current space weather and propagation conditions. It is available in small, medium, and lock screen sizes.

### Home Screen Variants

**Small Widget:**
- Circular arc gauges for K-index, A-index, and {{< term "SFI" >}}
- Arc fill and color indicate propagation quality
- 2x2 color-coded band conditions grid (80m-40m, 30m-20m, 17m-15m, 12m-10m)

**Medium Widget:**
- All metrics from small widget
- Per-metric descriptions:
  - **K-index:** Quiet, Unsettled, Active, Storm
  - **A-index:** Quiet, Unsettled, Active, Storm
  - **{{< term "SFI" >}}:** Poor, Low, Good, Very Good, Excellent

### Lock Screen Variants

**Circular:**
- K-index value in a circular gauge

**Rectangular:**
- K-index, A-index, and band conditions summary

**Inline:**
- K-index value and single band condition

### Configuration

Long-press the widget to configure band selection. The widget fetches data directly from HamQSL and refreshes periodically.

---

## Stats & Streaks Widget

The Stats & Streaks widget displays your operating statistics and streaks. It is available in small and lock screen sizes.

### Configurable Metrics

Long-press the widget to select:

**Streak Types:**
- On-Air streak (consecutive days with {{< term "QSO" >}}s)
- Activation streak (consecutive days activating parks)
- Hunter streak (consecutive days hunting {{< term "POTA" >}})
- {{< term "CW" >}} streak
- {{< term "Phone" >}} streak
- Digital streak

**Count Metrics:**
- {{< term "QSO" >}}s per week/month/year
- Activations per week/month/year
- Hunts per week/month/year
- New {{< term "DXCC" >}} entities this year

### Data Source

The widget reads from App Group UserDefaults, which the main app updates after each {{< term "QSO" >}} and at session end.

---

## Radio Spots Widget

The Radio Spots widget shows live {{< term "POTA" >}} and {{< term "RBN" >}} (Reverse Beacon Network) spots. It is available in medium and large sizes.

### What It Shows

- Live spots from {{< term "POTA" >}} and {{< term "RBN" >}}
- Aligned table layout with fixed-width columns:
  - {{< term "Callsign" >}}
  - Frequency
  - {{< term "Mode" >}}
  - Park reference (for {{< term "POTA" >}} spots)
  - Timestamp

### Configuration

Long-press the widget to configure:

**Source Filter:**
- All sources
- {{< term "POTA" >}} only
- {{< term "RBN" >}} only

**Band Filter:**
- Multi-select from 160m to 2m

**{{< term "Mode" >}} Filter:**
- {{< term "CW" >}}
- {{< term "SSB" >}}
- {{< term "FT8" >}}
- {{< term "FT4" >}}
- Digital (other digital modes)

### Active Filters

Active filters appear as badges in the widget header. When more spots are available than can fit, a "+N more" indicator appears at the bottom.

### Refresh Interval

The widget refreshes every 5 minutes to fetch new spots.

### Tapping the Widget

Tapping the Radio Spots widget opens the Activity Log in the main app.

---

## Active Session Widget

The Active Session widget displays the current logging session. It is available in small, medium, and lock screen sizes.

### What It Shows

- Current {{< term "QSO" >}} count
- Park reference (for {{< term "POTA" >}} activations)
- Elapsed time since session start

### Tapping the Widget

Tapping the Active Session widget navigates directly to the Logger in the main app.

---

## Widget Configuration

All widgets support configuration via long-press. Configuration options vary by widget type and include:

- Metric or streak selection (Stats & Streaks)
- Band selection (Solar Conditions)
- Source, band, and {{< term "mode" >}} filters (Radio Spots)

### App Group

Carrier Wave uses an App Group (`group.com.jsvana.FullDuplex`) to share data between the main app and widgets. This enables:

- Real-time updates without opening the app
- Background solar polling for fresh propagation data
- Immediate reflection of logged {{< term "QSO" >}}s in stats widgets

---

## Deep Links

Tapping widgets navigates to specific areas of the app:

- **Radio Spots:** Opens Activity Log
- **Active Session:** Opens Logger
- **Solar Conditions, Stats & Streaks:** Opens Dashboard

---

## See Also

- [Dashboard & Statistics](/reference/dashboard/) - Overview of app metrics
- [Activity Log](/reference/activity-log/) - Daily QSO tracking and spot monitoring
- [Logger](/reference/logger/) - QSO entry and session management
