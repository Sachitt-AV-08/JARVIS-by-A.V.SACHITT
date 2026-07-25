[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Glossary/HTML5)
[![Three.js](https://img.shields.io/badge/Three.js-000000?style=flat&logo=three.js&logoColor=white)](https://threejs.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![COSMIC Ecosystem](https://img.shields.io/badge/COSMIC-Ecosystem-blue.svg)](https://github.com/Sachitt-AV-08)

# J.A.R.V.I.S — Holographic Interface

A browser-based holographic interface inspired by the Iron Man JARVIS system. Renders 3D planet holograms over a live webcam feed with hand tracking, voice commands, and custom GLSL shaders.

## Features

- **Holographic rendering** — Custom GLSL scan-line, rim-light, and atmospheric glow shaders over webcam feed
- **4 interactive objects** — Earth (with clouds + normal map), Mars, Moon, and Crystal (wireframe icosahedron)
- **Hand tracking** — MediaPipe Hands for real-time palm tracking, pinch-to-zoom, and two-hand grab gestures
- **Voice commands** — Web Speech API for object switching, zoom, and reset ("show earth", "zoom in", "reset matrix")
- **HUD overlay** — FPS counter, clock, hand status, tracking mode, object scale — all live-updating
- **Loading sequence** — Animated boot screen with progress bar and system status messages
- **Keyboard controls** — 1-4 for object switch, full responsive viewport

## Quick start

```bash
# Serve locally (needs HTTPS for webcam)
npx serve .
# Open index.html in browser, allow camera access
```

## How it works

1. Webcam feed is rendered as a fullscreen `<video>` background
2. Three.js renders transparent holographic objects on a `<canvas>` overlay
3. Custom GLSL shaders add scan-lines, atmospheric glow, rim lighting, and orbital rings
4. MediaPipe Hands detects palm position for translate and pinch gestures for zoom
5. Web Speech API processes voice commands for hands-free control

## Tech stack

- **Three.js** r162 — 3D rendering, shaders, geometry
- **MediaPipe Tasks Vision** — Real-time hand landmark detection
- **Web Speech API** — Browser-native voice recognition
- **Pure HTML/CSS/JS** — Zero build step, single `index.html`

## Objects

| Key | Object | Shader |
|-----|--------|--------|
| 1 | Earth | Phong + normal map + cloud layer + blue atmospheric glow |
| 2 | Mars | Phong + rust-colored rim |
| 3 | Moon | Phong + subtle grey rim |
| 4 | Crystal | Translucent icosahedron + wireframe overlay |

## License

MIT
