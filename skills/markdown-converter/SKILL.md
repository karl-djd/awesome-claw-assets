---
name: markdown-converter
description: Convert documents and mixed file formats to Markdown with `uvx markitdown`. Use when the user wants PDFs, Office files, HTML, CSV, JSON, images, EPUBs, or similar content turned into LLM-friendly Markdown.
---

# Markdown Converter

Use `uvx markitdown` when the user wants a file converted into readable Markdown instead of manually copy-pasting content.

## Why keep this

- broad everyday utility with one clear job
- excellent fit for downstream summarization and extraction workflows
- no opaque bundle logic in the skill itself
- honest dependency story: `uvx` fetches the tool on first run

## Expected runtime

- `uv` / `uvx` available
- local file access to the source document
- optional Azure Document Intelligence credentials for tougher PDF extraction

## Good workflow

1. convert to stdout first when the user only needs inspection
2. write to a new `.md` file when the result should be saved
3. preserve originals; do not overwrite source documents
4. escalate to Azure Document Intelligence only when plain extraction is not good enough

## Useful patterns

```bash
uvx markitdown input.pdf
uvx markitdown report.docx -o report.md
uvx markitdown slides.pptx > slides.md
cat input.pdf | uvx markitdown -x .pdf > output.md
uvx markitdown scan.pdf -d -e "https://your-resource.cognitiveservices.azure.com/"
```

## Caution

First run pulls dependencies from the network, so that behavior should be explicit. Complex PDFs, OCR-heavy scans, audio transcription, and plugin-enabled flows may need extra review before trusting the output blindly.
