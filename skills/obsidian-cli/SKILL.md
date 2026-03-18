---
name: obsidian-cli
description: Interact with an Obsidian vault through the Obsidian CLI to read notes, create notes, search content, append text, manage properties, inspect backlinks, and automate vault workflows. Use when the user wants to operate on a real Obsidian vault from the command line.
---

# Obsidian CLI

Use the `obsidian` CLI when the user wants real vault operations instead of generic Markdown editing.

## Core approach

1. Confirm the target vault or file.
2. Prefer read/search before write.
3. Use exact file or path targeting when ambiguity exists.
4. Preserve user content; do not overwrite unless asked.

## Useful patterns

```bash
obsidian help
obsidian read file="My Note"
obsidian search query="term"
obsidian create name="New Note" content="# Title"
obsidian append file="My Note" content="New line"
obsidian property:set name="status" value="done" file="My Note"
obsidian backlinks file="My Note"
```

## Good habits

- Without a clear target, search first.
- Use `vault="..."` when multiple vaults exist.
- Prefer appending or patching over destructive rewrites.
- For plugin/theme debugging, use the CLI developer commands only when Obsidian is already running.

## Caution

This skill acts on a real vault. Do not make silent bulk edits just because the terminal makes it feel easy.
