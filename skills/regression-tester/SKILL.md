---
name: regression-tester
description: Generate targeted regression tests around a refactor, run them against old and new code, and surface preserved behavior versus real breakage.
source:
  upstream: https://github.com/TerminalSkills/skills/tree/main/skills/regression-tester
  reviewed: 2026-04-05
review:
  recommendation: include
  rationale: Practical and honest testing workflow with explicit before/after verification, strong focus on behavior instead of implementation trivia, and no suspicious bundle contents in the reviewed snapshot.
platform: cross-platform / any git-backed codebase with a runnable test stack
---

# Regression Tester

When someone says "I only refactored it," this is how you check whether they are lying to themselves.

## Why keep this

- strong real-world value after refactors, rewrites, and module splits
- pushes the right habit: test behavior contracts, not internal implementation details
- verifies against both old and new code, which catches fake confidence fast
- framework-agnostic enough to stay useful across JavaScript, Python, Go, and similar stacks

## Expected runtime

- git history that can compare old and new implementations
- a runnable project test command such as `npm test`, `pytest`, or `go test ./...`
- permission to create or edit project tests when the user asks for that work

## Typical usage

```bash
git diff main...HEAD
npm test
pytest
```

## Bundle / safety notes

- reviewed upstream bundle is a single `SKILL.md`
- no hidden scripts, binaries, or credential-related setup in the reviewed snapshot
- main operational risk is workflow friction: checking old and new code may require stash discipline and can be messy in dirty repos

## Review conclusion

- Worth including for code-review and refactor-heavy workflows. It is concrete, teachable, and much less hand-wavy than most "make sure nothing broke" advice.
