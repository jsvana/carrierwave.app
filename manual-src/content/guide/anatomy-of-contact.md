---
title: "The Anatomy of a Contact"
description: "What information makes up a QSO"
weight: 2
---

Every {{< term "QSO" >}} consists of essential information that both stations exchange and record.

## The Basics

### Callsigns

Every contact involves two {{< term "Callsign" >}}s - yours and theirs. Your callsign identifies you; theirs identifies the station you're talking to.

Callsigns follow patterns based on country. US callsigns start with W, K, N, or AA-AL. Canadian calls start with VE. Japanese calls start with JA.

### Date and Time

Contacts are always logged in {{< term "UTC" >}} (Coordinated Universal Time), not your local time zone. This prevents confusion when stations in different time zones log the same contact.

Carrier Wave automatically records the current UTC time when you save a QSO.

### Frequency and Band

The {{< term "Band" >}} tells you which part of the radio spectrum you're using. Common bands include:

- **HF**: 80m, 40m, 20m, 15m, 10m (long-distance)
- **VHF**: 6m, 2m (regional)
- **UHF**: 70cm (local)

The frequency is more specific - for example, 14.250 MHz on the 20 meter band.

### Mode

The {{< term "Mode" >}} describes how you're communicating:

- **SSB** (Single Sideband) - Voice on HF
- **FM** - Voice on VHF/UHF
- **CW** - Morse code
- **FT8** - Digital weak-signal mode
- **FM** - Voice on VHF/UHF repeaters

## Signal Reports (RST)

During every contact, stations exchange signal reports using the {{< term "RST" >}} system:

- **R** (Readability): 1-5, how clearly you can understand them
- **S** (Signal Strength): 1-9, how strong their signal is
- **T** (Tone): 1-9, quality of their CW tone (only used for Morse)

A typical voice report is "59" (perfectly readable, very strong). A CW report might be "599" (perfect readability, strong signal, pure tone).

{{< callout "note" "The 59 Convention" >}}
In contests and casual contacts, many operators simply exchange "59" regardless of actual signal quality. This speeds up contacts but isn't technically accurate. For more meaningful reports, listen carefully and report what you actually hear.
{{< /callout >}}

## Optional Information

Beyond the basics, you might also log:

- **Name** - The operator's name
- **QTH** - Their location (city, state, country)
- **Grid Square** - A precise location code
- **Notes** - Anything memorable about the contact
- **Park Reference** - For POTA activations

## What's Next?

Now that you know what goes in a log entry, let's explore [why you might want to sync your log to the cloud](/guide/why-cloud/).
