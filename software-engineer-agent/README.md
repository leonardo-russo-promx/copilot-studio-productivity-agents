# Software Engineer (Copilot Studio agent)

A **Copilot Studio new-experience agent** for technical analysis and project planning. It examines the repository context or documentation the user makes available, evaluates options, and produces evidence-based plans. It does not implement changes.

## Agent description
Use this text in the Copilot Studio agent description and when connecting it to Botfather:
> Analyzes technical problems and system architecture, compares implementation approaches, identifies risks and dependencies, and turns goals into actionable project plans with acceptance criteria and validation steps. Use for technical feasibility, architecture decisions, technical requirements, and implementation planning. It plans but does not edit code or implement changes.

## Files
| File | Purpose |
|---|---|
| `system-prompt.md` | Paste into agent Instructions |
| `skills/*/SKILL.md` | Upload under Build → Skills |
| `test-set.csv` | Import under Evaluate → New evaluation → Single response |
| `AGENT-PLAN.md` | Design and setup plan |
| `docs/templates/` | Reusable analysis and project-plan structures |

## Skills
- `technical-analysis`: investigates a technical question using supplied or connected repository evidence.
- `architecture-review`: compares architectural approaches, constraints, and tradeoffs.
- `project-planning`: turns goals and technical findings into phased, dependency-aware delivery plans.

## Tools and knowledge
This agent needs technical context to analyze a real system. Recommended, read-only setup:
1. Add a GitHub MCP server connection in Copilot Studio and enable only repository/code search and file-content read operations, scoped to approved repositories.
2. If GitHub MCP isn't available, add approved SharePoint/OneDrive knowledge sources or have the user provide the relevant design docs and files. Clearly state when the available context is insufficient.
3. Do not add code-write, shell/terminal, issue/PR creation, deployment, or secret-management tools to this planning agent.

A metadata-only GitHub connector is not enough for source-level architecture analysis. Do not claim code was inspected unless code-search/file-read tools returned it.

## Settings
- Connections: per-user authentication, limited to repositories or documents the user is authorized to access.
- Model: choose a currently available generally available reasoning model in the environment; test it against all three cases before rollout.

## Add to Botfather
Add this agent in Botfather → Build → Connected agents. The agents must be published, available to connect, in the same environment, and shared with intended users. Add the description above to the connected-agent description.

## Safety and quality
- Distinguish verified facts, assumptions, and recommendations.
- Cite repository-relative file paths and line numbers when available.
- Never invent requirements, code behavior, deadlines, estimates, or dependencies.
- Plans are recommendations for owner review, not authorization to implement.