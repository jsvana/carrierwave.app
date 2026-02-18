---
title: "Map View"
description: "QSO map with contacts, geodesic arcs, and activation maps"
weight: 12
showToc: true
---

The Map View displays your {{< term "QSO" >}} contacts on an interactive world map with markers, geodesic paths, and performance-optimized rendering.

## Overview

Map View provides visual insight into your operating patterns by showing:

- Contact locations with marker pins
- Geodesic arc paths from your station to contacted stations
- Distance and direction statistics
- Geographic coverage (states, {{< term "DXCC" >}} entities)
- Real-time session maps during active logging

All map rendering respects your privacy settings and only displays contacts you've logged locally.

## QSO Map

The main map displays your logged contacts as markers on a world map.

### Contact Markers

Each marker represents a station you've contacted. The marker is placed at the station's location based on:

- {{< term "Grid Square" >}} coordinates (if logged)
- {{< term "QTH" >}} data from {{< term "QRZ" >}} lookup
- State/country geolocation (fallback)

Markers are color-coded and sized to indicate density in areas with many contacts.

### Geodesic Arcs

Lines connecting your station to each contacted station follow the great circle (shortest) path over Earth's surface. These arcs show:

- True bearing from your location
- Visual representation of propagation paths
- Distance coverage patterns

Arcs are semi-transparent to prevent clutter in densely-contacted areas.

### Performance Limit

To maintain smooth interaction on large logs, the map defaults to displaying **500 QSOs** maximum. This limit ensures:

- Fast rendering and panning
- Responsive zooming
- Low memory usage

**Show All Toggle:** Tap the "Show All" button to render your entire log on the map. On logs with thousands of contacts, rendering may take a few seconds. The app caches the result for subsequent loads.

## Map Statistics Overlay

A heads-up statistics panel displays key metrics for the visible contacts:

| Metric | Description |
|--------|-------------|
| **QSO Count** | Total contacts displayed on the map |
| **Average Distance** | Mean distance from your station to all contacts |
| **Longest Distance** | Furthest contact ({{< term "DX" >}} record) |
| **States Worked** | Count of unique US states and Canadian provinces |
| **DXCC Entities** | Count of unique countries worked |
| **QSOs/hr Rate** | Average contact rate during the time span |
| **Time Span** | Date range of displayed contacts |

These statistics update in real time as you apply filters.

## Filtering

The map supports multi-dimensional filtering to focus on specific operating conditions.

### Date Range Filter

Set a start and end date to view contacts from a specific period. The filter defaults to your earliest {{< term "QSO" >}} date through the current date.

**Use cases:**
- View a single activation day
- Compare year-over-year coverage
- Isolate contest weekends

### Band Filter

Filter by amateur {{< term "band" >}} (e.g., 20m, 40m, 2m). Useful for:

- Analyzing band-specific propagation
- Visualizing {{< term "VHF" >}}/{{< term "UHF" >}} local coverage vs. {{< term "HF" >}} DX
- Comparing antenna performance across bands

### Mode Filter

Restrict the map to contacts using a specific {{< term "mode" >}} ({{< term "SSB" >}}, {{< term "CW" >}}, {{< term "FT8" >}}, etc.).

**Example:** Filter to CW only to see where your key has reached.

### Park Filter

For {{< term "POTA" >}} activators, filter by park reference (e.g., US-0001) to display only contacts made during that activation.

This is especially useful for reviewing single-park performance or comparing different park locations.

### Confirmed Filter

Show only QSOs confirmed via {{< term "QRZ" >}} or {{< term "LoTW" >}}. The app displays the **union** of both confirmation sources - any contact confirmed by either service is included.

**Use cases:**
- Track {{< term "WAS" >}} or {{< term "DXCC" >}} progress
- Identify unconfirmed contacts for targeted {{< term "QSL" >}} follow-up

### Active Filter Badges

All active filters are displayed as badges at the top of the map. Tap any badge to remove that filter. The badge display remains visible even when scrolling, so you always know what subset of your log is shown.

## Individual QSO Toggle

The **Show Individual QSOs** toggle switches between two rendering modes:

### Grid Square Mode (Default)

Contacts are aggregated by grid square. A single marker represents all QSOs within that 4-character or 6-character grid. The marker label shows the QSO count for that grid.

**Best for:** Large logs where individual contacts would clutter the map.

### Individual QSO Mode

Every contact is displayed as a small dot marker. Tapping a marker shows that specific QSO's details.

**Best for:**
- Small QSO counts (single activation, field day)
- Reviewing specific contacts
- Detailed path analysis

## Activation Maps

{{< term "POTA" >}} activations have dedicated map views accessible from the activation detail screen.

### RST-Based Contact Coloring

On activation maps, QSO markers are color-coded by signal report:

| Color | RST Range | Interpretation |
|-------|-----------|----------------|
| **Green** | 59, 599 | Strong signals |
| **Yellow** | 57-58, 579-589 | Good signals |
| **Red** | <57, <579 | Weak signals |

This visualization helps identify:

- Propagation sweet spots around the park
- Dead zones or directions with poor coverage
- Optimal antenna orientations

### Accessing Activation Maps

1. Open the **POTA** tab
2. Tap an activation entry
3. Tap **View Map** in the activation detail view

## QSO Callouts

Tap any contact marker to see a detailed callout overlay:

### Basic Information

- **Callsign**
- **Frequency** (in MHz)
- **Mode**
- **RST Sent / RST Received**

### Equipment (POTA Activations)

For {{< term "POTA" >}} contacts, additional equipment metadata is shown:

- **Radio** - Rig model used
- **Antenna** - Antenna type and configuration
- **Key** - CW key or paddle model (for CW contacts)
- **Microphone** - Mic model (for voice contacts)

### Morse Speed (CW)

For CW QSOs, the callout displays:

- **WPM** - Words per minute (sending speed)

### Solar Conditions (POTA)

POTA activation QSOs include solar condition metadata:

- **Solar Flux Index (SFI)** - 10.7 cm radio flux
- **Sunspot Number (SSN)**
- **A-Index** - Geomagnetic activity
- **K-Index** - 3-hour geomagnetic activity

These fields help correlate propagation conditions with contact quality.

## Rove Session Maps

Rove sessions (multi-park activations in a single outing) display a specialized map layout:

### Numbered Park Markers

Each park stop in the rove is marked with a numbered pin (1, 2, 3...) in the order you visited them.

### Dashed Route Line

A dashed line connects the park markers in chronological order, showing your route through the activation.

### All Parks Visible

The map zooms to fit all parks in the operation, giving a bird's-eye view of your roving path.

**Use cases:**
- Planning future rove routes
- Sharing your activation journey
- Visualizing time spent at each stop

## Session Map (MAP Command)

While logging an active session, you can view a real-time map of your current QSOs.

### Triggering the Session Map

In the **Logger** tab, type:

```
MAP
```

This opens a map view showing only contacts from the current logging session.

### Live Updates

As you log additional QSOs, the session map updates in real time. The map automatically zooms to fit all contacts.

### Session vs. Full Map

The session map is isolated from your full log. It resets when you:

- End the logging session
- Start a new activation
- Change operating bands or modes (if configured to create a new session)

**Tip:** Use the session map during {{< term "Contest" >}} or field day operations to track geographic coverage goals in real time.

## See Also

- [Logger](/reference/logger/) - Record contacts and start sessions
- [POTA Activations](/reference/pota/) - Park activation workflow
- [Dashboard & Statistics](/reference/dashboard/) - Aggregate statistics and drill-down views
