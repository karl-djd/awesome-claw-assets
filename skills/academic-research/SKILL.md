---
name: academic-research
description: Search scholarly papers with OpenAlex, inspect citation trails, and assemble quick literature-review inputs without needing a paid API key.
source:
  upstream: https://github.com/openclaw/skills/tree/main/skills/rogersuperbuilderalpha/academic-research
  reviewed: 2026-04-11
review:
  recommendation: include with caveat
  rationale: Strong practical research workflow and transparent Python scripts using OpenAlex, but outputs still need human validation because citation counts and auto-clustered themes can create false confidence.
platform: OpenAlex API, local Python scripts
---

# Academic Research

A practical paper-search skill for real literature triage.

## Why keep this

- clear purpose, find papers and build a first-pass review
- no paid key required for the main data source
- scripts are readable and narrowly scoped
- useful for students, researchers, and engineering background work

## What I reviewed

- bundle contents: `SKILL.md`, `_meta.json`, `scripts/scholar-search.py`, `scripts/literature-review.py`
- network behavior is explicit, mostly OpenAlex with optional Unpaywall lookup
- scripts use normal HTTP requests and light retry logic, not opaque installers or hidden hooks
- generated synthesis is opinionated but understandable

## Good uses

- topic exploration before a deeper literature review
- DOI lookup and citation-chain starting points
- assembling a shortlist of open-access papers
- fast background research for technical writing

## Caveat

Treat the generated review as a draft, not authority. Theme clustering and citation-based ranking are helpful shortcuts, but they can overweight popular papers and flatten nuance.
