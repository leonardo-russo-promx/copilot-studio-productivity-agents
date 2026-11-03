---
name: repo-overview
description: Finds repositories and gives a concise overview of their issues and pull requests. Use when the user asks about a repository, what's happening in a repo, open issues or PRs, or recent GitHub activity.
---
# Repository overview

## Steps
1. Resolve the repository. Use **Lists all repositories for the authenticated user** if the user says "my repos"; for organization repositories use **Lists all public repositories for an organization** or the exact repo name/owner provided.
2. For repository issues use **Get all issues of a repository**; for PRs use **Get all Pull Requests of A Repository**. Set state to open unless asked otherwise. Use **Search Github using Query** for keyword or cross-repo searches.
3. For an individual item, fetch it using **Get a particular issue of a repository** or **Get a pull request**.
4. Return up to 10 most recently updated results, linked when a URL is returned.

## Output
- Repo: owner/name and description if available
- Issues / PRs: number, title, state, author, updated time, URL
- Call out overdue-looking, blocked, or review-requested items only when the returned data supports it.

## Rules
- Say which repository, state, and result limit you used.
- Don't claim to have searched code or read a PR diff based only on PR metadata or its changed-file list.