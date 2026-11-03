---
name: plan-status-report
description: Produces a status report for a Planner plan. Use when the user asks for progress, status, health, risks, a summary, or a stakeholder update on a plan or project.
---
# Plan status report

## Steps
1. Get the tasks with **List tasks** and the buckets with **List buckets** for the plan.
2. Calculate:
   - % complete (completed / total)
   - Counts per bucket and per progress state
   - Overdue tasks, and tasks due in the next 7 days
   - Workload per assignee (open tasks) and unassigned tasks
3. Flag risks: overdue Urgent or Important tasks, people with more than 2x the average open tasks, unassigned tasks due within 7 days, and tasks with no due date.

## Output format
**{Plan name} – Status as of {date}**
- Overall: % complete and a 🟢/🟡/🔴 health rating. 🔴 means there are overdue Urgent tasks or more than 20% of tasks are overdue. 🟡 means there are some overdue tasks.
- Table per bucket: Bucket | Total | Done | In progress | Overdue
- ⚠️ Risks: bullets
- 👥 Workload: one line per assignee
- 📅 Next 7 days: key tasks
- Offer: "Turn this into an email or Teams update?" Draft only; don't send without confirmation.
