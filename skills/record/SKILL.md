---
name: record
description: Record microphone audio, screenshots, screen video, and camera captures on macOS from a terminal-first CLI.
source:
  upstream: https://github.com/openclaw/skills/tree/main/skills/atacan/record
  reviewed: 2026-04-15
review:
  recommendation: include-with-caveat
  rationale: Strong utility and clean bundle shape, with unusually explicit consent guidance, but the capability is inherently sensitive because it can record screen, mic, and camera data.
platform: macOS
---

# record

A reviewed capture skill for macOS media workflows.

## Why keep this

- genuinely useful for agents and users who need scripted capture
- output contract is practical: file path on stdout, status on stderr, optional JSON
- upstream docs explicitly require user consent before recording
- references are separated instead of hiding behavior inside a vague prompt blob

## What I reviewed

- positioning is clear: audio, screen, and camera capture
- bundle appears compact: `SKILL.md`, `_meta.json`, and reference docs
- no obvious malware-style payloads or unrelated junk in the reviewed tree
- the skill itself acknowledges privacy sensitivity instead of pretending recording is routine

## Good uses

- timed microphone captures
- screenshots or short screen recordings for debugging
- camera photos or clips when the user explicitly asks

## Notable risk level

Medium, by capability rather than by bundle quality. Keep only with the consent requirement front and center.
