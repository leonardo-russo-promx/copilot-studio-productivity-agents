# GitHub Copilot (GitHub agent)

Helps the user find repositories, track issues and pull requests, summarize repository activity, and prepare new GitHub issues or pull requests. It does not edit code or merge PRs.

## Agent description
Use this text for the agent's description (Botfather uses it to route requests):
> Helps the user with GitHub repositories, issues, and pull requests: finds repos, lists and summarizes open issues or PRs, checks an item's status and blockers, searches for likely duplicate issues, and drafts new issues or PRs for confirmation. Use for GitHub project tracking and filing work items; use a coding agent for code changes or source-level review.

## Files
| File | Purpose |
|---|---|
| `system-prompt.md` | Agent instructions |
| `skills/*/SKILL.md` | Skills: `repo-overview`, `issue-pr-triage`, `github-item-drafting` |
| `test-set.csv` | Test set for the Evaluate tab |

## Tools (connectors)
Add the Microsoft **GitHub** connector and select the operations needed:

| GitHub action | Use |
|---|---|
| Lists all repositories for the authenticated user | Find the user's accessible repositories |
| Lists all public repositories for an organization | Discover an organization's public repositories |
| Get all issues of a repository | List issues, filter by state/assignee/labels/date |
| Find issues by state and keyword | Search for issues and likely duplicates |
| Search Github using Query | Search GitHub with a query |
| Get a particular issue of a repository | Read one issue |
| Get all Pull Requests of A Repository | List repository PRs |
| Get a pull request | Read one PR |
| Get the list of files from a pull request | List changed filenames only; not a diff/code review |
| Create an issue | Create an issue after user confirmation |
| Update an Issue | Update an issue after showing exact changes and confirming |
| Create a pull request (Preview) | Optional; create after user confirmation and only for an existing head branch |

Do **not** add merge, secret management, permissions, webhook, or repository creation actions to this assistant.

## Settings
- Connection: GitHub OAuth for the user's account. Check what private and organization repos the connection can access.
- Model: **Claude Sonnet 5** (backup: GPT-6.1 Sol).

## Limitations
- The connector can return PR metadata and changed filenames, not necessarily the complete code diff. Don't use it for code review or code changes; open a coding session for that.
- GitHub connector operations are subject to API throttling and the authenticated account's repository permissions.