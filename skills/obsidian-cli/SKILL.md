---
name: obsidian-cli
description: Operate a running Obsidian vault through the official CLI for search, notes, tasks, links, properties, templates, plugins, and workspace actions.
source:
  upstream: https://github.com/openclaw/skills/tree/main/skills/adolago/obsidian-cli
  reviewed: 2026-04-11
review:
  recommendation: include with caveat
  rationale: Exceptionally complete and well-scoped for Obsidian power users, with transparent prerequisites and command coverage, but it assumes a live local Obsidian app and includes write-capable operations that need careful targeting.
platform: Obsidian 1.12+, official obsidian CLI, local vault access
---

# Obsidian CLI

This is the heavy-duty Obsidian operations skill.

## Why keep this

- clear target user, people already living in Obsidian
- broad command reference without hiding prerequisites
- covers both read paths and real maintenance tasks
- very strong fit for local knowledge-base workflows on desktop

## What I reviewed

- bundle contents: `SKILL.md`, `_meta.json`
- no hidden scripts, binaries, or install hooks in the bundle itself
- prerequisites are explicit: Obsidian running, CLI enabled, binary in PATH
- command surface is large but organized and concrete

## Good uses

- searching and reading notes from a vault
- task and daily-note workflows
- backlink, property, and workspace inspection
- controlled note creation and updates when the user explicitly wants vault changes

## Caveat

Power cuts both ways. This skill can edit, delete, publish, sync, and alter plugin state, so the operator should default to read-first behavior and confirm broader write actions.
