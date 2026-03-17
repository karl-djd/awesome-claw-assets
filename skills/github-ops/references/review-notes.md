# Review notes for upstream GitHub skills

## 1) conorkenn/openclaw-github-assistant

### What it is
A GitHub API-oriented skill bundle with compiled JavaScript files (`index.js`, `api.js`, `test.js`).

### What is good
- More complete than a pure markdown stub
- Covers repo listing, repo inspection, CI status, issue creation, repo creation, search, and PR creation
- Uses direct GitHub API calls instead of pretending browser automation is enough for everything

### Risks / caveats
- Requires `GITHUB_TOKEN` and often `GITHUB_USERNAME`
- Token-heavy setup is less aligned with this machine now that browser auth + SSH already work
- Frontmatter contains extra metadata fields beyond the minimal spec style we prefer locally
- Quality is acceptable, but it feels like a generic integration rather than a workflow tuned to our machine

### Security review
- No obvious malware or destructive script behavior found in the inspected files
- No hidden downloader, shell exec chain, persistence logic, or obvious payload
- Main code path is straightforward GitHub API fetch logic
- `test.js` imports `child_process` but does not do anything suspicious with it in the inspected file

## 2) steipete/github

### What it is
A very small SKILL.md-only GitHub skill centered on the `gh` CLI.

### What is good
- Clean and direct
- Practical examples for PR checks, runs, and `gh api`
- High signal-to-noise ratio

### Risks / caveats
- Too thin for a primary workflow skill
- Assumes `gh` CLI exists
- On this machine, `gh` is currently not installed, so it is not a reliable default path

### Security review
- No script payload at all in the downloaded bundle
- Essentially safe as documentation, but incomplete for our local needs

## Why build our own

Our actual environment is different from both upstream skills:

- GitHub is already authenticated in Chrome
- Git over SSH is configured and working
- `gh` CLI is absent
- We want a workflow skill, not just a token setup guide or a tiny command cheat sheet

So the local skill should prioritize:

1. local git over SSH
2. browser-authenticated GitHub UI operations
3. explicit verification of success
4. no dependency on `gh` unless installed later
