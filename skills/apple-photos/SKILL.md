---
name: apple-photos
description: Browse Apple Photos metadata, albums, people, and exports from macOS with explicit local scripts.
source:
  upstream: https://github.com/openclaw/skills/tree/main/skills/tyler6204/apple-photos
  reviewed: 2026-04-03
review:
  recommendation: include with caveat
  rationale: Strong local-only utility for Apple users with a clear command set, but it depends on Full Disk Access and can export personal photos, so privacy expectations must stay explicit.
---

# Apple Photos

Use this for local Apple Photos lookup on macOS: list albums, inspect recent photos, search by person/date/content, and export a specific image when the user actually wants it.

## Why keep this

- clear real-world value for Apple users
- local-first workflow instead of cloud scraping
- command set is small and understandable
- read-oriented by default, with export as an explicit step

## What I reviewed

- purpose is narrow and easy to explain
- bundle behavior appears transparent from the documented scripts
- no obvious prompt-hijack or auto-action nonsense
- privacy boundary is visible: the skill requires Photos library access

## Caveat

This skill touches very personal data. Reading metadata is already sensitive, and exporting a photo is more sensitive still. Keep it, but only for explicit user requests and only with privacy-aware handling.

## Good uses

- album or library overview
- find photos by person/date/content
- inspect metadata before export
- export a single requested photo to a known temp path

## Notable risk level

Low technical risk, moderate privacy risk.
