---
title: "iCloud Sync"
description: "Cross-device synchronization via iCloud"
weight: 7
showToc: true
---

iCloud Sync keeps your Carrier Wave data synchronized across all your Apple devices.

## What Syncs

### Synced via iCloud

- **QSO database** - All your logged contacts
- **App settings** - Preferences and configuration
- **Callsign notes** - Custom notes files

### Not Synced

- **Service credentials** - Stored in device Keychain (you'll need to sign in on each device)
- **Cached data** - Callsign lookups, temporary files

## Enabling iCloud Sync

1. Open **Settings**
2. Scroll to **iCloud**
3. Toggle **Enable iCloud Sync**

Requirements:
- Signed into iCloud on your device
- Carrier Wave enabled in iCloud settings

## How It Works

Carrier Wave uses CloudKit to sync data:

1. **Local changes** are pushed to iCloud
2. **Remote changes** are pulled when detected
3. **Merge** combines changes from multiple devices

Sync happens automatically in the background.

## Multi-Device Scenarios

### Logging on iPhone, Viewing on iPad

1. Log QSOs on your iPhone in the field
2. Open Carrier Wave on your iPad at home
3. QSOs appear automatically (may take a few moments)

### Simultaneous Logging

If you log on two devices simultaneously:
- Both QSOs are kept (no data loss)
- Duplicates may occur if logging the same contact on both

## Conflict Resolution

When the same record is modified on multiple devices:

- **QSOs:** Both versions kept if different; merged if compatible
- **Settings:** Most recent change wins

## Troubleshooting

### Sync Not Working

1. Verify iCloud is enabled in iOS Settings
2. Check Carrier Wave is enabled in iCloud settings
3. Ensure network connectivity
4. Pull to refresh in the app

### Data Not Appearing

iCloud sync can take time, especially:
- First sync with large databases
- Poor network conditions
- iCloud service issues

Check Apple's System Status page for iCloud outages.

### Duplicate QSOs

If duplicates appear after sync:
1. Check if logged on multiple devices
2. Use Logs search to find duplicates
3. Delete extras manually

## Storage

iCloud data counts against your iCloud storage quota. A typical ham's log uses minimal space (a few MB for thousands of QSOs).

## Privacy

Your QSO data is stored in your private iCloud container:
- Only accessible by your Apple ID
- Encrypted in transit and at rest
- Not shared with Apple or third parties

## Disabling Sync

To stop syncing:

1. Open **Settings**
2. Toggle off **Enable iCloud Sync**

Data remains on each device but no longer synchronizes.

**Warning:** Disabling sync doesn't delete data from iCloud. To fully remove, delete the app data in iOS Settings > [Your Name] > iCloud > Manage Storage.

## See Also

- [Settings & Services](/reference/settings/) - Other configuration options
- [Service Sync Flow](/reference/sync-flow/) - Cloud service sync
- [Troubleshooting](/reference/troubleshooting/) - Common issues
