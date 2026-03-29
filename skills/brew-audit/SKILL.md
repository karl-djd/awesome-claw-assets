---
name: brew-audit
description: Audit a macOS Homebrew setup for outdated packages, cleanup opportunities, and doctor warnings before changing anything.
source:
  upstream: https://github.com/openclaw/skills/tree/main/skills/rogue-agent1/brew-audit
  reviewed: 2026-03-29
review:
  recommendation: include
  rationale: Straightforward maintenance utility with transparent shell behavior, read-mostly inspection, and a realistic safety boundary before upgrades.
platform: macOS
---

# Brew Audit

Check Homebrew health before you start mashing upgrade commands like a raccoon in a pantry.

## Why keep this

- concrete everyday value for macOS users
- narrow scope and easy-to-explain output
- upstream bundle is small and legible
- encourages inspection before package changes

## Expected runtime

- macOS
- Homebrew installed
- `brew` available on `PATH`

## Typical usage

```bash
bash scripts/brew-audit.sh
bash scripts/brew-audit.sh --section outdated
bash scripts/brew-audit.sh --section cleanup
bash scripts/brew-audit.sh --section doctor
bash scripts/brew-audit.sh --json --section outdated
```

## Notes

- This is best used as an audit step, not automatic upgrade permission.
- Review `brew doctor` findings before suggesting cleanup or upgrades.
- Good fit for “what needs updating?” or “why is my Homebrew setup crusty?” requests.
- Keep upgrade and cleanup actions separate so the user can see what will change.
