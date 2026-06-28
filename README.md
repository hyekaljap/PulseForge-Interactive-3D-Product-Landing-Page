# 🎧 PulseForge — Interactive 3D Product Landing Page

> **"Hear everything. Miss nothing."**
> An immersive, scroll-driven 3D product showcase for next-generation smart biometric earbuds — built with React Three Fiber.

![React](https://img.shields.io/badge/React-19-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![Three.js](https://img.shields.io/badge/Three.js-0.184-black?style=for-the-badge&logo=three.js&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-8-646CFF?style=for-the-badge&logo=vite&logoColor=white)
![Framer Motion](https://img.shields.io/badge/Framer_Motion-12-FF0055?style=for-the-badge&logo=framer&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

---

## 📌 Table of Contents

- [Project Overview](#-project-overview)
- [Live Demo](#-live-demo)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [Getting Started](#-getting-started)
- [Product Specifications](#-product-specifications)

---

## 📖 Project Overview

**PulseForge** is a single-page interactive product landing page for a premium pair of next-generation smart earbuds. The earbuds combine studio-grade **Active Noise Cancellation (ANC)** with continuous medical-grade biometric health sensing — including PPG heart rate, SpO2 blood oxygen, and core temperature — directly from the ear canal. No smartwatch needed.

The website places an interactive, real-time **3D model** at the center of the experience. A scroll-driven narrative guides users from the hero introduction through features, specs, and a pre-order call to action — all within one seamless page.

### 🎯 Target Audience

| Audience | Description |
|---|---|
| 🏃 Active Athletes | Real-time biometrics during workouts without a smartwatch |
| 🎧 Audiophiles & Tech Enthusiasts | Premium ANC and cutting-edge hardware design |
| 💼 On-the-go Professionals | AI voice translation, meeting summaries, long battery life |

---

## 🔗 Live Demo

🌐 **[Insert your deployed Vercel / Netlify URL here]**

> Deployed via Vercel / Netlify with zero-config from the `main` branch.

---

## ✨ Features

### 🎮 Interactive 3D Model
- **Scroll-Driven Storytelling** — The 3D earbud case repositions as you scroll: centered in Hero, shifted right during Features & Specs, and left-centered in the CTA section
- **Auto Lid Open / Close** — Case lid opens automatically at 12% scroll progress and closes smoothly when returning to top
- **Mouse Magnet Tracking** — The case and buds dynamically tilt toward the user's cursor in real time
- **Earbud Click Ripples** — Clicking either earbud triggers expanding Torus soundwave rings that fade using delta frame calculations
- **Drag-to-Rotate** — Click and drag anywhere in the background to manually spin and inspect the model from any angle

### 🧩 Interactive UI Simulators
- **PPG Biometric Sensor Widget** — Live heart rate simulation with pulsing animation and fluctuating BPM readout
- **ANC Noise Simulator** — Toggle switch that flattens an animated SVG waveform to visualise active noise cancellation

### 🎨 Premium Visual Design
- **Cyber Orchid Theme** — Bespoke dark design system using HSL CSS variables with `#ff5e8c` (Sunset Orchid) and `#00f5d4` (Cyber Turquoise) accents
- **Technical Blueprint Grid** — Subtle 50px blueprint overlay with fixed ambient glow orbs
- **Frosted Glass Navbar** — Fixed glassmorphic header with `backdrop-filter: blur(12px)`
- **Spec Sheet EQ Panel** — Hover-highlighted spec grid with sliding orange metric fill-bars

### 📱 Responsive Layout
- On mobile, the 3D model repositions to the top of the viewport so content flows naturally below
- All interactive widgets and simulators are fully usable on touch devices

---

## 🛠 Tech Stack

| Category | Technology | Version |
|---|---|---|
| **Framework** | React + Vite | React 19 / Vite 8 |
| **3D Engine** | Three.js + React Three Fiber | three ^0.184 / R3F ^9.6 |
| **3D Helpers** | @react-three/drei | ^10.7.7 |
| **Animation** | Framer Motion | ^12.41.0 |
| **Styling** | Vanilla CSS + HSL Variables | — |
| **Linting** | oxlint | ^1.69.0 |
| **Deployment** | Vercel / Netlify | zero-config |

### Key Dependencies (`package.json`)

```json
"dependencies": {
  "@react-three/drei": "^10.7.7",
  "@react-three/fiber": "^9.6.1",
  "framer-motion": "^12.41.0",
  "react": "^19.2.7",
  "react-dom": "^19.2.7",
  "three": "^0.184.0"
}
```

---

## 📁 Project Structure

```
pulseforge-r3f-project/
├── index.html
├── vite.config.js
├── package.json
├── public/
│   ├── favicon.svg
│   └── icons.svg
└── src/
    ├── main.jsx                  # Application entry point
    ├── App.jsx                   # Root container; tracks global scroll progress (0.0–1.0)
    ├── components/               # UI sections and interactive widgets
    │   ├── Navbar.jsx            # Glassmorphic fixed header with smooth anchor links
    │   ├── Hero.jsx              # Opening headline, tagline, and CTA teaser
    │   ├── Features.jsx          # Feature cards with ANC & PPG live simulators
    │   ├── Specs.jsx             # Technical spec sheet with EQ-style fill-bar animations
    │   ├── CallToAction.jsx      # Pre-order interface with pricing (RM 1,099)
    │   └── Waveform.jsx          # Reusable animated SVG waveform component
    ├── config/
    │   └── siteConfig.js         # Central config for all text, specs, colors, and pricing
    ├── scene/
    │   ├── Scene.jsx             # R3F Canvas setup: camera, lighting, ContactShadows
    │   └── EarbudCase.jsx        # Full 3D model: geometry, materials, scroll interpolation
    └── styles/
        └── global.css            # CSS reset, HSL variable system, blueprint grid background
```

> **💡 Architecture Note:** The R3F `<Canvas>` is mounted globally in `App.jsx` and sits behind all page sections via CSS z-stacking. This means the 3D model persists and animates continuously as the user scrolls — it is never confined to a single section.

---

## 🚀 Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) v18 or higher
- npm v9 or higher

### 1. Clone the Repository

```bash
git clone https://github.com/hyekaljap/PulseForge-Interactive-3D-Product-Landing-Page.git
cd PulseForge-Interactive-3D-Product-Landing-Page
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Start Development Server

```bash
npm run dev
```

Open [http://localhost:5173](http://localhost:5173) in your browser. The page hot-reloads automatically on file changes.

### 4. Build for Production

```bash
npm run build
```

Generates optimised production assets in `/dist`.

### 5. Preview Production Build

```bash
npm run preview
```

### 6. Run Linter

```bash
npm run lint
```

---

## 📦 Deployment

This project deploys with **zero configuration** on Vercel or Netlify.

**Vercel:**
1. Push your code to GitHub
2. Import the repository at [vercel.com](https://vercel.com)
3. Vercel auto-detects Vite — click **Deploy**

**Netlify:**
1. Push your code to GitHub
2. Import the repository at [netlify.com](https://netlify.com)
3. Set build command: `npm run build` and publish directory: `dist`
4. Click **Deploy**

---

## 📊 Product Specifications

| Spec | Value |
|---|---|
| **Driver** | 11mm dynamic + balanced armature |
| **Connectivity** | Bluetooth 6.0, multipoint |
| **Water Resistance** | IP68 (buds) · IPX4 (case) |
| **Weight** | 4.8g per bud |
| **Charging** | USB-C + Qi wireless |
| **Sensors** | PPG · SpO2 · Accelerometer · Gyroscope |
| **Battery Life** | 38h total (with case) |
| **ANC Performance** | -42dB peak noise reduction |
| **Price** | RM 1,099 — Free worldwide shipping |

---



---

<div align="center">

Built with ❤️ using **React Three Fiber** &nbsp;·&nbsp; Group Assignment 2025/2026

*PulseForge — "Hear everything. Miss nothing."*

</div>
