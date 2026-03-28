---
name: testflight-monitor
description: Monitor TestFlight invite links in batch, stay quiet when nothing changed, and alert only when slots open up.
source:
  upstream: https://github.com/jon-xo/testflight-monitor-skill
  reviewed: 2026-03-28
review:
  recommendation: include with caveat
  rationale: Legitimately useful niche tool with readable bash scripts and sane state tracking, but it depends on TestFlight page scraping plus user-specific config/state files.
---

# TestFlight Monitor

Watch TestFlight beta links without manually refreshing Apple pages like a gremlin.

## Why keep this

- clear real-world use case for iOS beta hunters
- batch mode is quiet by default and only announces openings
- readable shell layout with explicit config and state files
- no credential harvesting or hidden background persistence

## Expected runtime

- macOS or Linux shell
- `bash`
- `curl`
- `jq`
- network access to TestFlight pages

## Good workflow

1. Add known TestFlight invite URLs to the monitored list.
2. Run a manual batch check once to establish baseline state.
3. Schedule periodic checks with cron only if the user actually wants monitoring.
4. Announce only state transitions from full to available.

## Notes

- Best fit for users who already know which betas they want to watch.
- Availability detection depends on Apple page text and may break if TestFlight changes its HTML.
- Keep user-specific config and state out of shared repos; they are local runtime artifacts, not public asset content.
