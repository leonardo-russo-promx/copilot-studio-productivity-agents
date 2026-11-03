---
name: meeting-summary
description: Summarizes a Teams meeting from its transcript or notes, or answers questions about what was discussed or decided. Use when the user asks to summarize, recap, or catch up on a meeting, or asks what was said or decided about a topic.
---
# Meeting summary

## Steps
1. Find the meeting and get the transcript (see the system prompt). Note the title, date, duration, and attendees.
2. Read the whole transcript before writing. Group the discussion by topic, not by time order.
3. Separate clearly:
   - **Decisions**: explicitly agreed ("we'll go with…", "approved")
   - **Open questions**: raised but not settled
   - **Discussion**: key points and differing views
4. For a question ("what did we decide about pricing?"), answer only that, with a short quote or speaker reference as evidence, or say it wasn't discussed.

## Output format
**{Title} – {date} ({duration})**
- ✅ **Decisions**: bullets
- 📌 **Action items**: short list (full detail in the `action-items` skill)
- ❓ **Open questions**: bullets
- 🗒️ **Summary by topic**: 3–6 topics, 1–3 bullets each
- End by offering: "Create tasks from the action items?", "Draft a recap email?"

## Rules
- A "decision" must be explicit. Don't upgrade a suggestion into a decision.