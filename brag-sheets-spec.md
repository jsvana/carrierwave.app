# Period Brag Sheets — Feature Spec

Configurable, shareable image cards showing weekly, monthly, and all-time operating stats. Each period has its own independent configuration. Users pick which stats appear, drag to reorder, and promote up to 4 stats to a hero row.

## Time Windows

- **Weekly** — Monday 0000Z through Sunday 2359Z
- **Monthly** — Calendar month (UTC)
- **All Time** — Entire QSO log

## Configuration Model

- Each period (weekly/monthly/all-time) has an **independent** stat selection and ordering
- Individual stats are toggled on/off in a **stat picker** organized by category
- Any enabled stat can be **starred** to appear in the hero row (max 4)
- Stats are **drag-to-reorder** within the card
- **Presets** provide curated starting points (can be customized after applying)
- **Copy config** between periods via long-press on period tab

### Presets

| Preset | Focus | Key Stats |
|--------|-------|-----------|
| **General** | Balanced overview | Total QSOs, Furthest Contact, DXCC Entities, States, Active Bands, Active Modes, Operating Days, Best Session Rate |
| **DXer** | Distance & entities | Furthest Contact, Furthest per Band, DXCC Entities, New DXCC, Continents, Most Countries in a Day, Grid Squares, Total Distance |
| **QRP** | Low power | Lowest Power Contact, Best Watts-per-Mile, Furthest QRP Contact, QRP QSO Count, Milliwatt QSO Count, Furthest Contact, Total Distance |
| **Activator** | POTA | Parks Activated, Best Activation, Fastest Activation, P2P Contacts, Largest N-fer, New Parks, Total QSOs, Best Session Rate |
| **Contester** | Speed & volume | Fastest 10 QSOs, Peak 15-Min Rate, Best Session Rate, Most QSOs in a Day, Total QSOs, Active Bands, Unique Callsigns |
| **CW Enthusiast** | Morse code | CW QSO Count, Fastest CW Speed, CW Distance Record, CW QRP Record, Peak 15-Min Rate, Perfect Reports, On-Air Streak |
| **Show Everything** | All stats | Every stat from every category |

### Per-Period Defaults

- Weekly → **Contester** preset
- Monthly → **General** preset
- All Time → **DXer** preset

## Stats — All Categories

### Totals

- **Total QSOs** — Contact count for the period
- **Total CW QSOs** — CW-mode contact count
- **Total Phone QSOs** — Voice-mode (SSB, FM, AM) contact count
- **Total Digital QSOs** — Digital-mode (FT8, FT4, RTTY, PSK31, etc.) contact count
- **Total Distance** — Cumulative distance across all contacts with known grids (e.g., "Your signals traveled 142,000 km this month")
- **Operating Days** — Distinct UTC days with at least one QSO
- **Operating Hours** — Total time in active sessions (excludes gaps >15 min)
- **Active Bands** — Distinct bands used
- **Active Modes** — Distinct modes used
- **Unique Callsigns** — Distinct stations worked
- **QRP QSO Count** — Contacts at 5W or less
- **Milliwatt QSO Count** — Contacts at less than 1W

### Speed & Rate

- **Fastest 10 QSOs** — Shortest elapsed time to log 10 consecutive contacts in a single session (e.g., "10 QSOs in 8m 22s")
- **Peak 15-Minute Rate** — Highest QSO count in any 15-min sliding window, with projected hourly rate
- **Best Session Rate** — Highest avg QSOs/hr for any session with 10+ contacts (excludes idle gaps >15 min)
- **Fastest Activation** — Shortest time from 1st to 10th QSO in a POTA activation

### Distance

- **Furthest Contact** — Max distance QSO (from grid squares). Shows callsign, distance, band
- **Furthest Contact per Band** — Best DX on each band. Compact table: band → callsign → distance
- **Furthest QRP Contact** — Longest-distance QSO at 5W or less
- **Average Contact Distance** — Mean distance across contacts with known grids

### Power & Efficiency

- **Lowest Power Contact** — QSO at lowest transmit power. Shows watts, callsign, distance, band
- **Best Watts-per-Mile** — Lowest power÷distance ratio (e.g., "0.003 W/mi — 5W to JA1ABC at 5,400 mi on 20m")

### Geographic Reach

- **DXCC Entities** — Unique countries worked in the period
- **New DXCC Entities** — Countries worked for the first time ever (all-time firsts, even on weekly/monthly cards)
- **States & Provinces** — Unique US states and Canadian provinces
- **Grid Squares** — Unique Maidenhead grid squares worked
- **Continents** — Continents contacted (out of 6 inhabited)
- **Most Continents in a Day** — Best single UTC day for continent diversity
- **Worked All States Progress** — X/50 US states, shown as progress bar

### Volume Records

- **Most QSOs in a Day** — Best single UTC day by contact count
- **Most QSOs in a Session** — Largest single session
- **Most Countries in a Day** — Best single-day DXCC count
- **Most Bands in a Day** — Most distinct bands in a single UTC day

### Streaks

- **Current On-Air Streak** — Consecutive days with at least one QSO
- **Best On-Air Streak** — Longest streak in the period (or all-time)
- **Current Activation Streak** — Consecutive days with a POTA activation
- **Mode Streaks** — Longest streak for CW, Phone, and Digital individually

### POTA

- **Parks Activated** — Unique parks with valid activations (10+ QSOs)
- **Parks Hunted** — Unique parks contacted as hunter
- **Park-to-Park Contacts** — Total P2P QSOs
- **Largest N-fer** — Most parks activated simultaneously
- **Best Activation** — Activation with most QSOs. Shows park, date, count
- **New Parks** — Parks activated or hunted for the first time

### CW

- **Fastest CW Speed** — Highest WPM logged
- **CW Distance Record** — Furthest CW-mode contact
- **CW QRP Record** — Furthest CW contact at 5W or less

### Signal Quality

- **Perfect Reports** — Count of 599 (CW) or 59 (Phone) reports received
- **Average RST Received** — Mean signal report
- **Best RST at Distance** — Furthest contact with a perfect 59/599 report

### Fun & Unique

- **Earliest QSO of the Day** — Contact closest to 0000Z
- **Latest QSO of the Day** — Contact closest to 2359Z
- **Longest Session** — Duration of longest operating session
- **Most Active Day of the Week** — Day (Mon–Sun) with most contacts
- **Busiest Band** — Band with most QSOs
- **Busiest Mode** — Mode with most QSOs
- **Repeat Customers** — Station worked the most times (callsign + count)

## Professional Statistician Mode (Pro Stats)

Additional stats available when Professional Statistician Mode is enabled. Also individually toggleable.

### Charts & Visualizations

- **Band Distribution** — Pie/bar chart of QSOs by band, color-coded
- **Mode Distribution** — Pie/bar chart of QSOs by mode
- **QSO Rate Over Time** — Line graph: hourly bins (weekly), daily bins (monthly), weekly/monthly bins (all-time)
- **Distance Distribution Histogram** — Contact distances in range buckets
- **Distance CDF** — Cumulative distribution of contact distances
- **Timing CDF** — Cumulative distribution of inter-QSO timing
- **Daily Activity Bar Chart** — QSO count per day, color-coded by band/mode
- **Hour-of-Day Heatmap** — 24-column heatmap of UTC hour activity
- **Day-of-Week × Hour Heatmap** — 7×24 grid of operating patterns

### Statistical Summaries

- **Distance Box Plot** — Median, quartiles, outliers for distance
- **RST Box Plot** — Signal strength distribution, separate CW/Phone
- **Inter-QSO Timing Box Plot** — Pacing distribution
- **Distance Percentiles** — 25th, 50th, 75th, 90th, 99th percentile table
- **RST Distribution** — Histograms by R, S, T components
- **Band × Mode Matrix** — Cross-tabulation of QSO counts
- **Band × Distance Summary** — Per-band median/max distance and count
- **Power × Distance Scatter** — Scatter plot highlighting the efficiency frontier

### Derived Metrics

- **Median Contact Distance** — 50th percentile distance
- **Distance Standard Deviation** — Spread of contact distances
- **Operating Efficiency** — QSOs per operating hour across the period
- **Peak Hour** — Single UTC hour with most contacts
- **Peak Day** — Single UTC day with most contacts (with band/mode breakdown)
- **Band Diversity Index** — Shannon entropy of band distribution
- **Mode Diversity Index** — Shannon entropy of mode distribution
- **Geographic Spread** — Convex hull area (km²) of contacted grid squares
- **QSO Clustering Score** — How bursty vs. evenly spread your operating is

### Pro Stats Presets

- **Analyst** — Standard stats + charts (no box plots or derived metrics)
- **Full Statistician** — Everything enabled

## Card Layout

1. **Header** — Callsign, operator name, period label, branding
2. **Hero Stats Row** — 3–4 configurable large numbers
3. **Stats Body** — Enabled stats in order, grouped by category. Gold badge on all-time records set during the period
4. **Activity Visualization** — Weekly: 7-bar chart. Monthly: calendar heatmap. All-time: band/mode pie charts
5. **Map** (optional) — World map with contact arcs, RST color coding
6. **Footer** — Date generated, Carrier Wave logo

Card height adapts to stat count. 16:9 aspect ratio maintained.

## Settings (Settings → Brag Sheets)

### General

| Setting | Default |
|---------|---------|
| Include Map | On |
| Include Equipment Summary | Off |
| Gold Record Badges | On |
| Unit Preference | Follows app Units setting |

### Per-Period

Each tab (Weekly / Monthly / All Time):
- Enabled Stats — toggle on/off
- Stat Order — drag to reorder
- Hero Stats — star up to 4
- Apply Preset
- Reset to Default
