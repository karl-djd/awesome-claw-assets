# ClawHub source review

## What ClawHub is good for

ClawHub is currently the fastest public discovery surface for OpenClaw skills.
It exposes:
- popularity signals (downloads, stars, installs, versions)
- per-skill detail pages
- downloadable zip bundles
- a built-in security scan summary
- comments that sometimes reveal breakage, malware warnings, or maintenance issues

That makes it useful as a **discovery source**, but not something we should trust blindly.

## Current collection reality

- Homepage fetch works.
- Skill list page is dynamic; plain HTML fetch only returns a loading shell.
- Browser rendering does load the real list.
- As of this review, the non-suspicious list shows **27,065** skills.

## Practical collection method

For ClawHub, browser-based review is the reliable path.

Recommended flow:
1. Open `https://clawhub.ai/skills?sort=downloads&nonSuspicious=true`
2. Prefer beginner-friendly / useful / fun candidates first
3. Open each detail page
4. Check:
   - summary clarity
   - runtime requirements
   - version count
   - built-in security scan text
   - comments for warnings / breakage / spam
   - downloadable bundle contents
5. Download zip and inspect locally in `tmp/clawhub/review/<slug>/`
6. Reject anything with suspicious binaries, hidden payloads, unrelated hooks, credential-grabbing behavior, or sketchy install steps

## Sample review results

### 1) steipete/obsidian
- Category: useful / beginner-friendly
- Bundle contents: `SKILL.md`, `_meta.json`
- Risk level: low
- Notes:
  - Very small bundle; no bundled scripts or binaries
  - Depends on `obsidian-cli`
  - Comments mention a malware warning about an external script by another user and note a CLI rename / maintenance issue
  - So the bundle itself looks clean, but the surrounding ecosystem has drift and some confusion
- Verdict: **keep as a candidate**, but annotate that install/setup should be revalidated before recommendation

### 2) steipete/discord
- Category: useful
- Bundle contents: `SKILL.md`, `_meta.json`
- Risk level: low
- Notes:
  - Mostly usage documentation for a Discord tool
  - No bundled executables or hook scripts
  - Better suited to users already operating inside Clawdbot/OpenClaw
- Verdict: **safe but niche**; keep as a reference skill, not a headline beginner pick

### 3) steipete/spotify-player
- Category: fun / useful
- Bundle contents: `SKILL.md`, `_meta.json`
- Risk level: low to medium
- Notes:
  - Small doc-only bundle
  - Requires Spotify Premium and external CLI tooling
  - Includes browser-cookie import flow via `spogo auth import --browser chrome`, which is not malware, but raises the trust bar because it touches authenticated browser state
- Verdict: **interesting but not default-recommendable for novices**

## Source-level judgment

### Strengths
- Huge surface area
- Good popularity metadata
- Downloadable bundles are easy to diff and inspect
- Comments can expose real-world issues quickly

### Weaknesses
- Dynamic list page makes simple scraping brittle
- Download count alone is not a trust signal
- Comments can contain spam, scams, or unrelated malware bait
- Security scan is useful, but not enough to replace manual review

## Recommendation for this repo

Treat ClawHub as:
- **Tier A discovery source**
- **Tier C trust source**

Meaning:
- great for finding candidates
- not good enough for blind inclusion

## Suggested inclusion rules for ClawHub-derived skills

Only promote a skill into our public shortlist if it passes all of these:
- bundle is readable and small enough to inspect quickly
- no suspicious binaries or opaque payloads
- no hidden hook behavior without clear justification
- no obvious credential, wallet, token, or browser-state abuse
- value is understandable to a beginner or clearly useful in a narrow domain
- setup burden is honest and documented

## Current call

ClawHub is worth keeping in the pipeline, but only with manual review.
It should be treated as a **lead generator**, not as a trusted registry of safe-by-default skills.
