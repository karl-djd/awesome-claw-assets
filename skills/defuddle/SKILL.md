---
name: defuddle
description: Extract clean Markdown from web pages with Defuddle, removing navigation and clutter before analysis or summarization. Use when the user wants readable content from an article, documentation page, blog post, or other standard web page and Defuddle is available locally.
---

# Defuddle

Use Defuddle when a normal webpage should be turned into clean Markdown before analysis.

## Default command

```bash
defuddle parse <url> --md
```

## Good uses

- documentation pages
- blog posts
- articles
- reference pages where boilerplate wastes tokens

## Tips

- Prefer Markdown output.
- Save to a file when the content will be reused.
- If metadata alone is needed, request only the property you need.

## Caution

Use this only when `defuddle` is already available. Do not turn a simple fetch into an installation adventure unless the user explicitly wants that.
