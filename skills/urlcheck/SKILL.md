---
name: urlcheck
description: Verify a URL for threat signals and destination-intent mismatch before opening, navigating, downloading, or submitting credentials.
source:
  upstream: https://github.com/openclaw/skills/tree/main/skills/cplusdev/urlcheck
  reviewed: 2026-04-06
review:
  recommendation: include with caveat
  rationale: Clear security-focused workflow for pre-navigation checks with explicit allow/deny handling, but it depends on a separate plugin and is only as useful as that runtime integration actually is.
platform: OpenClaw URLCheck plugin
---

# URLCheck

Check the damn link before you click it.

## Why keep this

- strong, easy-to-explain safety value
- clear decision model: verify first, then proceed or stop
- intent-aware checks are more useful than generic phishing vibes alone
- nice fit for agents that browse, download, or handle login flows

## What I reviewed

- trigger conditions are concrete and sensible
- result handling is explicit (`ALLOW`, `DENY`, `RETRY_LATER`, `REQUIRE_CREDENTIALS`)
- user messaging guidance avoids fake certainty
- no hidden secret collection in the reviewed skill text beyond normal plugin setup

## Caveats

- requires the separate `@cybrlab/urlcheck-openclaw` plugin
- usefulness depends on the plugin staying maintained and available on the host
- weaker fit for minimal installs that already have strict browser restrictions

## Notable risk level

Low to moderate. The workflow is defensive, but it relies on external scan infrastructure and plugin availability.
