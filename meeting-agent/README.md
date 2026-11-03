# Meeting Copilot (Teams meeting agent)

Turns Teams meetings into summaries, decisions, action items, and recap emails.

## Agent description
Use this text for the agent's description (Botfather uses it to route requests):
> Summarizes Teams meetings from transcripts or notes: decisions, action items with owners and due dates, open questions, and answers about what was discussed. Drafts recap emails for attendees (with confirmation). Use for any request about past meetings, meeting notes, minutes, or follow-ups.

## Files
| File | Purpose |
|---|---|
| `system-prompt.md` | Agent instructions |
| `skills/*/SKILL.md` | Skills: `meeting-summary`, `action-items`, `recap-email` |
| `test-set.csv` | Test set for the Evaluate tab |

## Tools (connectors)
| Connector | Actions |
|---|---|
| Office 365 Outlook | Get events (V4) (find the meeting and its join URL), Draft an email message, Send an email (V2) (ask before running) |
| **Teams Transcripts** (custom connector, see below) | Find meeting by join URL, List transcripts, Get transcript content |
| Microsoft Teams (optional) | List chat messages (fallback when there is no transcript), Post message in a chat or channel (ask before running) |
| Office 365 Users | Search for users (match speakers and attendees to people) |

Tasks are created through **Plan Copilot** via Botfather, so no Planner connector is needed here.

## Transcript access (custom connector)
The standard Teams connector has no transcript actions, so create a custom connector to Microsoft Graph:
- Auth: OAuth 2.0 (Microsoft Entra ID), **delegated** permission `OnlineMeetingTranscript.Read.All` (plus `OnlineMeetings.Read`). Requires admin consent.
- Operations:
  - `GET /me/onlineMeetings?$filter=JoinWebUrl eq '{joinUrl}'`: find the meeting
  - `GET /me/onlineMeetings/{meetingId}/transcripts`: list transcripts
  - `GET /me/onlineMeetings/{meetingId}/transcripts/{transcriptId}/content?$format=text/vtt`: transcript text
- Tenant prerequisites: transcription turned on in the Teams meeting policy, and **Graph API access to transcripts** turned on (Teams admin center → Meetings → Meeting settings → Transcript API access). Otherwise Graph returns 403.
- Check: with delegated permissions, access may be limited to meetings the user organized. Test with a meeting you attended but didn't organize.
- Fallback: the user can paste or upload a transcript or notes, and every skill works on that text.

## Triggers (optional)
- Recurrence (end of day): "Recap today's meetings" digest

## Settings
- Connections: user authentication
- Model: **Claude Sonnet 5** (backup: GPT-6.1 Sol). Long transcripts benefit from a large context window and careful extraction.