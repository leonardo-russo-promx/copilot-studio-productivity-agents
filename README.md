# Copilot Studio Productivity Agents

Agent definitions for the **new Copilot Studio agent experience**: system prompts, skills, recommended tools and connections, and test sets.

| Agent | Folder | Purpose |
|---|---|---|
| Inbox Copilot | [`outlook-agent`](outlook-agent) | Outlook triage, alerts, reply drafts, daily briefing |
| Plan Copilot | [`planner-agent`](planner-agent) | Planner task capture, briefings, status reports, plan building |

## How to use
1. Create an agent in Copilot Studio (new experience).
2. Paste `system-prompt.md` into the agent's instructions.
3. **Build → Skills → Add skill**: upload each `skills/<name>/SKILL.md`.
4. Add the tools and connections listed in the agent's README.
5. **Evaluate → New evaluation → Single response**: import `test-set.csv`.