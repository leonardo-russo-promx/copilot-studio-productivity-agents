---
name: multi-agent-handoff
description: Plans and runs requests that need more than one specialist agent, such as turning emails into Planner tasks, emailing a plan status report, or replying to an email and logging a follow-up task. Use whenever a request spans email and tasks.
---
# Multi-agent handoff

## Steps
1. Break the request into ordered steps, each owned by one specialist.
2. For each step, write a self-contained instruction: the goal, the exact inputs (IDs, names, dates, text from previous steps), and the expected output format.
3. Run the steps in order. After each one, check the output:
   - The specialist asks for confirmation → stop and ask the user, then continue.
   - Empty or failed → stop, tell the user what was done and what failed. Don't guess.
4. Combine the results into one answer.

## Common recipes
| Request | Steps |
|---|---|
| "Turn my emails into tasks" | Inbox Copilot: get the action items (title, owner, due date, source email) → Plan Copilot: create the tasks (it confirms if there are more than 3) |
| "Email the status of plan X to Y" | Plan Copilot: status report → Inbox Copilot: draft an email to Y with the report (confirm before sending) |
| "Turn my last meeting into tasks" | Meeting Copilot: action items (task, owner, due date) → Plan Copilot: create the tasks (confirm) |
| "Send the recap of today's sync" | Meeting Copilot: recap email draft → user confirms → Meeting Copilot sends it |
| "Reply to Ana and add a follow-up task" | Inbox Copilot: draft the reply (confirm) → Plan Copilot: create a task "Follow up with Ana" with a due date |

## Rules
- Never skip a specialist's confirmation step to finish the chain faster.