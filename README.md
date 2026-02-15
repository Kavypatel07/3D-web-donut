# 3D-web-donut - Interactive 3D Landing Page

A modern, immersive landing page featuring a 3D donut model as a fully interactive WebGL background, built entirely in a single HTML file.

---

## Preview
![Animation](https://github.com/user-attachments/assets/a9521900-cb04-457c-abf8-a56021e823ab)
![Animation-Perview](https://github.com/user-attachments/assets/c1623b6c-1fc6-4a68-ad39-6d0a51d442c3)


| Landing Page | Video Player |
|---|---|
| Bold hero text with auto-rotating 3D model | Cinematic frosted-glass video overlay |

---

## Features

### 3D Interactive Background
- Real-time 3D `.glb` model rendered with **Three.js** and **WebGLRenderer**
- Full-screen fixed canvas sitting behind all UI elements
- Auto-rotation on the Y-axis with smooth damping for a premium feel
- Click-and-drag to manually orbit the model
- Zoom and pan are disabled to protect the layout

### Studio-Grade Lighting
- **Ambient Light** for soft base illumination
- **Spot Light** with shadow casting for depth and realism
- **Directional Fill Light** to eliminate harsh shadows
- **Rim Point Light** (warm gold) for edge highlights
- ACES Filmic tone mapping for cinematic color grading



### Loading Experience
- Centered spinner animation with progress percentage counter
- Animated progress bar tracking real-time asset loading
- Smooth fade-out transition once the model reaches 100%

### Hero UI Overlay
- Bold, oversized typography with gradient accent text
- Tagline with uppercase letter-spacing
- "Explore" call-to-action button with hover lift effect
- All text uses `pointer-events: none` so users can click through to spin the 3D model

### Cinematic Video Player
- Triggered by the **Explore** button
- Frosted glass backdrop (`backdrop-filter: blur(20px)`)
- Rounded container with golden glow ring border
- Spring scale-up entrance animation
- "Now Playing" title bar with animated pulse indicator
- Corner accent bracket detail
- Close via button, click outside, ESC key, or video end

---

## Tech Stack

| Technology | Purpose |
|---|---|
| **HTML5 / CSS3** | Structure and styling (single file) |
| **JavaScript (ES Modules)** | Application logic |
| **Three.js v0.160** | WebGL 3D rendering engine |
| **GLTFLoader** | Loading `.glb` 3D model files |
| **OrbitControls** | Camera interaction (rotate, damping) |
| **Google Fonts (Inter)** | Typography |

---

## Project Structure

```
3D-web-donut/
├── index.html          # Complete single-file application
├── donut.glb           # 3D model (GLTF Binary)
├── 0001-0160.mp4       # Video asset for the Explore overlay
└── README.md           # This file
```

---

## Getting Started

### Prerequisites
- [Node.js](https://nodejs.org/) installed on your machine
- A `.glb` 3D model file named `Donut.glb` in the project root
- A video file named `0001-0160.mp4` in the project root

### Run Locally

```bash
# Install dependencies
npm install

# Start the local server
npx serve -l 3000 .
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

---

## Configuration

### Changing the 3D Model
Replace `donut.glb` with any GLTF/GLB file. The loader auto-centers and scales the model to fit the viewport.

### Adjusting Rotation Speed
In `index.html`, modify:
```js
controls.autoRotateSpeed = 2.0; // Higher = faster
```

### Adjusting Camera Angle
```js
camera.position.set(0, 1.2, 3.5);       // x, y, z position
controls.minPolarAngle = Math.PI * 0.3;  // Min vertical angle
controls.maxPolarAngle = Math.PI * 0.65; // Max vertical angle
```

### Lighting Tweaks
```js
ambientLight.intensity = 0.8;  // Base light strength
spotLight.intensity = 60;      // Key light strength
renderer.toneMappingExposure = 1.2; // Overall brightness
```

---
