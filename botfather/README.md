# Botfather (master / orchestrator agent)

Sends user requests to the specialist agents and combines their answers. It has no email or Planner tools of its own.


## Agent description
Use this text for the agent's description (Botfather uses it to route requests):
> Master assistant that understands the user's request and sends it to specialist agents (Inbox Copilot for email, Plan Copilot for Planner tasks, Meeting Copilot for Teams meetings, To Do Copilot for personal to-dos, Calendar Copilot for scheduling and the calendar), coordinating multi-step requests and combining the results into one answer.

## Files
| File | Purpose |
|---|---|
| `system-prompt.md` | Agent instructions, including routing rules |
| `skills/*/SKILL.md` | Skills: `multi-agent-handoff`, `daily-command-center` |
| `test-set.csv` | Routing test set for the Evaluate tab |

## Connected agents
Add them from **Build → Connected agents**:
| Agent | Folder |
|---|---|
| Inbox Copilot | [`../outlook-agent`](../outlook-agent) |
| Plan Copilot | [`../planner-agent`](../planner-agent) |
| Meeting Copilot | [`../meeting-agent`](../meeting-agent) |
| To Do Copilot | [`../todo-agent`](../todo-agent) |
| Calendar Copilot | [`../calendar-agent`](../calendar-agent) |

Requirements:
- Each specialist must be in the **same environment**, **published**, and set as **available to connect**.
- **Share each specialist separately** with every user. Access to Botfather doesn't give access to its connected agents.
- Give each connected agent a clear **description**. The orchestrator routes based on it.
- Use **user authentication** on the specialists' connections, so each user only reaches their own mailbox and plans.

## Tools
None required. Optional: Microsoft Teams (post message) for proactive alerts.

## Model
**Claude Sonnet 5** (backup: GPT-6.1 Sol). Routing and multi-step coordination benefit from a strong reasoning model.

## Adding a new specialist
1. Create the agent in its own folder in this repo.
2. Publish it and make it available to connect.
3. Add it in Botfather → Connected agents.
4. Add a line to the specialist list in `system-prompt.md`, plus a routing test case.