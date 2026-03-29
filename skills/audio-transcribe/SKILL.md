---
name: audio-transcribe
description: Transcribe local audio files with faster-whisper, keeping processing on-device and originals untouched.
source:
  upstream: https://github.com/openclaw/skills/tree/main/skills/aktheknight/audio-transcribe
  reviewed: 2026-03-29
review:
  recommendation: include with caveat
  rationale: Useful local transcription helper with a small readable bundle, but the upstream instructions needed cleanup because they hardcoded a machine-specific path and underexplained runtime setup.
platform: macOS, Linux
---

# Audio Transcribe

Turn voice notes and other audio files into text locally with `faster-whisper`.

## Why keep this

- very common need with clear value
- local processing avoids uploading private audio by default
- tiny bundle: one script plus basic instructions
- easy to adapt for voice notes, interviews, and meeting clips

## Expected runtime

- Python 3
- `faster-whisper`
- enough CPU or GPU resources for the chosen model

## Good workflow

1. Install `faster-whisper` into an isolated Python environment.
2. Start with a small or base model if speed matters.
3. Transcribe a copied file, not the only original.
4. Save transcript output next to your working notes or project files.

## Typical usage

```bash
python3 scripts/transcribe.py /path/to/audio.ogg
```

## Notes

- Keep paths local and explicit; do not bake in host-specific directories.
- Model downloads happen on first use, so the first run may be slower.
- Best for “transcribe this memo” workflows, not as a promise of perfect diarization or studio-grade cleanup.
- Preserve originals and treat transcripts as drafts that may still need a quick human pass.
