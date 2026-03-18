---
name: obsidian-bases
description: Create and edit Obsidian Bases files with filters, formulas, views, summaries, and note properties. Use when working with .base files, database-like note views, table/card/list layouts, or computed note views in Obsidian.
---

# Obsidian Bases

Work with `.base` files as valid YAML for Obsidian Bases.

## Core workflow

1. Define the scope with filters.
2. Add formulas only where they earn their keep.
3. Configure views for the real job: table, cards, list, or map.
4. Validate YAML before writing.
5. Keep formulas and property names consistent.

## Rules that matter

- Broken YAML breaks everything.
- Quote strings when special characters are involved.
- Guard formulas against missing values.
- Do not reference formulas that are not defined.

## When to read references

- Read `references/FUNCTIONS_REFERENCE.md` only when formula syntax or available functions matter.

## Caution

Bases are powerful, but they get unreadable fast when every view tries to be a spreadsheet, dashboard, and philosophy thesis at once.
