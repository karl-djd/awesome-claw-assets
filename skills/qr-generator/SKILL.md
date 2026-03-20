---
name: qr-generator
description: Generate QR codes from text or URLs as PNG, SVG, or terminal ASCII. Best for quick sharing to phones without typing.
source:
  upstream: https://github.com/openclaw/skills/tree/main/skills/autogame-17/qr-generator
  reviewed: 2026-03-20
review:
  recommendation: include
  rationale: Useful for ordinary users, transparent Node bundle, and easy to inspect.
---

# QR Generator

Generate a QR code from plain text or a URL.

## Why keep this

- clear purpose
- small, understandable bundle
- no account, browser, or remote service required
- handy for links, Wi-Fi strings, event codes, and quick handoff to mobile

## Expected runtime

- Node.js
- package deps: `commander`, `qrcode`

## Typical usage

```bash
node index.js --text "https://openclaw.ai" --output qr.png
node index.js --text "WIFI:S:MyWiFi;T:WPA;P:secret;;" --output wifi.svg
node index.js --text "Hello" --terminal
```

## Notes

- `--output` ending in `.svg` writes SVG; other file outputs default to PNG.
- `--terminal` prints ASCII QR directly in the shell.
- Good fit when the user wants something scannable, not just copy-pastable.
