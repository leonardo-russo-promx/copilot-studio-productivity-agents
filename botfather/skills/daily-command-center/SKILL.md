---
name: daily-command-center
description: Builds one combined daily briefing across email and Planner. Use when the user says "start my day", "what do I need to do today", "catch me up", or asks for an overall briefing.
---
# Daily command center

## Steps
1. Ask Inbox Copilot for the daily briefing: email counts by priority, the top 5 emails to handle, today's meetings, and replies the user is still waiting on.
2. Ask Plan Copilot for my tasks: overdue, due today or this week, and the top 3 to focus on.
3. Combine and remove duplicates. If an email and a task are about the same thing, show them once.

## Output format
**Good morning, {first name}.**
- 🎯 **Top 3 priorities today**: across email and tasks, with a one-line reason each
- 📬 **Email**: counts and urgent items
- ✅ **Tasks**: overdue and due today
- 📅 **Meetings**: times and titles
- End by offering 2–3 next actions ("Draft replies for urgent emails?", "Turn action emails into tasks?")

## Rules
- If one specialist fails, still show the other part and note what's missing.
- Keep it readable in under a minute.