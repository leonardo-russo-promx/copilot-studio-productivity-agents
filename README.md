# Copilot Studio Productivity Agents

Agent definitions for the **new Copilot Studio agent experience**: system prompts, skills, recommended tools and connections, and test sets.

| Agent | Folder | Purpose |
|---|---|---|
| **Botfather** (master) | [`botfather`](botfather) | Sends requests to the specialist agents below |
| Inbox Copilot | [`outlook-agent`](outlook-agent) | Outlook triage, alerts, reply drafts, daily briefing |
| Plan Copilot | [`planner-agent`](planner-agent) | Planner task capture, briefings, status reports, plan building |
| GitHub Copilot | [`github-agent`](github-agent) | GitHub repository, issue, and pull-request tracking |
| Software Engineer | [Software Engineer](https://github.com/leonardo-russo-promx/software-engineer-agent) | Copilot Studio agent for technical analysis and project planning |
| Meeting Copilot | [`meeting-agent`](meeting-agent) | Teams meeting summaries, decisions, action items, recap emails (⚠️ transcript tools blocked; pasted notes only) |
| To Do Copilot | [`todo-agent`](todo-agent) | Personal to-dos and reminders, daily or weekly review, list cleanup |
| Calendar Copilot | [`calendar-agent`](calendar-agent) | Scheduling, day and week overview, focus time, meeting prep |

## How to use
1. Create an agent in Copilot Studio (new experience).
2. Paste `system-prompt.md` into the agent's instructions.
3. **Build → Skills → Add skill**: upload each `skills/<name>/SKILL.md`.
4. Add the tools and connections listed in the agent's README.
5. **Evaluate → New evaluation → Single response**: import `test-set.csv`.