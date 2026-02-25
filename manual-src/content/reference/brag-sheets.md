---
title: "Period Brag Sheets"
description: "Configurable weekly, monthly, and all-time shareable stats cards"
weight: 16
showToc: true
---

## Overview

Period brag sheets are shareable image cards summarizing your operating achievements over a specific time window — **this week**, **this month**, or **all time**. Unlike activation brag sheets (which cover a single {{< term "POTA" >}} session), period brag sheets aggregate across all your {{< term "QSO" >}}s to surface personal records, milestones, and bragging rights.

Every stat on a period brag sheet is **configurable** — you choose which stats appear, how they're arranged, and which numbers matter most to you.

Access period brag sheets from the **Dashboard** toolbar or the **Logs** tab share menu.

## Time Windows

Each brag sheet covers one of three periods:

- **Weekly** — Monday 0000Z through Sunday 2359Z (current or most recent complete week)
- **Monthly** — First through last day of the calendar month (UTC)
- **All Time** — Every {{< term "QSO" >}} in your log

The selected period applies to all stats on the card. Where relevant, stats show the specific date and {{< term "QSO" >}} that achieved the record.

---

## Configuration

### How Configuration Works

Each period (weekly, monthly, all time) has its own independent brag sheet configuration. This allows you to highlight different things on each card — for example, your weekly card might focus on rate and volume, while your all-time card showcases distance records and geographic reach.

Configure brag sheets in **Settings → Brag Sheets**, or tap **Customize** on the brag sheet preview before sharing.

### Stat Picker

The stat picker lets you build your brag sheet by toggling individual stats on or off:

1. Open **Settings → Brag Sheets**
2. Select a period tab (**Weekly**, **Monthly**, or **All Time**)
3. Browse stats organized by category
4. Toggle individual stats on or off
5. Drag to reorder stats within and across categories

Each stat shows a live preview of its current value so you can see what will appear on the card.

### Hero Stats

Choose **3–4 stats** to feature prominently in the hero row at the top of the card. These are displayed large and serve as the visual anchor. Any enabled stat can be promoted to the hero row by tapping the star icon next to it in the stat picker.

**Default hero stats:** Total QSOs, Furthest Contact, DXCC Entities, Best Session Rate

### Presets

Presets provide curated stat selections for common operating styles. Apply a preset as a starting point, then customize further.

| Preset | Description | Key Stats Included |
|--------|-------------|-------------------|
| **General** | Balanced overview for any operator | Total QSOs, Furthest Contact, DXCC Entities, States, Active Bands, Active Modes, Operating Days, Best Session Rate |
| **DXer** | Focused on distance and entities | Furthest Contact, Furthest per Band, DXCC Entities, New DXCC, Continents, Most Countries in a Day, Grid Squares, Total Distance |
| **QRP** | For low-power operators | Lowest Power Contact, Best Watts-per-Mile, Furthest QRP Contact, QRP QSO Count, Milliwatt QSO Count, Furthest Contact, Total Distance |
| **Activator** | POTA activation highlights | Parks Activated, Best Activation, Fastest Activation, Park-to-Park Contacts, Largest N-fer, New Parks, Total QSOs, Best Session Rate |
| **Contester** | Speed and volume | Fastest 10 QSOs, Peak 15-Minute Rate, Best Session Rate, Most QSOs in a Day, Total QSOs, Active Bands, Unique Callsigns |
| **CW Enthusiast** | Morse code focused | CW QSO Count, Fastest CW Speed, CW Distance Record, CW QRP Record, Peak 15-Minute Rate, Perfect Reports, Current On-Air Streak |
| **Show Everything** | Every stat enabled | All stats from all categories |

Applying a preset replaces the current stat selection for that period. Your previous configuration is not lost — tap **Undo** to revert.

### Per-Period Defaults

When you first access period brag sheets, each period starts with sensible defaults:

- **Weekly** — Uses the **Contester** preset (rate, volume, and activity focused)
- **Monthly** — Uses the **General** preset (balanced overview)
- **All Time** — Uses the **DXer** preset (records and geographic reach)

These defaults are applied once and can be changed at any time.

### Copy Configuration Between Periods

Long-press a period tab to copy its configuration to another period. This is useful when you want similar layouts across time windows with minor tweaks.

---

## Stats Categories

Stats are organized into categories for browsing in the stat picker. Each stat can be individually enabled or disabled.

### Totals

Summary counts for the period.

| Stat | Description |
|------|-------------|
| **Total QSOs** | Contact count for the period. |
| **Total CW QSOs** | CW-mode contact count. |
| **Total Phone QSOs** | Voice-mode (SSB, FM, AM) contact count. |
| **Total Digital QSOs** | Digital-mode (FT8, FT4, RTTY, PSK31, etc.) contact count. |
| **Total Distance** | Cumulative distance across all contacts with known grids. (e.g., "Your signals traveled 142,000 km this month.") |
| **Operating Days** | Distinct UTC days with at least one QSO. |
| **Operating Hours** | Total time spent in active sessions (excludes gaps longer than 15 minutes). |
| **Active Bands** | Number of distinct bands used. |
| **Active Modes** | Number of distinct modes used. |
| **Unique Callsigns** | Distinct stations worked. |
| **QRP QSO Count** | Contacts made at 5W or less. |
| **Milliwatt QSO Count** | Contacts made at less than 1W. |

### Speed & Rate

Metrics that highlight how fast you operate.

| Stat | Description |
|------|-------------|
| **Fastest 10 QSOs** | Shortest elapsed time to log 10 consecutive contacts within a single session. Shows the session, date, and elapsed time (e.g., "10 QSOs in 8m 22s"). |
| **Peak 15-Minute Rate** | Highest number of {{< term "QSO" >}}s logged in any 15-minute sliding window. Expressed as raw count and projected hourly rate (e.g., "12 QSOs / 48 per hr"). |
| **Best Session Rate** | Highest average QSOs/hour for any session with 10+ contacts. Excludes idle gaps longer than 15 minutes. |
| **Fastest Activation** | Shortest time from first to tenth {{< term "QSO" >}} in a {{< term "POTA" >}} activation (time to valid activation). |

### Distance

How far your signal reached.

| Stat | Description |
|------|-------------|
| **Furthest Contact** | Maximum distance {{< term "QSO" >}}, computed from {{< term "Maidenhead grid" >}} squares. Shows callsign, distance (km/mi), and band. |
| **Furthest Contact per Band** | Best DX on each band you've operated. Compact table with band, callsign, and distance. |
| **Furthest QRP Contact** | Longest-distance {{< term "QSO" >}} made at 5 watts or less. |
| **Average Contact Distance** | Mean distance across all contacts with known grids. |

### Power & Efficiency

Doing more with less.

| Stat | Description |
|------|-------------|
| **Lowest Power Contact** | {{< term "QSO" >}} made at the lowest transmit power. Shows watts, callsign, distance, and band. |
| **Best Watts-per-Mile** | Most efficient contact: lowest ratio of transmit power to distance. Rewards QRP DX. (e.g., "0.003 W/mi — 5W to JA1ABC at 5,400 mi on 20m"). |

### Geographic Reach

How much of the world you've worked.

| Stat | Description |
|------|-------------|
| **DXCC Entities** | Unique {{< term "DXCC" >}} countries worked in the period. |
| **New DXCC Entities** | DXCC entities worked for the first time ever (all-time firsts, even on weekly/monthly cards). |
| **States & Provinces** | Unique US states and Canadian provinces. |
| **Grid Squares** | Unique {{< term "Maidenhead grid" >}} squares worked. |
| **Continents** | Number of continents contacted (out of 6 inhabited). |
| **Most Continents in a Day** | Best single UTC day for continent diversity. |
| **Worked All States Progress** | X/50 US states — shown as a progress bar. |

### Volume Records

Personal bests for operating output.

| Stat | Description |
|------|-------------|
| **Most QSOs in a Day** | Best single UTC day by contact count. Shows date and count. |
| **Most QSOs in a Session** | Largest single session by contact count. |
| **Most Countries in a Day** | Best single-day DXCC count. |
| **Most Bands in a Day** | Most distinct bands used in a single UTC day. |

### Streaks

Consistency is its own flex.

| Stat | Description |
|------|-------------|
| **Current On-Air Streak** | Consecutive days with at least one {{< term "QSO" >}}. |
| **Best On-Air Streak** | Longest on-air streak in the period (or all-time). |
| **Current Activation Streak** | Consecutive days with a {{< term "POTA" >}} activation. |
| **Mode Streaks** | Longest streak for CW, Phone, and Digital individually. |

### POTA

Parks on the Air highlights.

| Stat | Description |
|------|-------------|
| **Parks Activated** | Unique parks with valid activations (10+ QSOs). |
| **Parks Hunted** | Unique parks contacted as a hunter. |
| **Park-to-Park Contacts** | Total P2P QSOs in the period. |
| **Largest N-fer** | Most parks activated simultaneously (2-fer, 3-fer, etc.). |
| **Best Activation** | Activation with the most QSOs in the period. Shows park, date, and count. |
| **New Parks** | Parks activated or hunted for the first time. |

### CW

Morse code highlights.

| Stat | Description |
|------|-------------|
| **Fastest CW Speed** | Highest WPM logged. |
| **CW Distance Record** | Furthest CW-mode contact. |
| **CW QRP Record** | Furthest CW contact at 5W or less. |

### Signal Quality

How well you're being heard.

| Stat | Description |
|------|-------------|
| **Perfect Reports** | Count of 599 (CW) or 59 (Phone) reports received. |
| **Average RST Received** | Mean signal report across contacts. |
| **Best RST at Distance** | Furthest contact where you still received a 59/599 report. |

### Fun & Unique

Conversation starters.

| Stat | Description |
|------|-------------|
| **Earliest QSO of the Day** | Contact closest to 0000Z — who's up late (or early)? |
| **Latest QSO of the Day** | Contact closest to 2359Z. |
| **Longest Session** | Duration of your longest single operating session. |
| **Most Active Day of the Week** | Which day of the week (Mon–Sun) you log the most contacts. |
| **Busiest Band** | The band with the most QSOs in the period. |
| **Busiest Mode** | The mode with the most QSOs in the period. |
| **Repeat Customers** | Station you've worked the most times (callsign and count). |

---

## Professional Statistician Mode

When **Professional Statistician Mode** is enabled (Settings → POTA → Professional Statistician Mode), period brag sheets gain an additional set of charts, distributions, and deep-dive analytics. These appear in a dedicated section below the standard stats body.

Professional Statistician Mode stats are also individually toggleable in the stat picker, under a dedicated **Pro Stats** category.

### Charts & Visualizations

| Chart | Description |
|-------|-------------|
| **Band Distribution** | Pie chart or horizontal bar showing QSO breakdown by band. Segments are color-coded to match standard band colors. |
| **Mode Distribution** | Pie chart or horizontal bar showing QSO breakdown by mode (CW, SSB, FT8, FM, etc.). |
| **QSO Rate Over Time** | Line graph showing contacts per hour across the period. Weekly shows hourly bins per day; monthly shows daily bins; all-time shows weekly or monthly bins. |
| **Distance Distribution Histogram** | Histogram of contact distances bucketed into ranges (0–500 km, 500–1000 km, etc.). Shows how your contacts are distributed geographically. |
| **Distance CDF** | Cumulative distribution function of contact distances. Shows what percentage of contacts fell within various distance thresholds. |
| **Timing CDF** | Cumulative distribution of inter-QSO timing. Shows how quickly contacts accumulated — steep curves indicate fast operating runs. |
| **Daily Activity Bar Chart** | QSO count per UTC day across the period. Color-coded by primary band or mode used each day. |
| **Hour-of-Day Heatmap** | 24-column heatmap showing which UTC hours you're most active. Intensity represents QSO count. |
| **Day-of-Week × Hour Heatmap** | 7×24 grid showing your activity pattern across the week. Reveals your preferred operating schedule. |

### Statistical Summaries

| Stat | Description |
|------|-------------|
| **Distance Box Plot** | Box-and-whisker plot showing median, quartiles, and outlier contacts by distance. |
| **RST Box Plot** | Box plot of received signal strength (S component). Separate plots for CW and Phone modes. |
| **Inter-QSO Timing Box Plot** | Box plot showing the distribution of time between consecutive contacts. Highlights your typical pacing and outlier gaps. |
| **Distance Percentiles** | Table of distance at the 25th, 50th, 75th, 90th, and 99th percentiles. |
| **RST Distribution** | Histograms bucketed by R (readability), S (signal strength), and T (tone for CW). Separate analysis for each RST component. |
| **Band × Mode Matrix** | Cross-tabulation table showing QSO counts at each band/mode intersection. Highlights where you operate most. |
| **Band × Distance Summary** | Per-band statistics: median distance, max distance, QSO count. Table format for quick comparison. |
| **Power × Distance Scatter** | Scatter plot of transmit power vs. contact distance. Highlights the efficiency frontier — contacts in the lower-right (low power, high distance) are most impressive. |

### Derived Metrics

| Metric | Description |
|--------|-------------|
| **Median Contact Distance** | 50th percentile distance (often more meaningful than average for skewed distributions). |
| **Distance Standard Deviation** | Spread of contact distances — high values indicate diverse DX and local mix. |
| **Operating Efficiency** | QSOs per operating hour, excluding idle time. A refined version of session rate that spans the entire period. |
| **Peak Hour** | The single UTC hour with the most contacts in the period. |
| **Peak Day** | The single UTC day with the most contacts, shown with a breakdown by band and mode. |
| **Band Diversity Index** | Shannon entropy of band distribution — higher values mean more even band usage. |
| **Mode Diversity Index** | Shannon entropy of mode distribution. |
| **Geographic Spread** | Convex hull area (in km²) of all contacted grid squares. A single number representing how much of the globe you reached. |
| **QSO Clustering Score** | Measures how "bursty" your operating is — do you log in concentrated runs or spread evenly throughout the period? |

### Pro Stats Presets

Two additional presets are available when Professional Statistician Mode is enabled:

| Preset | Description |
|--------|-------------|
| **Analyst** | All standard stats plus charts (band/mode distributions, rate over time, distance histogram, daily activity). No box plots or derived metrics. Good for visual-heavy cards. |
| **Full Statistician** | Everything enabled — all standard stats, all charts, all box plots, all derived metrics. Makes a tall, data-dense card. |

---

## Brag Sheet Layout

### Card Structure

Period brag sheets follow a consistent visual layout:

**Header**
- Your callsign and operator name
- Period label (e.g., "Week of Feb 17–23, 2026" or "February 2026" or "All Time")
- Carrier Wave branding

**Hero Stats Row**
- 3–4 configurable headline numbers displayed large
- These serve as the visual anchor of the card

**Stats Body**
- Enabled stats rendered in order, grouped by category
- Each stat shows label, value, and supporting detail (callsign, date, band) where applicable
- Gold highlight badge on stats where an all-time record was set or broken during this period

**Activity Visualization**
- Weekly: day-by-day bar chart of QSO count (7 bars)
- Monthly: day-by-day activity grid (calendar heatmap)
- All Time: band/mode distribution pie charts

**Map** (optional, toggleable)
- World map with contact markers and arcs
- Same RST color coding as activation brag sheets

**Footer**
- Date generated
- Carrier Wave logo

### Adaptive Sizing

The card automatically adjusts its height based on how many stats are enabled. Cards with fewer stats are more compact; cards with many stats expand to fit. The 16:9 aspect ratio is maintained by scaling the content area.

---

## Settings

Configure period brag sheets in **Settings → Brag Sheets**.

### General

| Setting | Description | Default |
|---------|-------------|---------|
| **Include Map** | Show world map visualization with contact arcs | On |
| **Include Equipment Summary** | Show primary rig and antenna | Off |
| **Unit Preference** | Miles or kilometers for distance stats | Follows app-wide Units setting |
| **Gold Record Badges** | Highlight stats where an all-time record was set during the period | On |

### Per-Period Configuration

Each period tab (Weekly, Monthly, All Time) has:

| Setting | Description |
|---------|-------------|
| **Enabled Stats** | Toggle individual stats on or off |
| **Stat Order** | Drag to reorder stats within the card |
| **Hero Stats** | Star up to 4 stats to feature in the hero row |
| **Apply Preset** | Replace current selection with a curated preset |
| **Reset to Default** | Restore the default configuration for this period |

---

## Sharing

Period brag sheets share via the same flow as activation brag sheets:

1. Generate a brag sheet from the Dashboard or Logs tab
2. Optionally tap **Customize** to adjust stats before sharing
3. Preview the card image
4. Use **ShareLink** for iOS share sheet (Messages, Mail, AirDrop, social media)
5. Or tap **Save to Photos** for quick saving

The card image uses high contrast colors for readability at various sizes on social media platforms.

## See Also

- [Export & Sharing](/reference/export/) — Activation brag sheets, ADIF export, and daily share cards
- [Dashboard & Statistics](/reference/dashboard/) — Activity grid, streaks, and drill-down views
- [Community & Activity](/reference/community/) — Challenges, leaderboards, and achievements
- [POTA (Parks on the Air)](/reference/pota/) — Activation tracking and park management
- [Settings & Services](/reference/settings/) — All app configuration including brag sheet settings
