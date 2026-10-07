# 🕯️ Maze Runner 3D

A lightweight, first-person 3D browser horror game.  
Grab your torch, navigate the dark maze, find the exit lantern, and don't let the entity catch you.

[![Live Demo](https://img.shields.io/badge/Play_Now-Vercel-000000?style=for-the-badge&logo=vercel&logoColor=white)](https://maze-runner-game.vercel.app/)

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![Three.js](https://img.shields.io/badge/Three.js-r128-000000?style=flat&logo=three.js)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![No Build](https://img.shields.io/badge/build-none-brightgreen)
![License](https://img.shields.io/badge/license-MIT-blue)

---

## 🌐 Live Demo

Play instantly in your browser:  
👉 **[https://maze-runner-game.vercel.app/](https://maze-runner-game.vercel.app/)**

_No installation or dependencies needed. The game runs natively in desktop and mobile browsers._

---

## 🎮 What Is It?

You wake up at the entrance of a pitch-black maze with only a flickering torch in hand.  
A glowing golden lantern burns at the opposite corner — **that's your way out.**

Something else is inside with you. It navigates through the corridors tile by tile, constantly calculating the shortest route toward your position.

**One touch, and it's game over.**

---

## 🕹️ How to Play

| Action | Key / Input |
|---|---|
| **Move** | `W` `A` `S` `D` or arrow keys |
| **Look around** | Mouse (click the screen to lock pointer) |
| **Sprint** | `Shift` |
| **Release mouse** | `Esc` |
| **Enter maze** | Click **Enter** on the title screen |

> 🎧 **Headphones recommended:** Ambient drones and catch alerts are synthesized live for maximum atmosphere.

**Objective:** Reach the **golden lantern** at the far corner of the maze. The ghost is persistent, but taking an efficient route gives you the edge.

---

## 🚀 How to Run Locally

### Option 1: Direct File Launch

1. Download or clone this repository.
2. Open `index.html` in any web browser.

> **Note:** Browsers may block local audio files (`scream.mp3`) under `file://`. If so, the built-in procedural Web Audio synthesizer takes over seamlessly.

### Option 2: Local HTTP Server (Recommended)

Run a local development server from your terminal:

```bash
# Python 3
python -m http.server 8000
```

Then visit [http://localhost:8000](http://localhost:8000) in your browser.

## 📁 Project Structure

```text
maze-runner-3d/
├── index.html   # Complete game (HTML, CSS, and JavaScript engine)
├── scream.mp3  # Jump-scare sound effect (optional fallback included)
└── README.md   # Project documentation
```

## ✨ Core Features & Technical Highlights

- 🎯 **First-person controls:** Smooth WASD movement integrated with pointer lock controls.
- 🔥 **Dynamic torch light:** Procedural flame system made of stacked geometric cones that reacts dynamically to movement and entity proximity.
- 👻 **A* pathfinding AI:** Real-time pathing using an A* search algorithm with a binary-heap priority queue.
- 🗺️ **Live minimap:** Displays the maze grid layout alongside player and entity tracking in real time.
- 🎚️ **Multiple difficulties:** Easy, Moderate, and Difficult modes scaling maze size, entity speed, and grace windows.
- 🏆 **Local leaderboard:** Saves your top 10 fastest escape records directly in `localStorage`.
- 🔊 **Procedural Web Audio:** Background drones, heartbeats, and alert tones are generated using the Web Audio API without relying on external media files.
- 🚀 **Instanced mesh rendering:** Optimized WebGL batching to maintain 60 FPS across desktop and mobile browsers.

## 🎚️ Difficulty Levels

| Level | Maze Size | Ghost Speed | Grace Period | Focus |
|---|---|---|---|---|
| **Easy** | Small | Slow | 6 seconds | Route learning and casual exploration |
| **Moderate** | Medium | Balanced | 4 seconds | Standard balanced experience |
| **Difficult** | Large | Fast | 2 seconds | High-intensity survival |

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| **3D rendering** | [Three.js r128](https://threejs.org/) / WebGL |
| **Logic** | Vanilla JavaScript (ES6+) |
| **Styling** | Native CSS3 |
| **Audio** | Web Audio API |
| **Storage** | Browser `localStorage` |

## 🎨 Engine Customization

Gameplay constants can be tweaked near the top of the `<script>` tag inside `index.html`.

### Difficulty Tuning

```javascript
const DIFF = {
  easy: { base: 11, espd: 1.8, grace: 6 },
  moderate: { base: 13, espd: 2.3, grace: 4 },
  difficult: { base: 17, espd: 3.0, grace: 2 }
};
```

### Player Speed Settings

```javascript
const sp = (keys.ShiftLeft || keys.ShiftRight) ? 6.4 : 4.2;
```
