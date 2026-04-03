# Awesome Claw Assets

A curated collection of useful, fun, and reviewable Claw assets.

This repo is for **public-facing assets**.
That means the remote should stay clean:
- `skills/` for useful and interesting skills
- `souls/` for interesting `SOUL.md` style assets

Research notes, triage scratchpads, source comparisons, and other curator-only working files stay local and do **not** belong in the public repo.

## Principles

- keep the public tree clean
- review before commit
- adapt assets into our own versions instead of dumping raw upstream clutter
- prefer quality over quantity
- skip shady, noisy, or unclear stuff

## Structure

```text
awesome-claw-assets/
├── README.md
├── skills/
└── souls/
```

## Status

The repo is being rebuilt around reviewed assets.
Curator notes and in-progress review materials are now kept locally instead of being pushed to GitHub.

## Current reviewed skills

### Skills

- [`skills/apple-mail-search-safe/`](skills/apple-mail-search-safe/) — fast, read-only Apple Mail search on macOS
- [`skills/apple-reminders/`](skills/apple-reminders/) — manage Apple Reminders from a local macOS CLI
- [`skills/audio-transcribe/`](skills/audio-transcribe/) — transcribe local audio files with faster-whisper while keeping originals untouched
- [`skills/bear-notes/`](skills/bear-notes/) — create, search, and update Bear notes on macOS
- [`skills/beeper/`](skills/beeper/) — search local Beeper chat history with read-only thread and message lookup
- [`skills/blogwatcher/`](skills/blogwatcher/) — monitor RSS and blog feeds from a local CLI
- [`skills/brew-audit/`](skills/brew-audit/) — audit Homebrew packages, cleanup opportunities, and doctor warnings on macOS
- [`skills/calctl/`](skills/calctl/) — manage Apple Calendar events from a local macOS CLI
- [`skills/db-readonly/`](skills/db-readonly/) — inspect PostgreSQL or MySQL safely with read-only queries
- [`skills/api-tester/`](skills/api-tester/) — test REST and GraphQL endpoints with explicit assertions and safety checks
- [`skills/broken-link-checker/`](skills/broken-link-checker/) — verify external HTTP/HTTPS links with fast structured checks
- [`skills/cross-validated-search/`](skills/cross-validated-search/) — source-backed web search and lightweight claim verification with explicit evidence reporting
- [`skills/domain-checker/`](skills/domain-checker/) — cross-check domain availability with whois and DNS signals
- [`skills/log-analyzer/`](skills/log-analyzer/) — analyze logs to build incident timelines and isolate root causes
- [`skills/data-validator/`](skills/data-validator/) — validate exports and datasets for nulls, duplicates, drift, and freshness issues
- [`skills/contrast-check/`](skills/contrast-check/) — check foreground/background color pairs against WCAG contrast thresholds
- [`skills/defuddle/`](skills/defuddle/) — strip web pages down to clean Markdown before analysis
- [`skills/excel-processor/`](skills/excel-processor/) — inspect, clean, and transform Excel or CSV data without clobbering originals
- [`skills/pdf-analyzer/`](skills/pdf-analyzer/) — extract text, tables, and metadata from PDFs for reading or structured export
- [`skills/qr-generator/`](skills/qr-generator/) — generate QR codes locally from text or URLs
- [`skills/mermaid/`](skills/mermaid/) — render Mermaid diagrams to PNG, SVG, or PDF
- [`skills/macos-reminders/`](skills/macos-reminders/) — manage Apple Reminders from an agent on macOS
- [`skills/testflight-monitor/`](skills/testflight-monitor/) — monitor TestFlight betas and only alert when slots open
- [`skills/agent-hardening/`](skills/agent-hardening/) — synthetic prompt-injection and sanitization smoke tests for agent environments
- [`skills/repomix/`](skills/repomix/) — pack repos into AI-friendly analysis files for structure review and targeted search
- [`skills/trash-cli/`](skills/trash-cli/) — move files to trash instead of permanently deleting them
- [`skills/gtasks-cli/`](skills/gtasks-cli/) — manage Google Tasks from a local CLI once OAuth setup is in place
- [`skills/healthsync/`](skills/healthsync/) — inspect exported Apple Health data with read-only local queries
- [`skills/ical-cli/`](skills/ical-cli/) — manage Apple Calendar with fast reads, explicit writes, and structured export
- [`skills/image-analysis/`](skills/image-analysis/) — extract dominant colors and quick visual cues from screenshots or mockups
- [`skills/homebrew/`](skills/homebrew/) — inspect, install, upgrade, and troubleshoot Homebrew packages on macOS
- [`skills/image-compare/`](skills/image-compare/) — compare two images and generate a diff for visual regression review
- [`skills/claw-diary/`](skills/claw-diary/) — keep a local agent diary with daily summaries, replay views, and searchable history
- [`skills/excalidraw-canvas/`](skills/excalidraw-canvas/) — render quick Excalidraw-style diagrams to PNG with an editable follow-up link
- [`skills/a11y-auditor/`](skills/a11y-auditor/) — scan HTML and JSX for obvious accessibility issues before review
- [`skills/apple-photos/`](skills/apple-photos/) — browse Apple Photos metadata, albums, people, and export requested photos on macOS
- [`skills/agent-audit/`](skills/agent-audit/) — audit OpenClaw model usage, cron spend, and likely savings with read-only recommendations
- [`skills/focus-mode/`](skills/focus-mode/) — keep a work session on one goal with gentle drift detection and parked tangents
- [`skills/redline/`](skills/redline/) — monitor Claude/OpenAI usage windows and pace work before hitting rate limits
