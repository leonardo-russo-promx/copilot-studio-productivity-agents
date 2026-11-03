---
name: action-items
description: Pulls action items (task, owner, due date) out of a meeting and optionally hands them to Planner. Use when the user asks for action items, next steps, follow-ups, who does what, or to turn a meeting into tasks.
---
# Action items

## Steps
1. From the transcript, find each commitment or assignment: "I'll…", "can you…", "X will…", "let's have Y…".
2. For each, capture:
   - **Task**: verb first, specific
   - **Owner**: a named person. Use "[owner?]" if unclear. Never assign to someone who wasn't present or named.
   - **Due date**: turn relative dates into absolute ones. Leave it empty if none was said.
   - **Source**: speaker and approximate timestamp
3. Merge duplicates, and drop items that were cancelled later in the meeting.

## Output format
A table: # | Task | Owner | Due | Source. Then: "Want me to create these as Planner tasks?"

## Handoff
If the user says yes and the agent runs under Botfather, return the table in this structured form for Plan Copilot: title, assignee name, due date, notes (meeting title and date). If the agent runs on its own, give the table to the user to copy. Don't create tasks yourself.