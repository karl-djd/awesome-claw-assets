---
name: pdf-analyzer
description: Extract text, metadata, and tables from PDF files for reading, summarization, or structured export. Use when the user wants to read a PDF, summarize a PDF, pull tables from a PDF, inspect metadata, or convert PDF content into structured text or CSV.
---

# PDF Analyzer

Extract useful content from PDFs without mangling the original file.

## Default workflow

1. Identify the PDF path and the user's goal.
2. Choose the lightest tool that fits the task.
3. Preserve page numbers in results.
4. Export extracted data to a new file, not back into the source PDF.

## Common goals

- full-text extraction
- table extraction
- metadata inspection
- section-focused reading
- concise summary after extraction

## Good habits

- Prefer `pdfplumber` for text and table work.
- Try a fallback tool if extraction quality is poor.
- Flag scanned PDFs that likely need OCR.
- Never pretend a broken extraction is authoritative.

## Caution

Preserve the original PDF. The whole point is to learn from it, not to accidentally turn it into modern art.
