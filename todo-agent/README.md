# To Do Copilot (Microsoft To Do agent)

A personal to-do and reminder assistant: quick capture, a daily or weekly review, and list cleanup.

## Agent description
Use this text for the agent's description (Botfather uses it to route requests):
> Manages the user's personal Microsoft To Do lists: adds to-dos and reminders from natural language, reviews what's overdue or due today, marks items complete, and organizes lists. Use for personal to-dos, reminders, and checklists, not shared team plans (use Plan Copilot for those).

## Files
| File | Purpose |
|---|---|
| `system-prompt.md` | Agent instructions |
| `skills/*/SKILL.md` | Skills: `quick-capture`, `todo-review`, `list-organizer` |
| `test-set.csv` | Test set for the Evaluate tab |

## Tools (connectors)
| Connector | Actions |
|---|---|
| Microsoft To Do (Business) | List to-do lists, List to-dos by folder (V2), Get a to-do (V3), Add a to-do (V3), Update a to-do (V3), Create a to-do list, Delete a to-do (V2) (ask before running) |

Action names may vary slightly in the connector. Match them by function.

## Triggers (optional)
- Recurrence (weekdays at 08:00): to-do review for today
- Recurrence (Friday at 16:00): weekly review

## Settings
- Connections: user authentication
- Model: **Claude Sonnet 5** (backup: GPT-6.1 Sol). A lighter model would also work, because the tasks are simple.

## To Do vs. Planner
| To Do Copilot | Plan Copilot |
|---|---|
| Personal to-dos and reminders | Shared team plans |
| Only the user | Tasks assigned to others |
| "Remind me…", shopping and personal lists | Buckets, project status, workload |