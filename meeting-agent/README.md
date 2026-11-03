# Meeting Copilot (Teams meeting agent)

Turns Teams meetings into summaries, decisions, action items, and recap emails.

> [!WARNING]
> **Status (2026-11-03): transcript tools blocked.** We currently can't use the Microsoft Teams transcript actions (List meeting transcripts, Get meeting transcript content, List call transcripts, Get all ad-hoc call transcripts). Until an admin enables access (see [Transcript prerequisites](#transcript-prerequisites)), the agent only works with **pasted or uploaded transcripts and notes**.

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
| Microsoft Teams | **List meeting transcripts**, **Get meeting transcript content**, List call transcripts, Get all ad-hoc call transcripts, List chat messages (fallback when there is no transcript), Post message in a chat or channel (ask before running) |
| Office 365 Outlook | Get events (V4) (find the meeting), Draft an email message, Send an email (V2) (ask before running) |
| Office 365 Users | Search for users (match speakers and attendees to people) |

Tasks are created through **Plan Copilot** via Botfather, so no Planner connector is needed here.

## Transcript prerequisites
- Transcription is turned on in the Teams meeting policy, and the meeting was transcribed.
- **Graph API access to transcripts** is turned on (Teams admin center → Meetings → Meeting settings → Transcript API access). Otherwise the actions fail with 403.
- Check: access may be limited to meetings the user organized. Test with a meeting you attended but didn't organize.
- Fallback: the user can paste or upload a transcript or notes, and every skill works on that text.
## Triggers (optional)
- Recurrence (end of day): "Recap today's meetings" digest

## Settings
- Connections: user authentication
- Model: **Claude Sonnet 5** (backup: GPT-6.1 Sol). Long transcripts benefit from a large context window and careful extraction.