---
name: blogwatcher
description: Track blog and RSS/Atom feed updates through the local `blogwatcher` CLI. Use when the user wants a lightweight feed watcher instead of manual site checking.
---

# Blogwatcher

Use `blogwatcher` to monitor blogs and RSS/Atom feeds for new posts.

## Why keep this

- broadly useful and easy to understand
- simple read-oriented workflow
- local tracking with low operational risk
- good fit for recurring research or reading queues

## Expected runtime

- `blogwatcher`
- reachable blog or feed URLs

## Good workflow

1. add or inspect tracked blogs
2. scan for updates
3. review unread articles
4. mark items read only when the user wants state cleanup

## Useful patterns

```bash
blogwatcher blogs
blogwatcher add "My Blog" https://example.com
blogwatcher scan
blogwatcher articles
blogwatcher read 1
blogwatcher read-all
blogwatcher remove "My Blog"
```

## Caution

This is low risk, but it still mutates local watch state. Do not remove feeds or mark everything read unless the user actually wants that cleanup.
