---
title: "Logging Your First Contact"
description: "Step-by-step guide to recording a QSO"
weight: 5
---

You've set up the app. Now let's log a contact.

## Open the Logger

Tap the **Logger** tab at the bottom of the screen. You'll see the main logging interface.

## Start a Session

Tap the **Start Session** button. A wizard appears where you configure:

1. **Mode** — Select your operating mode (SSB, CW, FT8, etc.)
2. **Frequency** — Enter your operating frequency (optional — you can set it later)
3. **Activation type** — Choose Casual, POTA, or SOTA
4. **Equipment** — Select your radio, antenna, and other gear

You can save these as defaults for next time.

## Enter the Contact

Now you're ready to log:

### 1. Callsign

Tap the callsign field and enter the other station's call. As you type:
- Carrier Wave searches your callsign notes and QRZ for matching calls
- When found, their name, location, and grid appear in an info card
- A contact count badge shows if you've worked them before

### 2. RST Sent / RST Received

Enter the signal reports you exchanged:
- **RST Sent** — The report you gave them
- **RST Received** — The report they gave you

Fields start empty with placeholder hints (599 for CW, 59 for voice).

### 3. Optional Fields

Tap the chevron to expand additional fields:
- **State/Province** — Their state (often auto-filled from QRZ)
- **Park** — If they're a POTA activator, enter the park reference
- **Grid** — Their grid square
- **Notes** — Anything memorable about the contact

### 4. Log It

Tap **LOG** to save the contact.

That's it! Your contact is:
- Saved locally to your device
- Queued for sync to your connected services
- Visible in your Logs tab

The callsign field auto-focuses so you can immediately start entering the next contact.

{{< callout "tip" "Quick Entry" >}}
For rapid logging, type everything in one line: `K6TEST 599 CA` (callsign, RST, state). Color-coded tokens show how the input will be parsed.
{{< /callout >}}

## Watch It Sync

Switch to the **Dashboard** tab. You'll see your services listed with status indicators. Within a few seconds (depending on network conditions), your QSO syncs to the cloud.

## Duplicate Detection

If you log the same station twice on the same band and date, Carrier Wave blocks the duplicate and shows a warning. This prevents accidental double-logging.

Different band? Different date? No warning — those are valid separate contacts.

## What's Next?

Congratulations on your first logged QSO! Next, let's explore [your Dashboard](/guide/dashboard/) to understand your statistics.
