---
title: "Setting Up Carrier Wave"
description: "Configure your profile and connect services"
weight: 4
---

Let's get Carrier Wave ready for logging.

## Your Profile

On first launch, Carrier Wave walks you through onboarding. Enter your callsign and the app looks up your profile from HamDB.org, filling in your name, QTH, grid square, and license class automatically.

You can also set up your profile manually in **Settings** (the gear icon):

### Callsign

Enter your primary callsign. This is the callsign that will be logged as "your" call for every QSO.

If you have previous callsigns or operate under different calls (club calls, special event calls), you can add those as **Callsign Aliases** in Settings.

### Location (QTH)

Enter your city or general location. This helps when looking up your info from other services.

### Grid Square

Your {{< term "Grid Square" >}} is a location code based on the Maidenhead Locator System. If you granted location permission, Carrier Wave calculates this automatically.

Example: FN31 is the Boston area, CM87 is San Francisco.

### License Class

Select your license class (Technician, General, or Amateur Extra in the US). You can also tap the search icon to look up your license class from HamDB.org automatically. This helps with band plan validation — Carrier Wave can warn you if you try to log a contact on a frequency outside your privileges.

## Connecting Services

Scroll down to **Services** in Settings. Tap each service you want to connect:

### QRZ.com

1. Tap **QRZ.com**
2. Enter your QRZ username and password
3. Tap **Sign In**

Your credentials are stored securely in the iOS Keychain, not in the app's database. A QRZ XML Logbook Data subscription is required for callsign lookups.

### POTA

1. Tap **POTA**
2. Tap **Sign in with POTA**
3. Complete the OAuth flow in the web view
4. Return to the app

### Ham2K LoFi

1. Tap **Ham2K LoFi**
2. Enter your email address
3. Check your email for a device link
4. Tap the link to connect this device

### LoTW

1. Tap **LoTW**
2. Enter your LoTW username and password
3. Tap **Sign In**

Note: Carrier Wave downloads confirmations from LoTW but doesn't upload. Use ARRL's TQSL software to upload.

### Club Log

1. Tap **Club Log**
2. Enter your email, app password, callsign, and API key
3. Tap **Sign In**

Club Log provides bidirectional sync — your QSOs upload automatically and new data downloads during sync.

## Customize Your Tabs

In **Settings → Navigation**, you can show, hide, and reorder tabs. By default, Map and Activity are hidden but accessible from the More menu. On iPad, all tabs appear in the sidebar.

## What Syncs Where?

| Service | Uploads | Downloads |
|---------|---------|-----------|
| QRZ.com | ✓ QSOs | ✓ QSOs, Callsign info |
| POTA | ✓ Activations | ✗ |
| LoFi | ✓ QSOs | ✓ QSOs |
| LoTW | ✗ | ✓ Confirmations |
| Club Log | ✓ QSOs | ✓ QSOs |
| HAMRS | ✗ | ✓ QSOs |

## Start with One

Don't feel pressure to connect everything at once. Start with QRZ.com — it handles callsign lookups and gives you a cloud backup. Add other services as you need them.

## What's Next?

Your app is configured! Time to [log your first contact](/guide/first-contact/).
