---
name: macos-local-voice
description: Local speech-to-text and text-to-speech on macOS using Apple-native speech tools, with offline operation and explicit voice readiness checks.
source:
  upstream: https://github.com/openclaw/skills/tree/main/skills/strrl/macos-local-voice
  reviewed: 2026-04-15
review:
  recommendation: include
  rationale: Clear offline value, transparent dependencies, and a small understandable bundle centered on local speech workflows.
platform: macOS
---

# macOS Local Voice

A reviewed local voice helper for macOS.

## Why keep this

- useful for private on-device STT and TTS
- clear split between transcription, synthesis, and voice inspection
- honest dependency story: `yap`, `say`, optional `ffmpeg`
- good fit for users who want voice features without cloud APIs

## What I reviewed

- purpose is specific and easy to explain
- upstream instructions are concrete and readable
- bundle shape looks reasonable for this kind of skill, centered on `SKILL.md` plus helper scripts
- no obvious hidden network fetches, secret scraping, or unsafe auto-run behavior in the reviewed material

## Good uses

- transcribing local audio privately
- generating spoken replies offline
- checking whether premium macOS voices are actually installed

## Notable risk level

Low. Main caveat is macOS-only setup friction and dependency installation, not suspicious behavior.
