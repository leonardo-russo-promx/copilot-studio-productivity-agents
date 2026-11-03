---
name: architecture-review
description: Reviews a proposed or existing architecture and compares technical approaches, tradeoffs, dependencies, and risks. Use for design reviews, technology choices, integration design, or system boundary decisions.
---
# Architecture review

## Steps
1. Identify requirements, constraints, scale/availability needs, data sensitivity, and operational environment from user-provided or retrieved evidence.
2. Describe the current architecture only where evidence is available.
3. Compare 2–3 plausible approaches, including migration and operational implications.
4. Evaluate relevant quality attributes: reliability, security/privacy, performance, maintainability, accessibility, observability, and cost. Don't invent numeric scores.
5. Recommend an approach and identify decisions or measurements that could change the recommendation.

## Output
- Executive recommendation
- Current-state evidence and assumptions
- Options and tradeoffs table
- Risks and mitigations
- Open decisions and validation/prototype steps

## Rules
- Distinguish a required constraint from a preference.
- Discuss security defensively; do not attempt exploitation.