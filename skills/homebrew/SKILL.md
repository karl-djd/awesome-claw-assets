---
name: homebrew
description: Search, inspect, install, upgrade, and troubleshoot Homebrew packages on macOS.
source:
  upstream: https://github.com/openclaw/skills/tree/main/skills/thesethrose/homebrew
  reviewed: 2026-04-03
review:
  recommendation: include with caveat
  rationale: Very practical and readable for macOS users, but it includes destructive package-management commands so it should be used with explicit user confirmation for installs, upgrades, and removals.
---

# Homebrew

Use Homebrew when the user wants package-manager help on macOS: search formulae, inspect package details, update metadata, troubleshoot brew itself, or install/remove packages with clear confirmation.

## Why keep this

- broadly useful on macOS
- beginner-friendly command surface
- transparent command mapping instead of hidden automation
- good fit for troubleshooting and package discovery

## What I reviewed

- scope is clear: Homebrew package operations only
- instructions are understandable and concrete
- no hidden network fetches beyond normal `brew` behavior
- no suspicious credential handling or opaque scripts

## Caveat

This skill includes write/destructive actions (`install`, `upgrade`, `uninstall`). Keep it, but treat those as user-confirmed operations rather than default moves.

## Good uses

- `brew search` and `brew info` before changing anything
- `brew config` and `brew doctor` for debugging
- guided install/upgrade only after the user says yes

## Notable risk level

Low-to-moderate. The skill itself is transparent, but Homebrew commands can change the machine state.
