---
name: github-asset-curation
description: Curate Claw assets from GitHub by finding source repositories, cloning them locally, picking promising skills or souls, reviewing them for safety and usefulness, adapting them into local assets, and only then committing and pushing to the public repo. Use when maintaining the awesome-claw-assets workflow or doing similar GitHub-based asset discovery, review, adaptation, and publishing work.
---

# GitHub Asset Curation

Use this skill to run the full GitHub-based curation loop for `awesome-claw-assets`.

## Goal

Turn promising upstream GitHub assets into reviewed public assets.

Public repo stays clean.
Research and scratch work stay local until review is done.

## Public repo rules

The public repository should focus on:
- `skills/`
- `souls/`

Do **not** push curator-only working materials such as:
- source comparison notes
- shortlist drafts
- raw triage files
- review scratchpads
- bulk upstream mirrors

Keep those in ignored local storage.

## Default workflow

### 1) Find sources on GitHub

Look for repositories that are:
- useful
- clear in scope
- maintained enough to trust for review
- relevant to normal users, not just niche hype sludge

Prefer:
- curated lists
- focused skill libraries
- product-specific high-signal repos
- tooling that helps quality or validation

Be skeptical of:
- spammy mega-lists
- crypto/trading/wallet junk
- unclear repos with flashy claims and weak substance
- anything with suspicious binaries, installers, or hidden scripts

### 2) Clone sources locally

Clone candidate source repos into local GitHub workspace storage, for example under:
- `~/Documents/github/`

Prefer local inspection over repeated browser clicking.
It is faster, cheaper, and less annoying.

If a repo already exists locally, update it instead of recloning.

### 3) Pick candidates from the source

Browse the local source repo and identify candidate skills or souls.

Selection filters:
- understandable value
- good fit for general users or clearly valuable niche users
- low obvious security risk
- clean structure
- realistic dependencies
- adaptable to our repo style

Do not pick something just because it is popular.

### 4) Save picks into local review area

Before public inclusion, place candidates into a local review area.
Keep this area outside the public tree or inside an ignored local folder.

Suggested pattern:
- `.local/review/...`

At this stage, it is fine to keep:
- copied snapshots
- review notes
- shortlist files
- source provenance
- comparison drafts

This is **local review**, not public publishing.

### 5) Review and adapt

Review every picked asset before public inclusion.

Check for:
- suspicious scripts
- credential grabbing
- wallet/trading behavior
- unsafe write behavior
- opaque automation
- misleading setup steps
- poor portability
- over-specific assumptions

Improve where needed:
- tighten the description
- simplify the workflow
- remove noisy or unsafe instructions
- reduce unnecessary dependencies
- move bulky details into `references/` only when they are genuinely useful
- keep frontmatter minimal: only `name` and `description`

Reject assets that are:
- unsafe
- unclear
- too brittle
- mostly hype
- not worth the maintenance burden

### 6) Publish only after review

Only after review is complete:
- place approved assets into `skills/` or `souls/`
- keep the public repo tidy
- commit
- push
- tell 公子 what was added and why

Never use the public repo as a scratchpad.

## Review checklist

Before publishing, confirm:
- scope is clear
- value is real
- security risk looks acceptable
- no junk files are being pushed
- local review materials remain local
- the asset feels like something worth maintaining

## Good habits

- review first, commit later
- preserve provenance locally
- prefer adapting upstream work into our own clean version
- favor quality over quantity
- keep the public repo legible at a glance

## When to read references

Read `references/review-checklist.md` when you want a compact audit checklist for deciding whether a candidate should be promoted from local review into the public repo.

## Caution

If the repo starts looking like a landfill, the process failed. The whole point is to keep the public surface clean and trustworthy.
