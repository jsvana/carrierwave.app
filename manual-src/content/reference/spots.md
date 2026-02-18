---
title: "Spot Monitoring"
description: "RBN spots, POTA spots, P2P opportunities, and propagation data"
weight: 8
showToc: true
---

The Spot Monitoring system helps you find stations to work, assess propagation, and monitor current band conditions through integration with the {{< term "RBN" >}}, {{< term "POTA" >}} spotting network, and solar/weather data sources.

## Accessing Spots

### Logger Tab Commands

From the {{< term "Logger" >}} tab, enter these commands in the callsign field to open dedicated spot panels:

- `RBN` - Show your own {{< term "RBN" >}} spots
- `RBN <callsign>` - Show spots for any callsign
- `POTA` - Open POTA spots panel
- `P2P` - Show Park-to-Park opportunities (during POTA activations only)
- `SOLAR` - Display solar conditions panel
- `WEATHER` - Show weather conditions

### iPad Persistent Sidebar

On iPad, a persistent spots sidebar appears alongside the Logger, with tabs for:

- **POTA** - Active park activators
- **RBN/My Spots** - {{< term "RBN" >}} detections
- **P2P** - Park-to-park opportunities (when activating)

### Activity Log Hunter View

The [Activity Log](/reference/activity-log/) includes a dedicated hunter spot list with filtering specific to reviewing worked stations.

## Spot Types

### RBN (Reverse Beacon Network)

The {{< term "RBN" >}} is a worldwide network of automated receiving stations that decode {{< term "CW" >}} and digital mode transmissions. Each spot includes:

- **Callsign** - Station heard
- **Frequency** - In kHz
- **Mode** - CW, FT8, FT4, etc.
- **SNR** - Signal-to-noise ratio in dB
- **Spotter location** - RBN receiver grid or location

**Data source:** Vail ReRBN API
**Time window:** Limited to spots from the last 10 minutes

Use `RBN` to monitor your own signal propagation, or `RBN <callsign>` to check if another station is being heard.

### POTA Spots

Active {{< term "POTA" >}} park activators reported by hunters. Each spot includes:

- **Callsign** - Activator's call
- **Park reference** - e.g., K-4566
- **Park name** - Full park name
- **Frequency** - Operating frequency
- **Mode** - SSB, CW, FT8, etc.
- **Time spotted** - When the spot was posted
- **Comments** - Optional hunter feedback (e.g., "QRT", "Loud signal")

**Data source:** POTA API

Use the `POTA` command to open the dedicated POTA spots panel with band and mode filtering.

### Merged Spots

The main spot list merges {{< term "POTA" >}} and {{< term "RBN" >}} data into a unified view sorted by band:

- **Human spots first** - POTA spots (manually posted by hunters) appear before RBN spots
- **Deduplication** - When the same callsign appears on the same band in both POTA and RBN, spots are combined with POTA as the preferred source
- **Band grouping** - Spots organized by band for easy scanning

This merged view gives you both human-confirmed activity (POTA) and automated detection (RBN) in one place.

### Park-to-Park (P2P)

When you're conducting a {{< term "POTA" >}} activation, the `P2P` command shows potential park-to-park opportunities by cross-referencing:

- **POTA spots** - Other active park activators
- **RBN data** - Signal detections from skimmers within 500km of your {{< term "grid square" >}}

Each P2P entry displays:

- **SNR** - Signal strength from nearby RBN receivers
- **Frequency** - Operating frequency
- **Park information** - Park reference and name
- **Age** - Time since spot posted

**Tap a P2P spot** to auto-fill the Logger with callsign, frequency, and park-to-park notes.

## Spot Visual Indicators

### Age Color Coding

Spots are color-coded by age to help you prioritize fresh activity:

- **Green** - Less than 2 minutes old (very fresh)
- **Blue** - 2-10 minutes old
- **Orange** - 10-30 minutes old
- **Gray** - Older than 30 minutes

### Badges

Spots may display badges indicating special conditions:

- **SELF** - The spotted activator matches your own callsign
- **DUPE** - You've already worked this station on the same band and date
- **TODAY** - Worked today on a different band
- **PREV** - Worked in a previous session

These indicators help you avoid duplicate contacts and identify new {{< term "multiplier" >}} opportunities.

## Filtering

The spot filtering system lets you narrow results by multiple criteria:

### Source Filter

- **POTA** - Show only POTA spots
- **RBN** - Show only RBN spots
- **All** - Merged view (default)

### Band Filter

Multi-select band filter supporting:

- All HF bands (160m through 10m)
- VHF/UHF bands (6m, 2m, 70cm)
- Select multiple bands to monitor several at once

### Mode Filter

Multi-select mode filter including:

- {{< term "CW" >}}
- {{< term "SSB" >}} (Phone)
- {{< term "FT8" >}}
- {{< term "FT4" >}}
- Other digital modes

### Age Filter

Set maximum spot age from 5 to 30 minutes. Default is 12 minutes or less. Older spots are hidden to focus on current activity.

### Proximity Filter

**"Heard Nearby" toggle** with configurable radius (100-2000 miles):

- Shows only stations detected by {{< term "RBN" >}} receivers within your specified distance
- Helps assess short-skip propagation and regional activity
- Distance calculated from your {{< term "grid square" >}} (set in Settings)

### Sort Order

- **Recent** - Newest spots first (default)
- **Frequency** - Low to high frequency

### Hide Already Worked

Toggle to suppress spots with DUPE, TODAY, or PREV badges.

### Active Filter Badges

The spot panel header displays active filter badges (e.g., "20m, CW, <12 min") for quick reference to your current filters.

## Spot Map

A mini-map at the top of the spot panel shows:

- **Spotter locations** - RBN receiver positions
- **Signal paths** - Arcs from spotter to target station
- **Signal strength indicators** - RBN spotter circles sized by {{< term "SNR" >}} (larger = stronger signal)
- **Geographic context** - Your location and spotted station location

Spotter positions are resolved via HamDB {{< term "grid square" >}} lookups.

## Background Spot Monitoring

During active logging sessions, Carrier Wave automatically monitors spots in the background:

### Automatic Polling

- **Interval:** Every 45 seconds
- **Active during:** Any open logging session
- **POTA filtering:** POTA spots included only during POTA activations

### Compact Summary Banner

When spots are detected in the background, a compact banner appears showing:

- **Spot count** - Total new spots
- **Region breakdown** - Spot counts by region (NE, EU, NA, etc.)
- **Distance range** - Minimum to maximum distance in miles/km

**Tap the banner** to expand and see individual spots.

### Persisted Spots

{{< term "RBN" >}} and {{< term "POTA" >}} spots detected during your session are saved:

- Displayed in the session detail view
- POTA spots highlighted
- RBN spots collapsed by region for easier scanning
- Provides a historical record of propagation during your activation

## Solar & Weather Conditions

### Solar Conditions (SOLAR Command)

The solar panel displays:

- **K-index** - Geomagnetic activity (0-9, lower is better)
- **SFI (Solar Flux Index)** - 10.7cm solar flux (higher is better for HF)
- **A-index** - Daily geomagnetic activity (lower is better)
- **Band conditions** - Per-band propagation forecast (day/night) showing Good/Fair/Poor ratings

**Data source:** HamQSL.com and NOAA

### Weather Conditions (WEATHER Command)

Weather panel with NOAA data including:

- **Temperature, humidity, wind**
- **Outdoor advisory** - Weather suitability for outdoor operations
- **Antenna advisory** - Wind/ice warnings for antenna safety
- **Equipment advisory** - Temperature/humidity warnings for gear

### Conditions Recording

- Solar and weather conditions are automatically recorded at session start
- Optional hourly background polling fills conditions history (enable in Settings)
- Historical conditions help correlate QSO success with propagation

## Frequency Activity

The spot system monitors nearby frequency activity from {{< term "RBN" >}} data:

### QRM Assessment

- Detects activity within ±2kHz of your frequency
- Shows how busy the frequency is
- Helps decide if it's worth calling on a crowded frequency

### Frequency Warning Banner

A unified warning banner appears when:

- License class prohibits operation on your current frequency
- Significant {{< term "QRM" >}} detected nearby

## Data Sources

| Data | Source |
|------|--------|
| RBN spots | Vail ReRBN API |
| POTA spots | POTA API |
| Solar data | NOAA / HamQSL |
| Spotter locations | HamDB.org |

## See Also

- [Logger](/reference/logger/) - Log contacts from spot data
- [POTA Activations](/reference/pota/) - POTA-specific activation features
- [Activity Log](/reference/activity-log/) - Review worked stations and hunter spots
- [WebSDR Integration](/reference/websdr/) - Remote receiver integration for propagation assessment
