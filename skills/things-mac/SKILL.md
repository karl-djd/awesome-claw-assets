---
name: things-mac
description: Manage Things 3 on macOS through the local `things` CLI. Use when the user wants to inspect inbox/today/upcoming, search tasks, or add and update real Things todos and projects.
---

# Things Mac

Use `things` when the user wants real Things 3 task operations instead of a generic task list.

## Why keep this

- clear value for people already living in Things
- honest split between local reads and explicit writes
- practical support for inbox, today, projects, tags, and task updates
- no opaque bundle behavior beyond documented local CLI usage

## Expected runtime

- macOS
- Things 3 installed
- `things` installed
- Full Disk Access for local database reads when needed
- auth token available for some update actions

## Good workflow

1. read or search first to identify the exact task or project
2. use dry-run for write operations when available
3. treat task completion, cancellation, and project moves as explicit user actions
4. do not assume delete is supported; the CLI mainly supports add and update flows

## Useful patterns

```bash
things inbox --limit 50
things today
things upcoming
things search "dentist"
things --dry-run add "Buy milk"
things add "Buy milk" --when today --tags "errands"
things update --id <UUID> --auth-token <TOKEN> --completed
```

## Caution

This skill touches a real Things database and URL-scheme writes. Do not create or modify tasks casually, and do not assume Full Disk Access or auth-token setup already exists.
