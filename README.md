# Night-Shift 
A first-person stealth-horror game for the browser, built with three.js (r160). You are the night guard: collect every fuse on each floor to restore power, then reach the exit beam. Patrolling Wardens hunt you by sight and sound. Your flashlight is both your eyes and your only weapon: hold it on a Warden for ~1 s to stun it. Survive 5 floors.
Run
ES modules need an HTTP server (opening `index.html` via `file://` will not work). Needs internet once, because three.js loads from jsDelivr.
```bash
git clone <your-repo-url> && cd night-shift
npm start            # or: python3 -m http.server 8000   -> http://localhost:8000
```
Deploy: push to GitHub, then Settings -> Pages -> deploy from `main` / root.
Offline: `npm i three@0.160.0` and point the two importmap URLs in `index.html` at `node_modules/three/build/three.module.js` and `node_modules/three/examples/jsm/`.
Controls
WASD/Arrows move, Mouse look, Shift sprint (loud, uses stamina), F flashlight, Esc/P pause.
Layout
`src/main.js` flow, HUD, rendering, input | `level.js` maze generation, collision, pathfinding, pickups | `player.js` | `enemy.js` AI | `particles.js` | `audio.js` procedural WebAudio.
Limitations
Single-player only. The only persistence is `localStorage` (settings + best score). Levels use procedural placeholder geometry and textures (no external assets). Mobile/touch controls are not implemented. Gamepad is not supported.
