---
title: "Troubleshooting"
description: "Common issues, sync logs, and bug reporting"
weight: 12
showToc: true
---

This section helps diagnose and resolve common issues with Carrier Wave.

## Sync Issues

### QSOs Not Uploading

**Symptoms:** QSOs show "pending" status, never sync.

**Check:**
1. Network connectivity - try other apps
2. Service authentication - re-sign in if needed
3. Sync logs for specific errors

**Common causes:**
- Expired credentials
- Service temporarily down
- Rate limiting (wait and retry)

### QSOs Not Downloading

**Symptoms:** Contacts logged elsewhere don't appear.

**Check:**
1. Service supports downloads (POTA is upload-only)
2. Time since last sync
3. Manual sync trigger (pull to refresh)

### Sync Conflicts

**Symptoms:** Duplicate QSOs, mismatched data.

**Resolution:**
1. Let sync complete fully
2. Manually delete duplicates if needed
3. The most recent data usually wins

## Authentication Issues

### "Invalid Credentials" Error

**For username/password services (QRZ, LoTW):**
1. Verify credentials on the service's website
2. Check for special characters that might need escaping
3. Re-enter credentials in Carrier Wave

**For OAuth services (POTA, HAMRS):**
1. Tap "Sign Out"
2. Sign in again via the web flow
3. Complete the OAuth authorization

### "Session Expired"

OAuth tokens expire. When prompted:
1. Tap to re-authenticate
2. Complete the sign-in flow
3. Sync resumes automatically

## App Performance

### Slow Dashboard

**Cause:** Large QSO database, statistics computing.

**Mitigation:**
- Statistics compute in background
- Wait for progress indicator to complete
- Consider archiving very old QSOs

### Battery Drain

**Cause:** Frequent sync, GPS updates.

**Check:**
1. Reduce sync frequency in Settings
2. Disable location services when not needed
3. Background App Refresh settings

## Viewing Sync Logs

For detailed sync troubleshooting:

1. Go to **Settings > Advanced > Sync Debugging**
2. Enable verbose logging
3. Reproduce the issue
4. View logs showing:
   - API requests and responses
   - Error messages
   - Timing information

Logs can be exported for support.

## Submitting Bug Reports

When you encounter a bug:

1. Go to **Settings > Bug Report**
2. Describe the issue
3. Tap **Generate Report**

The report includes:
- Device model and iOS version
- App version
- Recent error logs
- Database statistics (no personal QSO data)

**Not included:** Your actual QSO data, credentials, or personal information.

Reports can be:
- Emailed to support
- Copied to clipboard
- Saved to Files

## Common Error Messages

| Error | Meaning | Resolution |
|-------|---------|------------|
| "Network unavailable" | No internet connection | Check WiFi/cellular |
| "Authentication failed" | Bad credentials | Re-enter password |
| "Rate limited" | Too many requests | Wait, then retry |
| "Server error" | Service-side issue | Try again later |
| "Invalid ADIF" | Malformed upload data | Check QSO fields |

## Data Recovery

### Accidental Deletion

Deleted QSOs are NOT recoverable from the app. However:
- If synced to cloud services, data exists there
- iCloud backup may contain older data
- Re-download from LoFi or QRZ

### Database Corruption

Rare, but if the app won't open:
1. Try force-quitting and reopening
2. Restart device
3. Reinstall app (synced data re-downloads)
4. Restore from iCloud backup as last resort

## Getting Help

If troubleshooting doesn't resolve your issue:

1. Check for app updates
2. Search existing bug reports
3. Submit detailed bug report with logs
4. Contact support with report reference

## See Also

- [Settings & Services](/reference/settings/) - Service configuration
- [Service Sync Flow](/reference/sync-flow/) - How sync works
- [iCloud Sync](/reference/icloud/) - Device sync issues
