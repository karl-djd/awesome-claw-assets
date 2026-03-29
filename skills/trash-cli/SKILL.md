---
name: trash-cli
description: Move files to the system trash instead of permanently deleting them, with restore and cleanup commands when needed.
source:
  upstream: https://github.com/openclaw/skills/tree/main/skills/xlionjuan/trash-cli
  reviewed: 2026-03-29
review:
  recommendation: include
  rationale: Extremely practical, safety-improving, and easy to inspect; it encourages recoverable deletion instead of destructive `rm` habits.
---

# Trash CLI

Delete more like a grown-up: move files to trash first, restore if needed, empty later when you're sure.

## Why keep this

- directly reduces accidental data loss
- tiny and easy to explain
- offers a full recovery workflow, not just deletion
- broadly useful on any machine where the CLI is installed

## Expected runtime

- `trash-cli` binaries such as `trash-put`, `trash-list`, and `trash-restore`
- a desktop or freedesktop-compatible trash location

## Good default workflow

1. Use `trash-put` for recoverable deletion.
2. Check `trash-list` before claiming something is gone.
3. Use `trash-restore` for reversals.
4. Only use `trash-empty` when the user clearly wants irreversible cleanup.

## Notes

- This is a safety skill first, not a cleanup flex.
- The upstream docs are transparent and match the actual command set.
- One caveat: some install notes are Linux-leaning, so platform-specific packaging guidance may need a quick adjustment on macOS or Windows.
