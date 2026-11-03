# Plan Copilot (Planner agent)

A Microsoft Planner assistant: captures tasks, gives briefings on your tasks, reports plan status, and breaks projects into plans.

## Files
| File | Purpose |
|---|---|
| `system-prompt.md` | Agent instructions |
| `skills/*/SKILL.md` | Skills: `task-capture`, `my-tasks-briefing`, `plan-status-report`, `plan-builder` |
| `test-set.csv` | Test set for the Evaluate tab |

## Tools (connectors)
| Connector | Actions |
|---|---|
| Planner | List my tasks, List tasks, List buckets, Get task, Get task details, Create a task, Update a task, Update task details, Create a bucket, Add/Remove assignees, Delete a task (ask before running) |
| Office 365 Groups | List groups the user belongs to. Description: "Use to find the user's Planner plans and their IDs before listing or creating tasks." |
| Office 365 Users | Search for users (look up people before assigning) |
| Microsoft Teams / Outlook (optional) | Post or draft status updates |

## Triggers (optional)
- Planner – *When a task is assigned to me*: alerts
- Recurrence (weekly): status report

## Settings
- Connections: user authentication
- Model: **Claude Sonnet 5** (backup: GPT-6.1 Sol)
- Note: the Planner connector may only support basic plans, not premium (Project) plans.