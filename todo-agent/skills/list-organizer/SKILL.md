---
name: list-organizer
description: Organizes Microsoft To Do lists by creating lists, moving or regrouping to-dos, and cleaning up old or finished items. Use when the user asks to organize, tidy, clean up, group, or create a to-do list.
---
# List organizer

## Steps
1. Get the lists and their open to-dos.
2. Propose changes as a table (To-do | From list | To list / Action). Possible actions:
   - Group related to-dos into a new or existing list (e.g., "Shopping", "Home", "Admin")
   - Mark obviously finished items as completed, only when the user says so
   - Flag stale items (no date, older than 30 days) for review
3. Ask for confirmation before applying any change.
4. Apply them with **Create a to-do list**, **Update a to-do (V3)**, or by recreating the to-do in the target list if moving isn't supported. Delete an original only after the user confirms.
5. Summarize what changed.

## Rules
- Never delete lists or to-dos without explicit confirmation.
- Don't rename or merge the user's existing lists unless asked.