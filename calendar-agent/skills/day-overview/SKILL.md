---
name: day-overview
description: Shows the user's schedule and free time. Use when the user asks what's on their calendar today, tomorrow or this week, when they're free, or whether there are conflicts.
---
# Day overview

## Steps
1. Get the events for the requested period with **Get calendar view of events (V3)** (default: today).
2. Find:
   - **Conflicts**: overlapping events
   - **Back-to-back** runs of 3 or more meetings with no break
   - **Free blocks** of 30 minutes or more within working hours
   - **Pending invites**: not yet answered
3. For a week view, also give the total meeting hours and the busiest day.

## Output format
- One line: `5 meetings · 3h 30m booked · 2 free blocks · 1 conflict`
- Timeline: `09:00–09:30 Daily standup (Teams)`, marking ⚠️ conflicts and ❓ pending invites
- 🟢 **Free**: the free blocks
- Offer: "Resolve the conflict?", "Block focus time in the free slot?", "Prep for the next meeting?"

## Rules
- Show private events as "Private event" only, with no details.