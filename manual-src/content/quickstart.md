---
title: "Quick Start"
description: "Get logging in 5 minutes"
weight: 1
---

You've used loggers before. Here's how to get on the air with Carrier Wave.

## Download & First Launch

[Download Carrier Wave from the App Store](https://apps.apple.com/app/carrier-wave). On first launch, the app walks you through an onboarding flow:

1. Enter your callsign — Carrier Wave looks up your profile from HamDB
2. Connect your services (QRZ, POTA, LoFi, LoTW, Club Log)
3. Optionally enable community features (friends, challenges, activity feed)

The app asks for location permission to automatically determine your {{< term "Grid Square" >}}.

## Connect Your Services

Open **Settings** (gear icon) and scroll to **Services**. Connect at least one:

| Service | What it does |
|---------|--------------|
| **QRZ.com** | General logbook, callsign lookups |
| **POTA** | Park activation uploads |
| **Ham2K LoFi** | Cross-device sync |
| **LoTW** | Confirmation downloads |
| **Club Log** | Bidirectional logbook sync |
| **HAMRS** | HAMRS cloud sync |

Start with QRZ — enter your username and password. The app stores credentials securely in the iOS Keychain.

## Log Your First QSO

1. Tap the **Logger** tab
2. Tap **Start Session** and set your mode, frequency, and activation type
3. Enter the callsign — QRZ lookup happens automatically
4. Enter RST sent/received
5. Tap **LOG**

That's it. Your {{< term "QSO" >}} is logged locally and queued for sync.

{{< callout "tip" "Quick Entry Mode" >}}
For rapid logging, type everything in one line:
`K6TEST 599 CA` (callsign, RST, state) or `AJ7CM 579 WA US-0189` (callsign, RST, state, park)
{{< /callout >}}

## Verify Sync

Check the **Dashboard** tab. Service status indicators show:

- **Green**: Synced and current
- **Yellow**: Sync in progress
- **Red**: Sync error (tap for details)

If you see issues, check [Troubleshooting](/reference/troubleshooting/).

## What's Next

- [POTA Activations](/reference/pota/) — Upload your park contacts, try rove mode
- [Activity Log](/reference/activity-log/) — Track daily QSOs as a hunter without starting sessions
- [Map View](/reference/map/) — See your contacts on a world map
- [WebSDR](/reference/websdr/) — Listen to your signal from a remote receiver
- [Widgets](/reference/widgets/) — Add solar conditions, spots, and stats to your home screen
- [Search & Filters](/reference/logs-search/) — Query your log history with a powerful query language

For deeper understanding of logging concepts, see the [Beginner's Guide](/guide/).

For complete documentation of every feature, see the [Reference Manual](/reference/).
