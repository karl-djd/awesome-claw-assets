---
name: caldav-cli
description: Manage multi-account CalDAV calendars from the command line with JSON output and OS keychain-backed credential storage.
source:
  upstream: https://github.com/openclaw/skills/tree/main/skills/cyberash-dev/caldav-cli
  reviewed: 2026-04-15
review:
  recommendation: include-with-caveat
  rationale: Real cross-provider calendar value and good credential-storage notes, but setup is heavier and some flows depend on interactive auth and external provider configuration.
platform: macOS / Linux
---

# caldav-cli

A reviewed CalDAV calendar skill for multi-account command-line use.

## Why keep this

- practical for people who want one CLI across iCloud, Google, Yandex, and custom CalDAV servers
- explicit JSON output makes it automation-friendly
- upstream explains where secrets live and claims OS keychain storage instead of plaintext files
- narrower and more trustworthy than vague "calendar automation" wrappers

## What I reviewed

- scope is clear and not overhyped
- reviewed bundle is small, mainly `SKILL.md` and `_meta.json`
- credential handling notes are better than average for community skills
- no obvious sketchy monetization, wallet behavior, or hidden install bootstrap in the reviewed materials

## Good uses

- listing calendar events across providers
- creating events from scripts or agent workflows
- keeping calendar automation in a standard CLI rather than provider-specific hacks

## Notable risk level

Low to medium. The main downside is setup complexity, especially Google OAuth and provider credentials, not malicious behavior.
