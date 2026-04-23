---
name: safe-backup
description: Back up OpenClaw state and workspace into a portable archive while excluding obvious runtime clutter and common secret files.
source:
  upstream: https://github.com/openclaw/skills/tree/main/skills/hacksing/safe-backup
  reviewed: 2026-04-17
review:
  recommendation: include with caveat
  rationale: Clear disaster-recovery value and a readable single backup script, but the produced archive can still contain sensitive workspace data and the documented restore flow is more manual than the name suggests.
platform: bash, rsync, tar
---

# Safe Backup

A practical backup helper for people who want a quick OpenClaw snapshot without shoveling auth files into the archive.

## Why keep this

- obvious real-world value, backup before migration or cleanup
- bundle is small and easy to audit
- script excludes common secrets and runtime junk instead of blindly copying everything
- no hidden network calls or auto-push behavior

## What I reviewed

- bundle contents: `SKILL.md`, `_meta.json`, `scripts/backup.sh`
- `backup.sh` is a straightforward bash script using `rsync` and `tar`
- exclusions cover logs, auth profiles, common key files, caches, and runtime directories
- output stays local in a temp directory unless the user later moves it elsewhere manually

## Caveats

- backup still includes normal workspace content, which may contain sensitive notes or local data
- restore is documented in `SKILL.md` but not bundled as an actual restore script
- depends on `rsync`, so Windows support is really Git Bash or WSL rather than native Windows

## Notable risk level

Low to moderate. The code is readable and local-only, but the archive itself deserves careful handling because “safe backup” does not mean “safe to share.”
