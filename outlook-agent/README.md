# Inbox Copilot (Outlook agent)

A personal Outlook assistant: triages the inbox, sends alerts, drafts replies, and gives daily briefings.


## Agent description
Use this text for the agent's description (Botfather uses it to route requests):
> Handles the user's Outlook email: summarizes and prioritizes the inbox, searches emails, drafts and sends replies (with confirmation), flags phishing, sends urgent-email alerts, and gives a daily email and calendar briefing. Use for any request about reading, triaging, or writing emails.

## Files
| File | Purpose |
|---|---|
| `system-prompt.md` | Agent instructions |
| `skills/*/SKILL.md` | Skills: `email-triage`, `reply-drafting`, `phishing-check`, `daily-briefing` |
| `test-set.csv` | Test set for the Evaluate tab |

## Tools (connectors)
| Connector | Actions |
|---|---|
| Office 365 Outlook | Get emails (V3), Get email (V2), Draft an email message, Reply to email (V3), Send an email (V2), Flag email, Mark as read/unread, Move email, Get events (V4), Find meeting times (V2), Create event (V4) |
| Office 365 Users | Get my profile (V2), Get manager (V2), Search for users |
| Microsoft Teams | Post message in a chat or channel (alerts) |
| Microsoft To Do | Add a to-do (V3) |

Set Send, Reply, Create event and Move to **ask before running**.

## Triggers
- Office 365 Outlook – *When a new email arrives (V3)*: alerts
- Recurrence (weekdays at 08:00): daily briefing

## Settings
- Connections: user authentication, with Microsoft Entra ID sign-in
- Model: **Claude Sonnet 5** (backup: GPT-6.1 Sol)