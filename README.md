# Bit Focus ⏳ 🎧

> **A minimal, zero-bloat study timer and multi-track ambient soundscape mixer built for deep cognitive focus.**

**Bit Focus** is an installable, offline-first Progressive Web App (PWA) engineered to tackle cognitively demanding study sessions. Unlike heavy, ad-laden productivity apps, Resonance is compiled to ultra-lean JavaScript using **SvelteKit** and **TypeScript**, delivering fluid 60 FPS spring animations without the virtual-DOM bloat.

### Key Features
- **Adaptive Study Intervals:** Presets tailored to task difficulty (e.g., 45m/15m deep STEM sessions vs. 25m/5m review blocks).
- **Procedural Ambient Mixer:** Mix rain, binaural beats, white noise, and fireplace simultaneously via the native **Web Audio API**.
- **Dynamic Audio Filtering:** Automatic low-pass filters engage during break cycles to ease cognitive context switching.
- **Ultra-Fluid UI:** Physics-based progress indicators and gestures powered natively by `svelte/motion` (`tweened` / `spring`).
- **Offline-First & Installable:** Instant caching through Service Workers—runs seamlessly offline on mobile and desktop.
