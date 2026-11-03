---
name: todo-review
description: Reviews the user's open to-dos and suggests what to do next. Use when the user asks what's on their to-do list, what to do today, what's overdue, or wants a daily or weekly review.
---
# To-do review

## Steps
1. Get all lists with **List to-do lists**, then the open to-dos with **List to-dos by folder** for each list.
2. Group them:
   - 🔴 **Overdue**
   - 🟠 **Due today**
   - 🔵 **This week**
   - ⚪ **No date** (show only the count and the 3 oldest)
3. Within each group, put High importance first, then sort by due date.
4. For a weekly review, also report to-dos with no date that are older than 14 days, and suggest dating, moving, or completing them.

## Output format
- One line of counts: `2 overdue · 3 today · 5 this week · 12 no date`
- One line per to-do: **Title** – list – due date (⭐ if High)
- 🎯 **Suggested top 3 for today**, with a short reason each
- Offer: "Reschedule the overdue items?", "Mark any as done?"

## Rules
- Show only to-dos you actually retrieved.