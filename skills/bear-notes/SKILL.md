---
name: bear-notes
description: Create, search, open, and update Bear notes on macOS through the local `grizzly` CLI. Use when the user wants to work with a real Bear library instead of generic Markdown files.
---

# Bear Notes

Use `grizzly` when the user wants real Bear note operations.

## Why keep this

- clear Bear-specific value
- local note workflow instead of cloud glue
- easy to scope and reason about
- useful for capture, lookup, and append flows

## Expected runtime

- macOS
- Bear installed
- `grizzly`
- Bear running for callback-based reads
- optional Bear API token for some write and tag operations

## Good workflow

1. identify the target note or tag
2. prefer search or open before write when the target is fuzzy
3. append or create instead of overwriting by default
4. treat token-backed operations as sensitive local actions

## Useful patterns

```bash
echo "Note content here" | grizzly create --title "My Note" --tag work
grizzly open-note --id "NOTE_ID" --enable-callback --json
echo "Additional content" | grizzly add-text --id "NOTE_ID" --mode append --token-file ~/.config/grizzly/token
grizzly tags --enable-callback --json --token-file ~/.config/grizzly/token
grizzly open-tag --name "work" --enable-callback --json
```

## Caution

Bear writes are real writes. Do not bulk-edit or append to notes without a clear target, and do not assume token-backed operations are available unless the local setup actually supports them.
