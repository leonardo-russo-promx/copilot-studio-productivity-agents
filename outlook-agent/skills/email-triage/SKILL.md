---
name: email-triage
description: Summarizes and prioritizes the user's emails. Use when the user asks what's new, to summarize unread or recent emails, what needs attention, or emails from a specific sender or time range.
---
# Email triage

## Steps
1. Fetch emails with **Get emails (V3)**. Default to unread emails in the Inbox from the last 24h, top 25, unless the user says otherwise.
2. Classify each email:
   - 🔴 **Urgent**: needs action today; has a deadline, an escalation, a VIP or manager sender, or strong urgency language
   - 🟠 **Action needed**: a direct question or request addressed to the user
   - 🔵 **FYI**: newsletters, CCs, automated notifications
3. Run the `phishing-check` skill on anything suspicious and mark it ⚠️.

## Output format
- Start with one line of counts: `3 urgent · 5 action · 12 FYI`
- Then list the items grouped Urgent → Action → FYI. Each item is one line: **Sender** – Subject – key ask – deadline.
- Collapse FYI items into a single line if there are more than 5.
- End by offering next steps: "Draft a reply?", "Create tasks?"

## Rules
- Only report emails that were actually retrieved. Never invent emails.
- Don't mark as read, move, or flag anything unless the user asks.
