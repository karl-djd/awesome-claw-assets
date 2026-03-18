---
name: obsidian-markdown
description: Create and edit Obsidian-flavored Markdown with wikilinks, embeds, callouts, properties, tags, and note-friendly structure. Use when working with Obsidian notes, vault content, wikilinks, callouts, frontmatter properties, or Markdown files meant for Obsidian.
---

# Obsidian Markdown

Write valid Obsidian-flavored Markdown.

## Default workflow

1. Start with frontmatter only if it adds real value.
2. Use normal Markdown for structure.
3. Use `[[wikilinks]]` for internal vault references.
4. Use callouts and embeds only when they improve readability.
5. Keep note names and links stable and human-readable.

## Rules that matter

- Use `[[Note Name]]` for internal notes.
- Use `[label](https://...)` for external links.
- Use `![[...]]` for embeds.
- Use `> [!type]` callouts for highlights, warnings, notes, todos, and similar blocks.
- Keep frontmatter valid YAML.
- Do not invent Obsidian syntax when standard Markdown is enough.

## When to read references

Read these only when needed:
- `references/PROPERTIES.md` for frontmatter/property details
- `references/EMBEDS.md` for embed variations
- `references/CALLOUTS.md` for callout types and patterns

## Caution

Prefer clean notes over feature soup. Just because Obsidian can render something fancy does not mean the note should turn into a circus.
