---
name: bat-cat
description: Use `bat` as a better `cat` for readable terminal previews with syntax highlighting, line ranges, and git-aware decorations.
source:
  upstream: https://github.com/openclaw/skills/tree/main/skills/arnarsson/bat-cat
  reviewed: 2026-04-11
review:
  recommendation: include
  rationale: Very clear utility skill, tiny low-risk bundle, and immediately useful for file inspection without pretending to be more than it is.
platform: local shell with `bat` installed
---

# bat-cat

A small skill, but a genuinely handy one.

## Why keep this

- dead simple value proposition
- teaches a better default for terminal file reading
- low setup burden on macOS and Linux
- easy for beginners to understand in one glance

## What I reviewed

- bundle contents: `SKILL.md`, `_meta.json`
- install requirements are explicit and normal
- no scripts, hooks, or secret handling
- guidance stays scoped to viewing and formatting files

## Good uses

- previewing config files or code with line numbers
- showing selected ranges from large files
- visually inspecting git changes in a single file
- pairing with ripgrep or fzf for fast terminal review

## Risk level

Low. The main failure mode is assuming `bat` exists everywhere, not hidden behavior in the skill.
