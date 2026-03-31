---
name: excalidraw-canvas
description: Render simple Excalidraw-style diagrams to PNG from structured JSON and return an edit URL for later tweaking.
source:
  upstream: https://github.com/openclaw/skills/tree/main/skills/0xartex/excalidraw-canvas
  reviewed: 2026-03-31
review:
  recommendation: include
  rationale: Narrow, understandable diagram utility with a tiny bundle and no hidden local automation.
---

# Excalidraw Canvas

Use this when a user needs a quick diagram, wireframe, or flow sketch without opening a full design tool first.

## Why keep this

- dead simple value proposition
- useful for architecture sketches, process maps, and UI mockups
- tiny bundle surface
- edit URL makes the output easy to hand off

## Expected runtime

- `curl`
- `python3` for decoding the PNG payload
- network access to the hosted render API

## Good default workflow

1. Keep diagrams small and explicit.
2. Save PNG output to a temp path.
3. Return the edit URL with the image.
4. Avoid sending sensitive internal diagrams to the hosted API.

## Useful pattern

```bash
RESULT=$(curl -s -m 60 -X POST https://excalidraw-mcp.up.railway.app/api/render \
  -H "Content-Type: application/json" \
  -H "Accept: application/json" \
  -d '{"elements":[{"type":"rectangle","x":80,"y":80,"width":220,"height":90,"label":"API"}]}' )

echo "$RESULT" | python3 -c "import json,sys,base64; d=json.load(sys.stdin); open('/tmp/diagram.png','wb').write(base64.b64decode(d['png'])); print(d['editUrl'])"
```

## Caution

The renderer is hosted off-box. Fine for ordinary diagrams; stupid for secrets.
