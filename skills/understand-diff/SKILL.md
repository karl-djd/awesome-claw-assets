---
name: understand-diff
description: Analyze a git diff against an existing knowledge graph to map blast radius, affected layers, and review risk before merging.
source:
  upstream: https://github.com/TerminalSkills/skills/tree/main/skills/understand-diff
  reviewed: 2026-04-05
review:
  recommendation: include with caveat
  rationale: Strong code-review value with a concrete graph-first workflow and no bundled scripts, but it depends on a separately generated `.understand-anything/knowledge-graph.json` and is useless without that prerequisite.
platform: cross-platform / git repo with understand-anything graph
---

# Understand Diff

Figure out what a diff actually touches before someone waves it through and ships a surprise outage.

## Why keep this

- clear review job: changed files, affected nodes, touched layers, and risk summary
- encourages efficient inspection instead of dumping an entire graph into context
- good fit for PR review, refactor review, and blast-radius estimation
- doc-only bundle in the reviewed upstream snapshot; no hidden installers or opaque payloads

## Expected runtime

- git repo with an existing `.understand-anything/knowledge-graph.json`
- grep-style search over JSON plus normal git diff access
- works best when the graph is reasonably fresh

## Typical usage

```bash
git diff main...HEAD --name-only
rg 'src/auth/session.ts' .understand-anything/knowledge-graph.json
```

## Bundle / safety notes

- reviewed upstream bundle is a single `SKILL.md`
- no obvious credential handling, background automation, or network fetches
- main risk is analytical drift: stale graphs can make the output confidently wrong

## Caveat

- Keep the prerequisite explicit. If the graph does not exist or is stale, stop and say so instead of pretending the analysis is solid.
