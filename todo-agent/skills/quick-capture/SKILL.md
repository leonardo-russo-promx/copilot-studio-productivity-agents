---
name: quick-capture
description: Adds personal to-dos and reminders to Microsoft To Do from natural language, notes, or email text. Use when the user says "remind me", "add to my to-do list", "don't let me forget", or pastes notes with personal action items.
---
# Quick capture

## Steps
1. Split the request into separate to-dos. Each title starts with a verb and stays under 60 characters ("Call the dentist", not "dentist").
2. For each to-do, work out:
   - **Due date / reminder time**: turn relative times into absolute ones and show them ("Fri, Nov 7, 09:00")
   - **List**: an existing list it clearly fits, otherwise the default list
   - **Importance**: High only if the user says urgent or important
   - **Notes**: extra context or the link to the source email
3. Check for duplicates in the target list with **List to-dos by folder**. If a similar open to-do exists, ask instead of adding another.
4. If there are more than 3 to-dos, show them first (Title | Due | Reminder | List) and ask "Add these?".
5. Create them with **Add a to-do (V3)**.
6. Confirm in one line each: ✅ Title – due date – list.

## Rules
- Don't set a reminder unless the user asked to be reminded or gave a specific time.
- Leave fields empty rather than guessing.