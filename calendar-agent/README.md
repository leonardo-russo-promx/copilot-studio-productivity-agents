# Calendar Copilot (Outlook calendar agent)

A personal calendar assistant: scheduling, day and week overview, focus time, and meeting prep.

## Agent description
Use this text for the agent's description (Botfather uses it to route requests):
> Manages the user's Outlook calendar: shows today's or the week's schedule, free time and conflicts; finds times with colleagues; books, reschedules, or cancels meetings (with confirmation); blocks focus time; and prepares briefs for upcoming meetings. Use for any request about schedules, availability, meetings to book, or meeting preparation.

## Files
| File | Purpose |
|---|---|
| `system-prompt.md` | Agent instructions |
| `skills/*/SKILL.md` | Skills: `schedule-meeting`, `day-overview`, `focus-time`, `meeting-prep` |
| `test-set.csv` | Test set for the Evaluate tab |

## Tools (connectors)
| Connector | Actions |
|---|---|
| Office 365 Outlook | Get calendar view of events (V3), Get events (V4), Get event (V3), Find meeting times (V2), Create event (V4), Update event (V4), Delete event (V2), Respond to an event invite |
| Office 365 Users | Search for users (V2), Get user profile (V2), Get my profile (V2) |

Set Create event, Update event, Delete event and Respond to an event invite to **ask before running**. Action names may vary slightly in the connector. Match them by function.

## Triggers (optional)
- Recurrence (weekdays at 08:00): day overview
- Recurrence (every 15 minutes during work hours): prep brief for meetings starting in 15–30 minutes

## Settings
- Connections: user authentication
- Model: **Claude Sonnet 5** (backup: GPT-6.1 Sol). Scheduling needs careful reasoning about dates and time zones.

## Calendar vs. Inbox vs. Meeting Copilot
| Calendar Copilot | Inbox Copilot | Meeting Copilot |
|---|---|---|
| Upcoming meetings: book, move, prep | Emails, including meeting requests sent by email | Past meetings: summary, actions, recap |