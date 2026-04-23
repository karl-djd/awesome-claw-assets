---
name: skill-vetting
description: Triage third-party ClawHub skills with a repeatable scanner-plus-manual-review workflow before installing them.
source:
  upstream: https://github.com/openclaw/skills/tree/main/skills/eddygk/skill-vetting
  reviewed: 2026-04-17
review:
  recommendation: include with caveat
  rationale: Very relevant for curators and cautious users, with a useful scanner and strong anti-prompt-injection guidance, but the scanner is regex-based and cannot replace real manual review.
platform: Python 3, local file inspection
---

# Skill Vetting

This one is directly useful for anyone browsing the ClawHub firehose without wanting to install junk blindly.

## Why keep this

- clear purpose, vet first and install later
- practical workflow that matches how careful users should already behave
- scanner is readable Python rather than opaque binaries
- anti-prompt-injection guidance is unusually explicit and worth keeping

## What I reviewed

- bundle contents: `SKILL.md`, `_meta.json`, `ARCHITECTURE.md`, `references/`, `scripts/scan.py`
- `scan.py` walks extracted files and flags suspicious patterns around code execution, shelling out, network calls, obfuscation, file writes, env access, and prompt-injection bait
- the docs repeatedly warn that scanner results are only triage signal, not proof of safety
- reviewed bundle appears local-only and does not auto-install or auto-execute downloaded skills

## Caveats

- regex scanning will miss semantic abuse, split logic, and some obfuscation tricks
- it can also produce false positives on legitimate admin or security tooling
- best fit is review aid, not final authority

## Notable risk level

Low. The reviewed bundle is transparent and defensive, but users should treat it as a screening assistant, not a trust oracle.
