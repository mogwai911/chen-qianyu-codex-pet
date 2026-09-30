# 陈千语（小陈） · Codex Pet

A soft chibi anime companion for Codex, with black cat ears, long dark hair, a blue cape and a tiny keyboard.

## Install

**Latest calm-loop version:** use the package in this repository. The Petdex online entry has not been updated to this revision, so `npx petdex@latest install chen-qianyu-3` currently installs the previous public version.

The Petdex entry is `chen-qianyu-3`; the package ID remains `chen-qianyu`.

Download [`dist/chen-qianyu-petdex.zip`](dist/chen-qianyu-petdex.zip), or copy the `pet` files locally:

```powershell
$petDir = Join-Path $env:USERPROFILE '.codex/pets/chen-qianyu-3'
New-Item -ItemType Directory -Force -Path $petDir
Copy-Item -LiteralPath './pet/pet.json', './pet/spritesheet.webp' -Destination $petDir -Force
```

Reselect **陈千语（小陈）** in Codex's pet settings to refresh the artwork. Restart Codex if it still displays a cached version.

## 2026-10-01: calmer loops

The animation set adds coordinated body and facial changes, with a small same-hand wave and an affectionate head tilt. The latest revision swaps the idle and waiting artwork: boredom bubbles now play during idle time, while quiet breathing and blinking accompanies the waiting state.

| Native slot | Visible action | Frames |
| --- | --- | ---: |
| `idle` | Bored blink and a small expanding/contracting bubble | 6 |
| `running-right` | Rightward run | 8 |
| `running-left` | Leftward run | 8 |
| `waving` | Same hand stays raised; only the wrist waves | 4 |
| `jumping` | Affectionate head tilt and closed-eye smile, with feet planted | 5 |
| `failed` | Surprise, disappointment and recovery | 8 |
| `waiting` | Quiet breathing and blinking | 6 |
| `running` | Focused typing | 6 |
| `review` | Thoughtful glance and nod | 6 |

Codex still selects the native states; this package maps the artwork to their atlas rows. The six-frame idle and waiting rows were exchanged without redrawing or changing the other seven rows. Each row uses the native timing of its destination state: the idle bubble loop takes 6.6 seconds. Codex controls the fixed frame counts and playback durations.

| Small wave | Affectionate tilt | Bored bubble |
| --- | --- | --- |
| ![Small wave](previews/waving.gif) | ![Affectionate tilt](previews/jumping.gif) | ![Bored bubble](previews/idle.gif) |

![All animation frames](qa/contact-sheet.png)

All nine GIF previews are in [`previews/`](previews/).

## Format and validation

- Codex v1 atlas: 1536 × 1872, 8 columns × 9 rows, 192 × 208 per cell.
- 57 used frames; unused cells are transparent. Lossless RGBA WebP.
- [Atlas validation](qa/validation.json), [frame inspection](qa/review.json) and [state swap verification](qa/state-swap-validation.json) passed. Pixel comparisons confirm the two complete rows exchanged places and the other seven rows stayed unchanged.
- [Edge cleanup](qa/edge-cleanup.json) records the previous approved artwork before this row exchange; its row indexes refer to that earlier layout. No additional image cleanup was applied during the swap.
- [Independent visual review](qa/visual-review.md) checked hand continuity, supported keyboard, planted feet and loop boundaries in the approved artwork. Its introductory note maps the former waiting bubble to the current idle row.
- Browser preview checks confirmed the 4-, 5- and 6-frame sequences wrap to their first frames. Actual desktop state triggers and cache refresh still depend on the installed Codex build.
- Minor limitation: the bubble contracts more visibly between frames 4 and 5 than in its other steps.

Diagnostic references to `extracted-frames/` and `assembly/` describe intermediate files; they are not required for installation.

## License

[MIT](LICENSE).
