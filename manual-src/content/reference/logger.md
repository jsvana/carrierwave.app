---
title: "Logger"
description: "QSO entry, session management, commands, and logging features"
weight: 1
showToc: true
---

The Logger is Carrier Wave's primary interface for recording contacts. It provides rapid {{< term "QSO" >}} entry, session management, real-time callsign lookup, and a comprehensive command system for controlling your operating session.

## Starting a Session

### Session Start Wizard

When you start a new session, the wizard guides you through:

**Basic Parameters:**
- **Mode** - {{< term "CW" >}}, {{< term "SSB" >}}, {{< term "FT8" >}}, FM, AM, FT4, {{< term "RTTY" >}}, PSK31, DATA
- **Frequency** - Operating frequency in MHz (optional - supports hunt-first flow)
- **Activation Type** - Casual, {{< term "POTA" >}}, {{< term "SOTA" >}}

**Equipment:**
- **Radio/Rig** - Select from user-managed radio list
- **Antenna** - Current antenna in use
- **CW Key** - For Morse code operations
- **Microphone** - For voice modes
- **Power** - Transmit power in watts (US max: 1,500W)

**Additional Fields:**
- **Attendees** - Who's operating (for multi-operator sessions)
- **Photos** - Session photos
- **Notes** - Session-level notes

**Activation Details:**

When operating {{< term "POTA" >}} or {{< term "SOTA" >}}:
- **Park Reference** - Supports multi-park n-fer operations with removable chips
- Search parks by name/reference or find nearby parks using GPS
- Number shorthand: typing "1234" expands to "US-1234"

**Portable Callsign:**

Configure callsign prefix/suffix for portable operations:
- Prefix: `I/W6JSV` (international)
- Suffix: `/P` (portable), `/M` (mobile), `/MM` (maritime mobile), `/AM` (aeronautical mobile), or custom

**Wizard Options:**

- **Save as Defaults** - Remember these settings for next time
- **Skip wizard next time** - Jump straight to logging with saved defaults

### Hunt-First Flow

Frequency is **not required** at session start. If you're hunting before activating, start the session without a frequency and set it later using the `BAND` command or by typing a frequency in the callsign field.

### Active Sessions

Only one session can be active at a time. Starting a new session automatically pauses the previous one.

**Session Actions:**
- **Continue** - Resume a paused session (makes it active)
- **Finish** - End a paused session permanently

## Callsign Entry

### Callsign Field

The primary entry field with auto-lookup:

1. **Polo Notes First** - Checks your saved callsign notes for nickname/emoji
2. **QRZ Lookup** - Queries QRZ.com for name, QTH, {{< term "Grid Square" >}}, license class

### Callsign Info Card

When a callsign is recognized, the info card displays:
- **Name** - Operator name
- **QTH** - Location
- **Grid Square** - Maidenhead locator
- **License Class** - For privilege validation
- **Callsign Notes Emoji** - Visual identifier from your saved notes

### Contact Count Badges

Badges indicate how many previous {{< term "QSO" >}}s you've had with this station:
- **Bronze** - 10+ contacts
- **Silver** - 25+ contacts
- **Gold** - 50+ contacts

### Auto-Focus

After logging a {{< term "QSO" >}}, the callsign field automatically regains focus for rapid sequential entries.

### Tap-to-Edit

Tap any logged callsign in the session log to bring it back into the entry fields for correction.

## Quick Entry

Type complete {{< term "QSO" >}}s in a single line for rapid logging:

```
AJ7CM 579 WA US-0189
```

### Parsing Rules

- **RST** - {{< term "RST" >}} reports (single value → both sent/received; two consecutive → sent/received)
- **Grid Square** - 4- or 6-character Maidenhead locators
- **State/Province** - US states, Canadian provinces
- **Park References** - {{< term "POTA" >}} refs (US-0189, K-1234, VE-0100)
- **Notes** - Unrecognized tokens become notes (multi-word notes combine into single badge)

### Token Preview

As you type, color-coded badges show how each component will be parsed. This gives immediate feedback before logging.

**Example:**
```
K6ABC 599 DM13 CA
```
Shows: `K6ABC` (callsign) `599` (RST) `DM13` (grid) `CA` (state)

## QSO Fields

### RST Sent / RST Received

Signal reports exchanged during the contact.

**Defaults:**
- Voice modes ({{< term "SSB" >}}, FM, AM): `59`
- {{< term "CW" >}} and digital modes: `599`
- Fields start empty with placeholder hints showing the default

### State/Province

US state or Canadian province. Auto-filled from QRZ when available.

**Manual Override:** You can override the auto-filled value if the operator gives you a different location (common during portable operations).

### Grid Square

Maidenhead {{< term "Grid Square" >}} locator (4 or 6 characters).

### Park Reference

For {{< term "POTA" >}} contacts:
- Supports multiple park references (activator operating from multiple parks)
- Chip-based UI with removable badges
- Search picker with nearby parks from GPS
- Number shorthand: `1234` → `US-1234`

### Operator

Individual operator's callsign if different from the station callsign (e.g., guest operators at club stations).

**Placeholder Hint:** Shows QRZ name as placeholder when field is empty.

### Notes

Free-form text for memorable details about the contact.

### Field Visibility

**Always-Visible Fields:** Configure in Settings → Logger which fields appear without expanding.

**More Chevron:** Tap to expand additional fields when needed.

## Commands

Type commands in the callsign field to control your session:

### Frequency & Band

| Command | Description |
|---------|-------------|
| `14.060` | Set frequency (supports kHz, MHz, with optional unit suffix) |
| `14.030.50` | Sub-kHz precision (dot-separated format) |
| `BAND` | Open band picker with live spots and clear-frequency recommendations |

### Mode

| Command | Description |
|---------|-------------|
| `MODE CW` | Switch to specified mode |
| `CW` | Bare mode name also works (CW, SSB, FT8, FM, etc.) |

### Spotting

| Command | Description |
|---------|-------------|
| `SPOT` | Post {{< term "POTA" >}} self-spot |
| `SPOT QRT` | Post spot with "QRT" comment |
| `SPOT QSY 14.062` | Post spot with custom comment |

### Spot Monitoring

| Command | Description |
|---------|-------------|
| `RBN` | Show your {{< term "RBN" >}} and {{< term "POTA" >}} spots |
| `RBN K6ABC` | Show spots for any callsign |
| `POTA` | Show active {{< term "POTA" >}} spots panel with band/mode filters |
| `P2P` | Find park-to-park opportunities via nearby {{< term "RBN" >}} skimmers |

### Conditions & Tools

| Command | Description |
|---------|-------------|
| `SOLAR` | Show solar conditions (K-index, SFI, propagation) |
| `WEATHER` | Show weather conditions from NOAA |
| `MAP` | Show session {{< term "QSO" >}}s on a map |
| `WEBSDR` | Open WebSDR receiver picker or connect to last receiver |

### Session Management

| Command | Description |
|---------|-------------|
| `NOTE <text>` | Add timestamped note to session log |
| `RIG` | Edit equipment (radio, antenna, key, mic) during active session |
| `HIDDEN` | View and restore deleted {{< term "QSO" >}}s from current session |

**Alias:** `DELETED` also opens hidden {{< term "QSO" >}}s.

### External Resources

| Command | Description |
|---------|-------------|
| `CHECKLIST` | Deep link to CW Field Guide outing checklists (passes session radio) |
| `MANUAL` | Open CW Field Guide radio manual for current radio |

**Alias:** `CL` for `CHECKLIST`.

## Band Plan Validation

### License Privilege Checking

If you've set your license class in Settings (Tech, General, Extra), Carrier Wave validates:
- **Frequency Privileges** - Warns when operating outside your license allocations
- **Mode Restrictions** - Alerts for {{< term "CW" >}}-only vs voice segments

### Warning Banner

The unified frequency warning banner shows:
- License violations (out-of-privilege operation)
- Mode violations (e.g., voice in {{< term "CW" >}}-only segment)

**Note:** Warnings don't prevent logging. You may be logging someone else's {{< term "QSO" >}}s or operating under a different license.

### Sub-kHz Precision

Supports frequencies like `14.03050` or dot-separated format `14.030.50` for precise logging.

## Frequency Activity

### RBN Monitoring

Monitors {{< term "RBN" >}} activity within ±2kHz of your frequency:
- **QRM Assessment** - Alerts when other stations are operating nearby
- **Operator Nearby** - Suppressed when the nearby spot is the station you're working

### Unified Warning Banner

Combines license violations and frequency activity warnings in a single banner for clarity.

## Auto Mode Detection

When you change frequency, Carrier Wave automatically switches to the appropriate mode:
- {{< term "CW" >}} segments → CW mode
- DATA segments → FT8/digital mode
- Phone segments → {{< term "SSB" >}} mode

**Toggle:** Enable/disable in Settings.

## Duplicate Detection

### Same-Band Duplicates

{{< term "QSO" >}}s with the same callsign, same band, same UTC date are blocked:
- **Log Button Disabled** - Cannot save duplicate
- **Warning Banner** - Explains why the contact is flagged

### Different-Band Contacts

Contacts with the same callsign on a different band or date are **highlighted green**:
- Indicates you've worked this station before
- Confirms this is a valid new contact (different band/date)

### POTA Rove Duplicate Detection

During {{< term "POTA" >}} rove sessions, duplicates are detected **per park stop**. You can work the same station from multiple parks in the same session.

## Session Log

### Recent QSOs

The session log shows recent contacts filtered by the current session:

- **UTC Times** - Displayed with "Z" suffix (e.g., 18:45Z)
- **Contact Info** - Nickname and callsign notes emoji
- **Total Count** - Number of contacts per row

### Swipe-to-Delete

Swipe left on any {{< term "QSO" >}} to delete:
- Requires confirmation dialog
- Use `HIDDEN` command to view and restore deleted contacts

## Keyboard Customization

### Number Row

Persistent row above keyboard with:
- Digits 0-9
- Decimal point
- Configurable symbols

### Command Row

Configurable buttons for frequently-used commands. Customize in Settings → Logger.

### Dismiss Button

Quickly dismiss the keyboard when needed.

## Equipment Tracking

### Session Equipment

Equipment propagated to all {{< term "QSO" >}}s logged during the session:
- Radio/rig
- Antenna
- {{< term "CW" >}} key
- Microphone
- Custom equipment

### Equipment Capsule

Tappable capsule in the session header shows current equipment. Use `RIG` command to edit equipment during an active session.

### ADIF Export

Equipment is exported as `MY_RIG` in ADIF files for compatibility with other logging software.

## Session Management

### Session Header

Shows:
- **Session Title** - Tap to customize
- **Duration** - Time elapsed since session start
- **QSO Count** - Total contacts in session

### End Session

**Active Session:**
- Red "End Session" button
- Auto-navigates to Logs tab when ended (if session has {{< term "QSO" >}}s)

**No Active Session:**
- Green "Start Session" button

### Delete Session

Hides all {{< term "QSO" >}}s and cleans up spots and photos.

**Confirmation Required:** Type "delete" to confirm (prevents accidental deletion).

### Keep Screen On

Enable in Settings → Logger to prevent device sleep during active sessions.

## iPad Layout

### Two-Pane Layout

On iPad with regular width:
- **Left Pane** - Logger with {{< term "QSO" >}} entry
- **Right Pane** - Persistent spots sidebar ({{< term "POTA" >}}, {{< term "RBN" >}}/My Spots, P2P tabs)

### Compact Width

On compact width (iPhone or iPad split view), the sidebar is hidden and the Logger uses the full width.

### Sidebar Toggle

NavigationSplitView sidebar toggle visible on Logger tab for manual control.

## Toast Notifications

### Success Feedback

Toast messages appear for:
- {{< term "QSO" >}} logged successfully
- Spot posted
- Command executed
- Friend spotted alerts

### Haptic Feedback

Success haptic (gentle bump) when logging a {{< term "QSO" >}}.

## See Also

- [POTA Activations](/reference/pota/) - Activation tracking and park management
- [Spot Monitoring](/reference/spots/) - {{< term "RBN" >}}, {{< term "POTA" >}}, and P2P spots
- [Activity Log](/reference/activity-log/) - Daily QSO tracking for hunters
- [Map View](/reference/map/) - Visualize contacts geographically
- [WebSDR Integration](/reference/websdr/) - Remote receiver access
- [Settings & Services](/reference/settings/) - Configure Logger behavior
