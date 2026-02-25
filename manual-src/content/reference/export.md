---
title: "Export & Sharing"
description: "ADIF export, brag sheets, and share cards"
weight: 15
showToc: true
---

## Overview

Carrier Wave provides multiple ways to export and share your logging data:

- **{{< term "ADIF" >}} file export** for importing into other logging software or online logbooks
- **Activation brag sheets** for sharing POTA activations as attractive image cards
- **Daily activity share cards** for sharing your day's operating summary
- **Summary cards** for individual sessions and activations

All export and sharing features integrate with the iOS share sheet, allowing you to send data via AirDrop, Messages, email, or save to Files and Photos.

## ADIF Export

### What is ADIF Export?

{{< term "ADIF" >}} (Amateur Data Interchange Format) is the standard format for exchanging amateur radio log data. Carrier Wave exports your QSOs as `.adi` files that can be imported into other logging applications or uploaded to online logbooks like QRZ, LoTW, and eQSL.

### Exporting ADIF Files

You can export ADIF files from:

- **Activation detail view** — Tap the share button in the toolbar to export that activation's QSOs
- **Sessions list** — Long-press or swipe on a session row to access the export option
- **Logging session manager** — Export the current session's QSOs

When you export an ADIF file:

1. Carrier Wave generates a properly formatted `.adi` file containing all QSOs for the selected session or activation
2. The iOS share sheet appears with options to:
   - **Share via AirDrop** to nearby devices
   - **Send via Messages or Mail**
   - **Save to Files** for later use
   - **Copy to clipboard** as text

### ADIF File Handling

Carrier Wave properly registers the ADIF UTType (`public.adi-file`) with iOS, ensuring that `.adi` files are recognized correctly when shared via AirDrop. Without this registration, some apps rename `.adi` files to `.txt`, causing import issues. Carrier Wave's implementation prevents this problem.

### What's Included in ADIF Exports

Each exported ADIF file includes:

- All QSO contact information (callsign, date, time, frequency, mode, RST)
- Station information (operator callsign, grid square, power)
- {{< term "POTA" >}} park references (for activations)
- {{< term "SOTA" >}} summit references (when applicable)
- Additional fields like comments and equipment notes

## Activation Brag Sheets

### What are Brag Sheets?

Brag sheets are shareable image cards that beautifully visualize your {{< term "POTA" >}} activations. They combine maps, statistics, and operating details into a single attractive image perfect for sharing on social media or with friends.

### Accessing Brag Sheets

You can generate a brag sheet by:

- **Swiping right** on any activation row in the {{< term "POTA" >}} activations list
- **Tapping the share button** in the activation detail view toolbar

### Brag Sheet Contents

Each brag sheet includes:

**Map Visualization**
- World map showing QSO locations
- Geodesic arcs connecting your location to each contact
- Colored dots based on {{< term "RST" >}} signal reports:
  - **Green** — Strong signals (S8-S9)
  - **Yellow** — Medium signals (S5-S7)
  - **Red** — Weak signals (S1-S4)

**Activation Details**
- Park reference (e.g., K-1234) and full park name
- Date of activation
- Total QSO count and activation duration
- Bands and modes used
- Equipment badges (antenna, key, mic) when enabled

**Operating Statistics**
- **Distance stats** — Average and maximum contact distance
- **Power output** — Transmitter power in watts
- **Watts per mile** — Efficiency metric (power/max distance)
- **Radio information** — Transceiver model and configuration
- **QSOs per hour** — Operating rate

**Timeline Visualization**
- QSO timeline bar showing when contacts were made
- Band-colored tick marks for each QSO
- Gap indicators showing breaks in operating

**Environmental Conditions**
- Solar conditions ({{< term "SFI" >}}, A-index, K-index) when available
- Weather conditions at activation time

**Branding**
- Carrier Wave logo and name
- Professional layout suitable for sharing

### Professional Statistician Mode

For operators who want deeper statistical analysis, enable **Professional Statistician Mode** in {{< term "POTA" >}} settings. This adds extended charts and statistics to both activation detail views and brag sheets.

#### Additional Charts and Visualizations

When Professional Statistician Mode is enabled, brag sheets include:

**Band Distribution Chart**
- Pie chart or bar graph showing QSO breakdown by band
- Helps visualize which bands were most productive

**QSO Rate Over Time**
- Line graph showing contacts per hour throughout the activation
- Identifies peak operating periods

**Cumulative Distance CDF Chart**
- Cumulative distribution function showing distance coverage
- Demonstrates how quickly you reached various distance milestones

**Cumulative Timing CDF Chart**
- Shows how QSOs accumulated over time during the activation
- Useful for analyzing operating efficiency

**RST Statistics**
- Statistics bucketed by R (readability), S (signal strength), and T (tone)
- Separate analysis for each component of signal reports
- Histograms showing distribution of each metric

**Distance and Timing Box Plots**
- Box-and-whisker plots showing statistical distribution
- Median, quartiles, and outliers clearly visualized

**Additional Metrics**
- **Entity counts** — Number of unique {{< term "DXCC" >}} entities worked
- **Peak rate badges** — "Best 15-min" highlighting your fastest operating period
- **Band/mode distributions** — Detailed breakdowns of operating patterns
- **Modes used** — List of all operating modes during the activation

These extended statistics provide deep insights into your activation's performance and help identify patterns for improving future operations.

### Equipment Badges

By default, Carrier Wave includes equipment badges on brag sheets showing:

- **Antenna** — The antenna(s) used during the activation
- **Key/Paddle** — For {{< term "CW" >}} operations
- **Microphone** — For voice operations
- **Extra Equipment** — Additional gear like tuners, amplifiers, batteries

You can control this behavior in {{< term "POTA" >}} settings with the **"Include Equipment on Brag Sheet"** toggle (enabled by default). Disabling this option creates cleaner brag sheets focused purely on operating statistics.

## Daily Activity Share Cards

### What are Activity Share Cards?

Daily activity share cards provide a quick summary of your operating day, including:

- Total QSOs logged
- Bands and modes used
- Activations completed
- Notable contacts or achievements

### Creating Activity Share Cards

From the Activity Log view:

1. Find the day you want to share in the daily summary
2. Tap the **share button** next to that day's entry
3. Carrier Wave generates a branded card with your day's statistics
4. Use the iOS share sheet to send it via your preferred method

Activity share cards use the same ShareCardContent template as other share features, maintaining consistent branding and layout.

## Share Preview and Photos

### Share Card Preview

When generating any share card (brag sheet, activity card, or summary), Carrier Wave presents a rich preview sheet showing:

- The generated card image
- A **ShareLink** button that opens the iOS share sheet with a proper thumbnail
- A **Save to Photos** button for quick saving to your device

This preview allows you to review the card before sharing and ensures the iOS share sheet displays a proper thumbnail image instead of a generic file icon.

### Saving to Photos

The **Save to Photos** button provides one-tap saving to your device's photo library. This is useful for:

- Building a collection of your activation memories
- Archiving statistical summaries
- Sharing later without regenerating the card

## Tips for Effective Sharing

### Brag Sheet Best Practices

- **Enable Professional Statistician Mode** if you want to showcase detailed analysis
- **Include equipment badges** to share your field setup with others
- **Wait until activation is complete** to ensure all statistics are accurate
- **Check the preview** before sharing to verify all information is correct

### ADIF Export Best Practices

- **Export regularly** to maintain backups of your log data
- **Use consistent filenames** when saving to Files for easy organization
- **Verify import** after uploading to online logbooks to ensure all QSOs transferred correctly

### Social Media Sharing

Carrier Wave's share cards are designed to look great on social media platforms:

- The 16:9 aspect ratio works well on most platforms
- Carrier Wave branding is subtle but professional
- Maps and statistics are easy to read at various sizes
- Colors use high contrast for accessibility

## See Also

- [Period Brag Sheets](/reference/brag-sheets/) — Configurable weekly, monthly, and all-time stats cards
- [POTA (Parks on the Air)](/reference/pota/) — Learn about POTA activations and how they integrate with brag sheets
- [Activity Log](/reference/activity-log/) — Understand how daily activity is tracked and shared
- [Logs & Search](/reference/logs-search/) - Browse sessions and QSO history
- [Settings](/reference/settings/) — Configure POTA settings including Professional Statistician Mode and equipment badges
