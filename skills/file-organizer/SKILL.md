---
name: file-organizer
description: Organize and rename files in a messy folder with explicit dry runs, content-aware grouping, and duplicate checks before moving anything.
source:
  upstream: https://github.com/TerminalSkills/skills/tree/main/skills/file-organizer
  reviewed: 2026-04-08
review:
  recommendation: include with caveat
  rationale: Real-world utility is high and the workflow is understandable, but it performs file moves and renames, so dry-run and confirmation discipline matter.
platform: cross-platform
---

# File Organizer

Clean up a chaotic folder without doing dumb irreversible things.

## Why keep this

- common pain point: Downloads folders and shared project dumps turn feral fast
- practical value for both technical and non-technical users
- upstream instructions cover sorting, renaming, and duplicate handling in one place
- easy to demo with a dry run first

## Expected runtime

- any OpenClaw setup with local file access
- optional Python for smarter renaming / duplicate workflows

## Recommended guardrails

1. start with a narrow folder, not a whole home directory
2. preview the rename / move plan first
3. use dry-run mode before actual moves
4. avoid touching synced, system, or application data directories unless the user explicitly asks
5. prefer trash or reversible moves over destructive cleanup

## Bundle / safety notes

- reviewed upstream bundle is documentation-only (`SKILL.md`)
- no hidden binaries, hooks, or secret-handling logic in the bundle itself
- operational risk is real because the skill can move or rename many files quickly
- best used with explicit scope and a reversible plan

## Keep / skip call

Keep with caveat. Good utility, but only when the agent behaves like an adult and previews the blast radius.
