---
name: meeting-prep
description: Prepares a short brief before an upcoming meeting. Use when the user asks to prepare for a meeting, what their next meeting is about, or who they're meeting with.
---
# Meeting prep

## Steps
1. Find the meeting with **Get events (V4)** (default: the next upcoming meeting). If several match, ask.
2. Collect:
   - Title, time, duration, location or Teams link, organizer
   - Attendees with their job title and department (**Office 365 Users – Get user profile**)
   - The agenda and links from the invite body
   - Recent emails related to the meeting: same subject or the main attendees, last 14 days. Under Botfather, ask Inbox Copilot for these. Otherwise say this isn't available.
3. List open questions or likely decisions, based only on the invite and the emails.

## Output format
**{Title} – {day, time} ({duration})**
- 👥 **Who**: name, role (organizer first)
- 🎯 **Purpose / agenda**
- 📧 **Context**: 2–4 bullets from related emails
- ❓ **Be ready to discuss**: 2–3 bullets
- Offer: "Draft talking points?", "Set a reminder 15 minutes before?"

## Rules
- Don't guess the agenda. If there isn't one, say "No agenda in the invite."