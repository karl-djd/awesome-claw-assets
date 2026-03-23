---
name: apple-reminders
description: Manage Apple Reminders on macOS through the local `remindctl` CLI. Use for explicit reminder and to-do actions like listing, creating, completing, editing, and deleting reminders.
---

# Apple Reminders

Use `remindctl` when the user wants real Apple Reminders operations instead of a plain text task list.

## Why keep this

- obvious everyday value
- narrow macOS app scope
- local-first workflow
- easy to explain and verify

## Expected runtime

- macOS
- `remindctl`
- Apple Reminders permission granted to the terminal or host app

## Good workflow

1. check permission or current reminder state first
2. list target reminders or lists when ambiguity exists
3. perform writes only for explicit user intent
4. confirm destructive actions like delete when the request is unclear

## Useful patterns

```bash
remindctl status
remindctl today --json
remindctl list
remindctl add "Buy milk"
remindctl add --title "Call mom" --list Personal --due tomorrow
remindctl edit 1 --title "New title" --due 2026-01-04
remindctl complete 1 2 3
remindctl delete 4A83 --force
```

## Caution

This skill can mutate a real reminders database. Do not silently create, complete, rename, or delete reminders unless the user clearly asked for it.
