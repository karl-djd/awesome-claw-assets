---
name: nb
description: Manage notes, bookmarks, notebooks, and todos with the `nb` CLI. Use when the user wants local note-taking with search, organization, and Git-backed history across one or more notebooks.
---

# nb

Use `nb` when the user wants real notebook operations rather than ad-hoc Markdown files.

## Why keep this

- strong local-first PKM utility
- clear notebook and search model
- Git-backed history is useful and auditable
- cross-platform enough to be more broadly useful than a single-app wrapper

## Expected runtime

- `nb` installed
- existing nb setup or user willingness to initialize one
- note data stored under `~/.nb/`

## Good workflow

1. list notebooks or search before editing when the target is fuzzy
2. use note IDs or exact titles for updates and deletes
3. prefer CLI operations over hand-editing files inside `~/.nb/`
4. treat delete, move, and sync as explicit user actions

## Useful patterns

```bash
nb notebooks
nb list
nb search "query"
nb add -t "Title" -c "Content here"
nb show <id> --print
nb edit <id> -c "New content" --overwrite
nb todo add "Task title"
nb todos open
nb git status
```

## Caution

Do not edit `~/.nb/*` repos by hand. Use the CLI so indexing and Git history stay consistent. `sync`, forced delete, and overwrite flows can mutate real notes and should follow clear user intent.
