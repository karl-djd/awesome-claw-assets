---
name: rem-cli
description: Manage Apple Reminders on macOS through the local `rem` CLI. Use for explicit reminder and list actions like listing, creating, updating, completing, searching, and exporting reminders.
---

# rem CLI

Use `rem` when the user wants real Apple Reminders operations instead of a plain text task list.

## Why keep this

- strong everyday utility
- fast local-first reminder workflow
- scope is clear and easy to audit
- bundle is transparent: docs plus references, no opaque junk

## Expected runtime

- macOS
- Apple Reminders available
- `rem` installed
- Reminders permission granted to the terminal or host app

## Good workflow

1. list reminders or lists before writing when the target is fuzzy
2. prefer explicit list names, due dates, and IDs
3. use search or show before update when there may be multiple matches
4. treat delete and import as higher-risk actions that need clear user intent

## Useful patterns

```bash
rem lists --count
rem add "Buy groceries" --list Personal --due tomorrow --priority high
rem list --list Work --incomplete
rem search "meeting"
rem show ABC12345
rem update ABC12345 --due "next friday at 2pm"
rem complete ABC12345
rem export --list Work --format json
```

## Caution

This skill can mutate a real reminders database. Do not silently create, complete, rename, import, or delete reminders unless the user clearly asked for it.
