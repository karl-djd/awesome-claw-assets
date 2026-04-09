---
name: drafts
description: Create, list, inspect, and update Drafts notes on macOS through the local `drafts` CLI.
source:
  upstream: https://github.com/openclaw/skills/tree/main/skills/nerveband/drafts
  reviewed: 2026-04-09
review:
  recommendation: include with caveat
  rationale: Strong note-capture utility with a readable command set and doc-only bundle, but it depends on a local CLI, the Drafts app being open, and write actions should stay explicit.
platform: darwin
---

# Drafts

Use this when the user wants to capture notes, list drafts, append to an existing draft, or run a Drafts action from macOS.

## Why keep this

- real note-taking utility instead of AI fluff
- concrete command examples for create / list / append / replace
- upstream limitations are stated honestly
- good fit for Drafts users who already live in that app

## What I reviewed

- reviewed upstream bundle is documentation-only (`SKILL.md` + `_meta.json`)
- setup expectations are explicit: macOS, Drafts running, Drafts Pro for automation
- command surface is understandable and auditable
- no hidden scripts, binaries, or secret-handling logic in the bundle itself

## Caveat

This is not a zero-setup skill. It is only useful if the `drafts` CLI is installed, Drafts is open, and the user actually uses Drafts. Keep create / replace / action-running steps intentional instead of spraying notes everywhere.

## Good uses

- quick capture into Drafts inbox
- append meeting notes to a known draft
- list drafts by folder or tag before editing
- inspect one draft in structured JSON output

## Notable risk level

Low-to-moderate. The reviewed bundle is clean, but the workflow can create or rewrite note content on the user's machine.