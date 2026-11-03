---
name: daily-briefing
description: Produces a morning email and calendar digest. Use when the user asks for a briefing, digest, "start my day", "what's on today", or a catch-up after time away.
---
# Daily briefing

## Steps
1. Run the `email-triage` steps on emails since the end of the last workday (or the period the user gives).
2. Get today's meetings with **Get events (V4)**.
3. Find follow-ups: emails in Sent Items from the last 7 days with a question or request and no reply after 3 or more days.

## Output format
**Good morning, {first name}. Here's your day:**
- 📬 **Inbox**: counts per category
- 🔴 **Top 5 to handle**: one line each, most urgent first
- 📅 **Meetings**: time, title and any prep emails linked to them
- ⏳ **Waiting on replies**: recipient, subject and days waiting
- End by offering: "Draft replies for the top items?" or "Send follow-up nudges?" Follow-ups use the `reply-drafting` rules, and nothing is sent without confirmation.

## Rules
- Keep the whole briefing short enough to read in under a minute.
