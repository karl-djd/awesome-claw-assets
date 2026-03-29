---
name: repomix
description: Pack local or remote repositories into a single AI-friendly file for structure review, grep-based exploration, and token estimation.
source:
  upstream: https://github.com/openclaw/skills/tree/main/skills/yamadashy/repomix
  reviewed: 2026-03-29
review:
  recommendation: include
  rationale: Clear repository-analysis value, well-known upstream tool, and a transparent docs-first wrapper with no hidden automation.
---

# Repomix

Turn a repo into one structured file so an agent can inspect layout, scan for patterns, and estimate token load without blindly opening half the tree.

## Why keep this

- useful for real code-review and repo-mapping work
- supports local folders and remote GitHub repos
- explicit about temp-file output and scope controls
- bundle is small and understandable; the heavy lifting comes from the public `repomix` CLI

## Expected runtime

- Node.js with `npx`
- network access for remote GitHub repos
- temp directory for output files

## Good default workflow

1. Pack to a temp file instead of cluttering the working tree.
2. Use `--compress` for large repositories.
3. Narrow scope with `--include` when the user only cares about part of a codebase.
4. Search the generated output first, then read targeted sections.
5. Report repo structure, token size, and concrete findings rather than dumping the whole blob back.

## Notes

- Best fit for codebase exploration, architecture review, and prep for downstream AI analysis.
- Remote packing is powerful, but it still depends on network fetches and the upstream npm package being available.
- Respect the tool's default secret filtering; overriding that would be stupid unless the user explicitly asks.
