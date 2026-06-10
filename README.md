# WebGL Image Viewer

A simple browser-based WebGL page that lets you upload an image and view it as a projected, perspective-aware surface.

## Features
- Upload an image from disk
- Set a capture size (default 1920x1080)
- Rotate the image by dragging with the mouse
- Zoom in and out with the mouse wheel or zoom slider
- Adjust perspective with Shift + scroll or the perspective slider
- Reset the view at any time

## Run locally
From the project folder, start a simple local server:

```bash
python -m http.server 8000
```

Then open:

```text
http://127.0.0.1:8000/
```

## Controls
- Drag: rotate
- Scroll: zoom
- Shift + scroll: perspective
- Apply size: updates the canvas capture size
- Reset view: restores the default camera view
