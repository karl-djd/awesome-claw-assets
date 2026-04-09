---
name: mac-tts
description: Speak short messages aloud on macOS with the built-in `say` command and selectable system voices.
source:
  upstream: https://github.com/openclaw/skills/tree/main/skills/kalijason/mac-tts
  reviewed: 2026-04-09
review:
  recommendation: include
  rationale: Clean, tiny, and immediately useful for reminders or spoken alerts, with no extra dependencies beyond standard macOS voice support.
platform: darwin
---

# mac-tts

Use macOS built-in text-to-speech when the user wants a spoken reminder, audible alert, or quick read-aloud through the Mac speakers.

## Why keep this

- extremely clear scope
- zero extra package dependency in normal macOS setups
- practical for reminders, accessibility, and ambient notifications
- upstream instructions stay short and concrete

## What I reviewed

- reviewed upstream bundle is documentation-only (`SKILL.md` + `_meta.json`)
- command surface is just `say` plus optional voice / volume helpers
- no hidden downloads, credential handling, or background hooks in the bundle
- language and voice examples are immediately usable

## Recommended guardrails

- prefer short spoken messages over reading giant walls of text
- warn before loud or unexpected playback in shared spaces
- check or adjust output volume when the user cares about noise

## Good uses

- meeting or timer reminders
- accessibility-friendly spoken status updates
- quick playback of short Chinese or English phrases

## Notable risk level

Low. The main risk is social annoyance, not machine compromise.