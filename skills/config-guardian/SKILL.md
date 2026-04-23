---
name: config-guardian
description: Apply OpenClaw config changes with backup, validation, and automatic rollback instead of editing live JSON by hand.
source:
  upstream: https://github.com/openclaw/skills/tree/main/skills/abdhilabs/config-guardian
  reviewed: 2026-04-17
review:
  recommendation: include with caveat
  rationale: Strong narrow purpose and readable shell scripts for backup plus rollback, but it still performs live config writes and relies on `openclaw doctor` being a trustworthy validation gate.
platform: bash, OpenClaw CLI
---

# Config Guardian

A sensible guardrail skill for one of the easiest ways to break a local OpenClaw install: sloppy config edits.

## Why keep this

- narrow, understandable job with clear user value
- backup and rollback behavior is easy to explain
- small shell-based bundle, no opaque installer nonsense
- safer default than manual JSON editing for routine config changes

## What I reviewed

- bundle contents: `SKILL.md`, `_meta.json`, `scripts/atomic_apply.sh`, `scripts/validate_config.sh`, `scripts/restore_config.sh`
- main flow copies the config to a timestamped backup, runs `openclaw config set`, then validates with `openclaw doctor --non-interactive`
- failure path restores the previous config via shell trap
- no external network calls or unrelated file scraping in the reviewed scripts

## Caveats

- still a write-capable skill, so it should not be used without explicit user approval
- safety depends on `openclaw doctor` catching bad states that matter in practice
- assumes a standard config location and shell environment

## Notable risk level

Moderate. It is well-scoped and transparent, but any skill that edits live config deserves careful use even when rollback exists.
