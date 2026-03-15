# 🛺 Autorickshaw Odyssey
### Mumbai Traffic Simulation — Frontend Hackathon Project

> *A city that never repeats itself.*

A browser-based endless survival game set on the streets of Mumbai — from the Worli Sea Face Promenade to the Bandra–Worli Sea Link. Built entirely with vanilla HTML5 Canvas, CSS, and JavaScript. No frameworks. No libraries. One file.

🎮 **[Play Live →](https://YOUR_USERNAME.github.io/autorickshaw-odyssey/)**

---

## 🌆 The Concept

You are an autorickshaw driver navigating the living ecosystem of Mumbai traffic. The city evolves as you drive — streets get faster, the monsoon arrives, night falls, and eventually the road itself changes from the Worli promenade to the elevated Bandra–Worli Sea Link, with the Arabian Sea stretching on both sides.

The city never truly repeats. Every wave, every building window, every rain drop is procedurally generated using value noise seeded by world distance — so no two runs look the same.

---

## 🗺️ Environment Progression

| Distance | Environment |
|---|---|
| 0 – 80 km | **Worli Sea Face Promenade** — sea on the left, stone walkway, umbrella pedestrians, lighthouse |
| 80 – 130 km | **Transition** — promenade fades, Sea Link rises from the water |
| 130 km+ | **Bandra–Worli Sea Link** — elevated bridge, cable-stay pylons, sea on both sides |

---

## 🌧️ City Phases

The game dynamically shifts through 5 phases as you cover more distance:

| Phase | Distance | What Changes |
|---|---|---|
| 🌅 Dawn | 0 km | Sparse traffic, slow speed |
| 🚗 Rush Hour | 160 km | Dense traffic, higher speed |
| 🌧️ Monsoon | 380 km | Heavy rain, puddles, mist, umbrella pedestrians |
| 🌙 Night | 720 km | Dark roads, headlight cones, vivid reflections |
| 🎊 Festival | 1100 km | Coloured sky, lit buildings, maximum chaos |

---

## 🎮 Controls

| Input | Action |
|---|---|
| `A` / `←` | Lane left |
| `D` / `→` | Lane right |
| `Space` | Horn — scatters nearby obstacles |
| `W` / `↑` | Fire turbo boost (requires full bar) |
| `P` | Pause |
| `R` | Restart |
| Swipe left / right | Lane change on mobile |

---

## ✨ Features

- **Procedural sea** — wave shape seeded by distance × time, never repeats
- **Mumbai skyline** — 24 buildings with individually flickering windows
- **Live traffic** — taxis, buses, bikes, trucks, autos moving in both directions
- **Rain system** — drops, ground splashes, puddles, mist layer
- **Umbrella pedestrians** — appear on the promenade during rain phases
- **Worli Sea Face Promenade** — walkway, benches, lamp posts, lighthouse with rotating beam
- **Bandra–Worli Sea Link** — concrete barriers, scrolling cable-stay pylons with aviation blink lights
- **Seamless environment crossfade** — promenade dissolves, Sea Link rises from the water
- **Turbo boost** — collect Boost pickups → press W → cyan speed trail fires
- **Crash flash** — full-screen red pulse on collision + invincibility window
- **Obstacles** that unlock per phase: Vendor, Dog, Pothole, Barrel, Cow, Cart
- **Pickups**: Chai (+10 pts), Coin (+5 pts), Vada Pav (+15 pts), Boost (charges turbo)

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Rendering | HTML5 Canvas API |
| Styling | Vanilla CSS |
| Logic | Vanilla JavaScript (ES6+) |
| Procedural generation | Value noise (custom, no library) |
| Dependencies | **Zero** |
| Build tools | **None** |
| File count | **1** (`index.html`) |

---

## 📁 Project Structure

```
autorickshaw-odyssey/
├── index.html    ← entire game: HTML + CSS + JS (~900 lines)
└── README.md
```

---

## 🚀 Run Locally

```bash
git clone https://github.com/YOUR_USERNAME/autorickshaw-odyssey.git
cd autorickshaw-odyssey
open index.html
```

No `npm install`. No `npm run dev`. Just open and play.

---

## 🧠 Key Frontend Decisions

**Canvas over DOM elements**
Canvas gives per-frame pixel control needed for procedural wave rendering, rain particles, and depth-sorted traffic. DOM-based rendering would require hundreds of absolutely-positioned elements with expensive reflows every frame.

**Zero dependencies**
The game loop runs at 60fps. Framework overhead (virtual DOM diffing, reactivity systems) adds latency with no benefit for a canvas-rendered game. Pure JS also means zero bundle size and instant load — open the file, game starts.

**Value noise over Math.random() for environment**
`Math.random()` produces a different value every call — impossible to create smooth scrolling terrain. Value noise is deterministic given the same input coordinate, so wave shapes are continuous, scrollable, and unique per run without ever looping.

**Responsive layout**
Canvas resizes to its container on window resize. On mobile (≤600px) the game goes full-viewport and swipe gestures replace keyboard input automatically.

---

*Built for [Recode] · Frontend Domain · [Ananya Tare,Priya Sinha,Sayali Shinde / Meowwers]*
