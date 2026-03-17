---
name: github-ops
description: Operate GitHub repos, issues, pull requests, repository setup, and routine maintenance using the local git CLI plus the authenticated GitHub browser session. Use when creating repos, editing repo metadata, preparing README files, opening issues or PRs, checking workflow/CI pages, reviewing repository pages, or handling GitHub tasks on a machine where browser auth and SSH git access are available but `gh` CLI may not be installed.
---

# GitHub Ops

Use the path that actually exists. Do not fantasize one.

## Local assumptions for this machine

- GitHub is already logged in via Chrome
- Git over SSH is configured and working
- `gh` CLI may not be installed, so do not assume it exists
- Browser automation is useful for GitHub UI tasks
- Local `git` is the default path for clone / commit / push work

## Default operating split

### Use local `git` for

- clone / init / branch / commit / pull / push
- checking remotes and repo status
- preparing local repo structure
- writing files before pushing

### Use the authenticated browser for

- creating repositories in the GitHub UI
- viewing issues, PRs, actions, and repository pages
- editing metadata or settings that are easier in the UI
- tasks that require the logged-in web session

## Guardrails

- Always inspect `git status` before committing
- Do not force-push unless explicitly asked
- Do not create or merge PRs silently
- When editing GitHub via browser, confirm the target repo/owner first
- If a browser action claims success, verify via URL or visible page state instead of vibes

## Repo creation workflow

1. Create the repo in GitHub if it does not exist yet
2. Initialize or connect the local directory
3. Prefer SSH remotes
4. Pull/rebase if GitHub already has an initial commit
5. Push only after local files look sane

Typical commands:

```bash
git init
git remote add origin git@github.com:owner/repo.git
git pull --rebase origin main
git add .
git commit -m "Initial commit"
git push -u origin main
```

## README / repo bootstrap workflow

When bootstrapping a new repo:

1. Write a README first
2. Keep the first commit small and legible
3. Push the minimum working shape before adding complexity

A clean first push usually beats a giant “here's everything” dump.

## Issues and PRs

If `gh` is unavailable:

- use the browser for issue/PR creation and inspection
- use local git for branch prep and commit hygiene
- verify branch names and remote before asking GitHub UI to open or compare anything

## CI / Actions checks

For GitHub Actions or CI:

- open the Actions tab or workflow run page in the browser
- inspect failed jobs visually
- if logs are hard to read in browser automation, fall back to page screenshots or targeted page extraction

## Security notes

- Prefer SSH keys over copy-pasted PATs when local git is enough
- Do not leak private remotes, tokens, or secret values into commits
- Treat third-party GitHub skills like code, not gospel

## Anti-bullshit rule

If `gh` is missing, say it is missing.
If browser auth is the only working route, use it.
If a GitHub UI action was not verified, do not claim it succeeded.
