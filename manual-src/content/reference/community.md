---
title: "Community & Activity"
description: "Friends, clubs, activity feed, challenges, and social features"
weight: 10
showToc: true
---

Carrier Wave's community features let you connect with friends, join clubs, track achievements, and compete in challenges.

## Community Account

Community features are opt-in and require registration with the activities server.

### Initial Registration

During onboarding, you can choose to enable community features. This registers your {{< term "callsign" >}} with the activities server and creates a community account.

Existing users see a one-time prompt when visiting the Activity tab. You can accept or decline community features.

### Enabling Later

If you skipped community setup:

1. Go to **Settings** → **Activities**
2. Toggle **Enable community features** on

The app automatically registers your account using your station {{< term "callsign" >}} from Logger settings.

### Privacy Controls

The **Enable community features** toggle in Settings → Activities controls your discoverability:

- **On** - Your {{< term "callsign" >}} appears in friend search and you can participate in challenges and clubs
- **Off** - You remain hidden from search but retain your local data

### Account Deletion

To permanently delete your community account:

1. Go to **Settings** → **Activities**
2. Scroll to **Delete Community Account**
3. Confirm deletion

This removes all your community data from the server, including challenge progress, friends, and activity history. The deletion cascades to all related records. This action cannot be undone.

## Friends

Connect with other Carrier Wave users to see their activity in your feed.

### Friends List

The Friends list shows:

- **Accepted friends** - People you're connected with, sorted by {{< term "callsign" >}}
- **Pending requests** - Incoming friend requests you can accept or decline
- **Sent requests** - Outgoing requests awaiting acceptance
- **Suggestions** - Recommended friends based on shared contacts

Access the list from the Activity tab toolbar (person icon with badge showing pending count).

### Sending Friend Requests

**By callsign search:**

1. Tap the **Friends** icon in the Activity tab toolbar
2. Tap the **+** button
3. Enter the {{< term "callsign" >}} to search
4. Tap **Send Request**

**By invite link:**

1. Open Friends list
2. Tap the menu button (three dots)
3. Select **Invite Friend**
4. Share the link via iOS share sheet or copy to clipboard
5. The recipient taps the link and sends a request

Invite links expire after 7 days.

### Accepting and Declining Requests

Incoming requests appear in the Friends list with **Accept** and **Decline** buttons. The pending count badge appears on the Activity tab icon and the Friends toolbar button.

A banner card also appears in the Activity feed linking to the Friends list when you have pending requests.

### Friend Profiles

Tap any {{< term "callsign" >}} in the Activity feed to view a friend's profile. Profiles show:

- Recent activity from that user
- Total activities count
- Activities this week
- Friendship start date (when you became friends)

### Removing Friends

Swipe left on a friend in the Friends list and tap **Delete**, or use the Edit button.

## Friend Suggestions

Carrier Wave suggests friends based on shared contacts:

- {{< term "callsign" >}}s with 3+ QSOs in your log who are Carrier Wave users appear as suggestions
- Suggestions appear in a dedicated section of the Friends list
- **Add** sends a friend request
- **Dismiss** hides the suggestion permanently

The app validates suggestions against the server in batches for efficiency.

## Clubs

Clubs are groups based on Ham2K Polo notes lists. You're automatically a member of clubs that include your {{< term "callsign" >}}.

### Clubs List

The Clubs list (accessed from the Activity tab toolbar, three-person icon) shows:

- Club name
- Member count

Tap a club to view details.

### Club Details

The club detail view shows:

- Full member list with {{< term "callsign" >}}s
- Club description (if available)

### Membership

Club membership is determined by Polo notes lists configured on the activities server. Contact a club admin to add your {{< term "callsign" >}} to the list.

## Activity Feed

The Activity feed displays notable achievements from you and your friends.

### Feed Content

The feed automatically detects and displays:

- **New DXCC entities** - First contact with a new {{< term "DXCC" >}} country
- **New bands worked** - First {{< term "QSO" >}} on a band
- **New modes** - First contact on a {{< term "mode" >}}
- **DX contacts** - Contacts over 5,000 km
- **Logging streaks** - 7, 14, 30, 60, 90, 100, 180, or 365 day milestones
- **POTA activations** - Completed activations (10+ QSOs)
- **Parks worked milestones** - Accumulating unique {{< term "POTA" >}} parks
- **Friend activities** - Notable achievements from accepted friends
- **Worked Friend** events - When you log a {{< term "QSO" >}} with an accepted friend

### Activity Detection

Detection runs automatically when you:

- Log a new {{< term "QSO" >}} during a session
- Complete a sync that downloads QSOs from {{< term "QRZ" >}}, {{< term "POTA" >}}, {{< term "LoFi" >}}, {{< term "LoTW" >}}, Club Log, or HAMRS

The detector analyzes recent QSOs in the background (capped at the 10,000 most recent for performance) and adds notable events to your feed.

### Feed Filters

Use the filter bar to focus the feed:

- **All** - Everything from everyone (you and friends)
- **Friends** - Only activities from accepted friends
- **Clubs** - Only activities from club members

Active filters show as highlighted chips. Tap a chip to toggle the filter.

### Feed Refresh

The feed auto-refreshes:

- Immediately when the Activity tab appears
- Every 60 seconds while the tab is visible
- When you tap the refresh button in the toolbar

## Challenges

Challenges are community events that encourage specific types of operating activity.

### Browsing Challenges

Open the **Activity** tab to see:

- **Active challenges** - Challenges you're currently participating in
- **Browse** button - View available challenges you can join
- **Completed** - Finished challenges with your final standing

### Challenge Types

Challenges vary in their goals:

- **QSO count** - Log a specific number of contacts in a time period
- **Band** - Work specific bands
- **Mode** - Focus on {{< term "CW" >}}, digital, phone, etc.
- **Geographic** - Work specific states, countries, or {{< term "grid square" >}}s
- **POTA** - Activate or hunt parks

### Joining Challenges

1. Tap **Browse** in the Challenges section
2. Tap a challenge to preview rules and requirements
3. Tap **Join** to participate

Existing QSOs may count retroactively if they meet the challenge criteria and fall within the challenge time window.

### Challenge Rules

Each challenge defines:

- **Start and end dates** - The time window when QSOs count
- **Qualifying criteria** - What makes a {{< term "QSO" >}} eligible (band, {{< term "mode" >}}, location, etc.)
- **Scoring** - How points are calculated
- **Categories** - Different entry classes (if applicable)

Read the rules carefully before joining. Not all QSOs may count toward the challenge.

### Progress Tracking

Once joined, the challenge card shows:

- Current progress (QSOs, points, or custom metric)
- Goal and completion percentage
- Time remaining
- Your rank among participants

Progress updates automatically as you log contacts. No special logging mode is required - just log QSOs normally.

### Leaderboards

Each challenge has a leaderboard showing:

- Top participants
- Your current rank
- Points or {{< term "QSO" >}} counts for each entry

Leaderboards refresh periodically as participants log contacts.

### Challenge History

Completed challenges remain visible with:

- Your final standing and rank
- Qualifying QSOs that counted
- Completion date

### Leaving Challenges

To leave an active challenge:

1. Open the challenge detail view
2. Tap the menu button (three dots)
3. Select **Leave Challenge**
4. Confirm

Your progress is removed from the leaderboard but local data remains.

## Sharing

Share achievements as branded image cards:

1. Tap the share icon on an activity item (or use the toolbar share button)
2. Choose **Share Summary** to generate a custom card
3. Post the image to social media or save it

Share cards include:

- Achievement details
- Your {{< term "callsign" >}}
- Carrier Wave branding

## Activity Servers

Community features are provided by activity servers. The official server is `https://activities.carrierwave.app`.

### Adding Servers

To add a community-run server:

1. Go to **Settings** → **Activities**
2. Scroll to **Activity Servers**
3. Tap **Add Server**
4. Enter the server URL and display name

Multiple servers can be configured. Challenges from all servers appear in the Activity tab.

### Server Status

The Activities settings screen shows:

- Server URL
- Last successful fetch time
- Errors (if any)
- Official badge for the Carrier Wave server

## See Also

- [Dashboard & Statistics](/reference/dashboard/) - Your personal stats and service sync status
- [Activity Log](/reference/activity-log/) - Hunter mode spot logging and daily QSO tracking
- [Settings](/reference/settings/) - Configure sync services and community features
