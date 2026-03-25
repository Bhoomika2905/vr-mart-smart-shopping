# 🛒 VR Mart — AI-Powered WebXR Virtual Shopping Experience

> A research-grade immersive retail system combining WebXR, real-time behavioral analytics, and an intelligent recommendation engine — built entirely in the browser with zero dependencies to install.

[![Live Demo](https://img.shields.io/badge/Live%20Demo-GitHub%20Pages-7C4DFF?style=for-the-badge)](https://yourusername.github.io/vr-mart-smart-shopping)
[![WebXR](https://img.shields.io/badge/WebXR-Ready-2ecc71?style=for-the-badge)](https://immersiveweb.dev/)
[![Three.js](https://img.shields.io/badge/Three.js-r128-blue?style=for-the-badge)](https://threejs.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)](LICENSE)

---

## 📸 Screenshots

> _(Add screenshots of your VR store, product panel, and analytics dashboard here)_

---

## 🎯 Project Overview

VR Mart is a browser-based virtual supermarket that demonstrates how **immersive commerce** can be enriched with **AI-driven behavioral intelligence**. It tracks real-time shopper behavior, delivers smart in-session recommendations, and generates a full post-session analytics report for shopkeepers.

This project was built to explore the intersection of:
- **Extended Reality (XR)** interfaces for retail
- **Behavioral analytics** and attention tracking
- **Collaborative filtering** for product recommendations
- **Real-time ML nudges** to influence purchase decisions

---

## ✨ Features

### 🛍️ VR Shopping Environment
- Fully walkable 3D supermarket built with **Three.js**
- 12 products across 6 shelf units with dynamic lighting and shadows
- **WebXR API** support — works on Oculus Quest, HTC Vive, and any WebXR-compatible headset
- Crosshair-based gaze selection with hover-to-highlight interaction
- Works in desktop browser with mouse + keyboard (no headset required)

### 🤖 Real-Time AI Recommendation Engine
- **Alternative brand suggestions** shown inside product panels (cheaper + premium options)
- **Price comparison** with exact savings/premium displayed
- **Popularity badges** — Best Seller 🔥, Popular ⭐, Low Stock ⚠️
- **Collaborative filtering** — "Customers who bought X also bought Y"
- **Smart nudge system** triggered at hesitation time thresholds:
  - `5s` — Social proof + stock urgency
  - `10s` — Cross-sell recommendation
  - `16s` — Prompt to explore alternatives
  - `24s` — Price-drop alert

### 🧠 Behavioral Analytics Engine
Tracks every micro-interaction during the session:

| Signal | What's measured |
|--------|----------------|
| **Gaze time** | Seconds crosshair was on each product |
| **Hesitation score** | Panel open time without purchase |
| **Inspect rate** | Products clicked vs products walked past |
| **Nudge response** | Which nudges triggered, at what dwell time |
| **Rec clicks** | How many alternative recommendations were explored |
| **Purchase funnel** | Viewed → Inspected → Added → Purchased |

### 📊 Shopkeeper Intelligence Dashboard
Post-session dashboard with:
- **8 KPI cards** (conversion rate, spend, hesitation count, nudges shown, etc.)
- **Attention heatmap** — ranked gaze time per product
- **Purchase funnel** visualization
- **Hesitation analysis table** — color-coded by severity
- **Spend breakdown** doughnut chart (Chart.js)
- **Behavioral timeline** — full event log with timestamps
- **AI-generated insights** — actionable recommendations for the shopkeeper

### 🎯 Post-Purchase Personalization
After checkout, generates a personalized "You might also like" section based on:
- Collaborative filtering from purchase history
- Hesitation data (products considered but not bought)

---

## 🛠️ Tech Stack

| Technology | Usage |
|-----------|-------|
| **Three.js r128** | 3D scene rendering, geometry, lighting, shadows |
| **WebXR API** | Immersive VR session management |
| **Chart.js 3.9** | Analytics dashboard charts |
| **Vanilla JS (ES6)** | All game logic, analytics engine, recommendation engine |
| **HTML5 / CSS3** | UI panels, HUD, dashboard |

> **Zero build tools. Zero frameworks. Zero npm.** Single `index.html` file.

---

## 🚀 Getting Started

### Option 1 — Run locally (simplest)
```bash
# Clone the repo
git clone https://github.com/yourusername/vr-mart-smart-shopping.git
cd vr-mart-smart-shopping

# Open directly in Chrome or Firefox
open index.html
```

### Option 2 — Live server (recommended for WebXR)
```bash
# Using Python
python -m http.server 8000
# Then open http://localhost:8000

# Or using Node.js
npx serve .
```

### Option 3 — Live demo
Visit the GitHub Pages deployment:
`https://yourusername.github.io/vr-mart-smart-shopping`

---

## 🕹️ Controls

| Action | Control |
|--------|---------|
| Move forward/back/left/right | `W A S D` or Arrow keys |
| Look around | Mouse (click canvas first to lock) |
| Inspect product | Aim crosshair + Click |
| Close panel | `Esc` or ✕ button |
| Add to cart | Click "Add to Cart" in panel |
| Proceed to billing | Click "Proceed to Billing" in cart |

---

## 🔬 Research Context

This project addresses key open questions in **immersive retail research**:

1. **Attention tracking without eye-tracking hardware** — using crosshair dwell time as a gaze proxy
2. **Real-time behavioral intervention** — do nudges at hesitation thresholds improve conversion?
3. **Alternative recommendation timing** — when is the optimal moment to show a competing product?
4. **XR vs traditional e-commerce** — does spatial browsing change purchase behavior?

### Potential Extensions
-  Eye-tracking integration (WebXR Eye Tracking API)
-  Multi-user shared VR environment (WebRTC + WebSockets)
-  A/B testing framework for nudge strategies
-  ML model training on aggregated session data
-  Backend API for persistent session storage
-  Voice-based product search (Web Speech API)
-  Haptic feedback on product selection (WebXR Gamepads)
-  Heat-overlay visualization in 3D space

---

## 📁 Project Structure

```
vr-mart-smart-shopping/
│
├── index.html          # Complete application (single file)
│
└── README.md           # This file
```

---

## 🧩 Core Architecture

```
┌─────────────────────────────────────────┐
│              Browser (WebXR)             │
├──────────────┬──────────────┬────────────┤
│   Three.js   │  Analytics   │    Rec     │
│   3D Scene   │   Engine     │  Engine    │
├──────────────┼──────────────┼────────────┤
│  Raycaster   │  Gaze Track  │  Alt Brands│
│  Hover/Click │  Dwell Timer │  Collab    │
│  Movement    │  Timeline    │  Filtering │
│  WebXR API   │  Funnel      │  Nudges    │
└──────────────┴──────────────┴────────────┘
         │               │
         ▼               ▼
   Shopping Flow    Dashboard +
   Billing →        AI Insights
   Checkout
```

---

## 📄 License

MIT License — free to use, modify, and build upon.

---

## 👨‍💻 Author

Built as a research prototype exploring AI-enhanced immersive retail experiences.

> *"The future of shopping is not just virtual — it's intelligent."*
