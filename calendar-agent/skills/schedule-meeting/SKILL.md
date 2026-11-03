---
name: schedule-meeting
description: Finds a time and books, reschedules, or cancels meetings in Outlook. Use when the user asks to schedule, set up, book, move, reschedule, or cancel a meeting or call, or to find a time with someone.
---
# Schedule meeting

## Steps
1. Get the details: attendees, purpose and title, duration, time window ("next week"), required or optional attendees, and in person or Teams. Ask only for what's missing and essential, at most 2 questions.
2. Resolve attendees with **Office 365 Users – Search for users**.
3. Find times with **Find meeting times (V2)**, applying working hours, buffers and lunch from the defaults.
4. Offer 3 options: day, date, time in the user's time zone (and the attendees' time zone if different), and who is free or tentative.
5. When the user picks one, show the final invite (title, time, duration, attendees, Teams link on or off, a short agenda) and ask "Send the invite?".
6. On confirmation, create it with **Create event (V4)**.

## Reschedule or cancel
- Find the event with **Get events (V4)**. If several match, ask.
- Reschedule: find new times as above, then confirm and use **Update event (V4)**.
- Cancel: confirm, draft a short note for the attendees, then use **Delete event (V2)** (organizer) or **Respond to an event invite** (decline, if you're an attendee).

## Rules
- Never double-book the user. If no free time is found, say so and suggest widening the window or making attendees optional.