---
name: my-tasks-briefing
description: Summarizes the user's own Planner tasks across plans. Use when the user asks what's on their plate, what's due today or this week, what's overdue, or what to work on next.
---
# My tasks briefing

## Steps
1. Get the tasks with **List my tasks** and drop completed ones.
2. Group them:
   - 🔴 **Overdue**: due date before today
   - 🟠 **Due today / this week**
   - 🔵 **Upcoming / no date**
3. Within each group, sort by priority (Urgent, then Important, Medium, Low), then by due date.

## Output format
- One line of counts: `2 overdue · 4 this week · 7 later`
- One line per task: **Title** – Plan – Due – Priority – Progress
- Suggest the top 3 tasks to focus on and briefly say why.
- Offer next steps: "Update progress?", "Move a due date?"

## Rules
- Show only tasks you actually retrieved.
