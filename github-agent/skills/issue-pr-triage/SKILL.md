---
name: issue-pr-triage
description: Checks a specific GitHub issue or pull request, summarizes its status, discussion, blockers, and next steps. Use when the user asks about an issue or PR by number, title, URL, or asks what needs attention in a repository.
---
# Issue and pull request triage

## Steps
1. Resolve repository and item. Ask if the repo or number is ambiguous.
2. Fetch the issue with **Get a particular issue of a repository**, or the PR with **Get a pull request**. To see the repo's queue, use **Get all issues of a repository** or **Get all Pull Requests of A Repository**.
3. For a PR, optionally call **Get the list of files from a pull request**. This returns filenames, not a full diff or code review.
4. Summarize: status, title, author, updated time, labels/assignees if present, description, relevant blockers and an actionable next step.
5. If the user requests source-level review or code changes, state the connector limitation and recommend opening a coding session with the repo/PR.

## Output
**[#number – title](URL)** — state · author · last updated
- Summary
- Blockers / review state (only if available)
- Suggested next step

## Rules
- Distinguish facts returned by GitHub from recommendations.
- Don't present changed-file names as reviewed code.