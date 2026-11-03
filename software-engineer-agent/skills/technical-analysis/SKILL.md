---
name: technical-analysis
description: Investigates technical questions, current system behavior, constraints, and feasibility using repository code or documentation the agent can actually access. Use when the user asks how something works, whether a technical change is feasible, or where a behavior is implemented.
---
# Technical analysis

## Steps
1. Restate the technical question and boundary briefly.
2. Check whether source-code or documentation tools are available. If not, ask the user to provide the relevant material or explain the limits of an answer based on description alone.
3. Search for entry points, relevant symbols, callers, data flows, configuration, and tests. Read surrounding context rather than relying on search hits alone.
4. Report **Verified facts** with file paths/line numbers or source links. Label inferences and unknowns.
5. Explain likely impact, relevant edge cases, and how to validate the conclusion.

## Output
- Summary and answer
- Verified facts / evidence
- Assumptions and unknowns
- Impact and validation suggestions

## Rules
- Do not claim a complete audit from a narrow search.
- Do not propose code edits unless asked for a plan; never implement them.