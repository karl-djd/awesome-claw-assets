---
name: git-commit-pro
description: Write accurate, useful git commit messages by inspecting staged changes and matching the repo's commit style. Use when the user wants help staging files, writing a commit message, improving commit quality, or making cleaner conventional commits.
---

# Git Commit Pro

Make commits understandable.

## Default workflow

1. Inspect status and staged diff.
2. If changes are unrelated, split them.
3. Match the repository's existing commit style when possible.
4. Write a short subject that says what changed.
5. Add a body only when it explains useful why.

## Good habits

- Prefer targeted staging over `git add .`.
- Use imperative commit subjects.
- Keep the subject line tight.
- Avoid garbage like `update stuff`.

## Caution

A commit message is not decorative trim. It is the future-you rescue rope when the repo catches fire.
