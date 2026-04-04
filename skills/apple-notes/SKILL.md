---
name: apple-notes
description: Manage Apple Notes on macOS through the local `memo` CLI. Use when the user wants to list, search, create, edit, move, delete, or export real Notes.app notes.
---

# Apple Notes

Use `memo notes` when the user wants real Apple Notes operations rather than generic Markdown files.

## Why keep this

- obvious personal productivity value
- narrow app-specific scope
- local-only note workflow
- simple bundle with no suspicious scripts or installers embedded in the skill

## Expected runtime

- macOS
- Apple Notes available
- `memo` installed
- Automation permission granted to the terminal or host app

## Good workflow

1. search or list before writing when the target note is not exact
2. confirm the destination folder before moving notes
3. prefer create or edit for single-note actions instead of broad folder operations
4. be cautious with deletes and note that attachment-heavy notes may not edit cleanly

## Useful patterns

```bash
memo notes
memo notes -f "Work"
memo notes -s "quarterly plan"
memo notes -a "Inbox capture"
memo notes -e
memo notes -m
memo notes -ex
```

## Caution

This skill acts on a real Notes library. Do not delete, move, or rewrite notes without a clear target. Notes with images or attachments may need the GUI instead of CLI editing.
