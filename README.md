# WebGL Image Viewer

**Live demo:** https://gagikh.github.io/webgl/

A single-file WebGL viewer for inspecting images (logos, graphics) with 3D perspective controls. Useful for previewing how a logo will look when projected onto a broadcast surface (e.g. a football field) at an angle.

## Workflow

1. **Upload** your logo or image.
2. **Adjust the view** — tilt, rotate, zoom, set camera distance, perspective, and logo aspect ratio until the scene matches how the logo will appear in the real broadcast.
3. Click **Preview full size** to open the full-resolution render (default 1920×1080) in a new tab — no need to save and reopen.
4. Right-click the canvas (or the preview tab image) to **Save image** if you want to keep it.

This lets you quickly iterate: tweak settings → preview → tweak again, until the logo quality and perspective look right.

## Run locally

```bash
python -m http.server 8000
```

Then open `http://127.0.0.1:8000/`

## Controls

### Mouse
| Action | Effect |
|--------|--------|
| Drag up/down | Tilt the image forward/backward (X rotation) |
| Drag left/right | Rotate the image left/right (Y rotation) |
| Scroll | Zoom in/out |
| Shift + Scroll | Adjust perspective |

### UI controls
| Control | Description |
|---------|-------------|
| **Upload image** | Load a local image file |
| **Capture width / height** | Internal canvas resolution (default 1920×1080) |
| **Logo aspect** | Override the logo's display aspect ratio in the scene; "Native" uses the image's real pixel ratio |
| **Zoom** | Scale the image (0.2–20) |
| **Cam dist** | Camera distance — higher = weaker foreshortening (0.3–10) |
| **Perspective** | Foreshortening strength — higher = more dramatic depth effect (0.1–2.0) |
| **Apply size** | Apply the capture width/height to the canvas |
| **Reset view** | Restore default zoom, camera, perspective, and rotation |
| **Preview full size** | Open the current render at full canvas resolution in a new tab |

## Getting the broadcast field look

1. Load a bird's-eye or flat image of the field/surface.
2. Drag **downward** to tilt the image (bottom becomes near, top becomes far).
3. Increase the **Perspective** slider to strengthen the foreshortening.
4. Adjust **Cam dist** to control how dramatically depth falls off with distance.
5. Click **Preview full size** to check how the logo reads at 1920×1080.

## Logo quality guidelines

- Design logos close to their final display size to avoid heavy downscaling.
- For a logo displayed at ~half of a 1080p screen height, target **500–800 px tall**.
- Avoid extremely tall/narrow logos (e.g. 160×2667) — they must be heavily scaled and lose detail.
- Keep text well-spaced; tight or heavy lettering blurs badly after downscaling.
- Use **Logo aspect** to force the logo to the intended display ratio if the file's native size is unusual.
