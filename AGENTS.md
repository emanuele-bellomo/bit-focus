# Autonomous AI Agent Guidelines

## 1. Project Overview & Mission
- **Project Name:** Bit Focus (Adaptive Pomodoro & Immersive Soundscape PWA)
- **Target Audience:** STEM & Engineering students with high cognitive workloads (e.g., studying Advanced Mathematics, Linear Algebra, or DSA).
- **Core Philosophy:** Extreme performance, zero bloat, offline-first. Proof that a compiled Svelte UI outperforms heavier Virtual DOM frameworks (like React) in responsiveness and resource efficiency.
- **Key Modules:**
  1. *Web Audio Engine:* Multi-track procedural ambient mixer (rain, waves, binaural beats, white noise) with dynamic filters (e.g., low-pass on rest cycles).
  2. *Adaptive Timer:* Customizable study/break interval models tailored to cognitive load (e.g., 45m/15m deep focus vs. 25m/5m review).
  3. *Fluid UI:* Sub-millisecond reactive timers and state-driven SVG progress indicators powered by `svelte/motion` (`tweened` / `spring`).
  4. *PWA & Offline:* Installable mobile experience, Service Worker audio caching.

---

## 2. Technical Stack & Architecture

- **Framework:** SvelteKit (latest version with Svelte Runes `$state`, `$derived`, `$effect`).
- **Language:** TypeScript (strict mode enabled).
- **Styling:** Tailwind CSS or clean modern CSS (prefer zero-runtime styling).
- **Audio:** Native Web Audio API (`AudioContext`, `GainNode`, `BiquadFilterNode`). Do NOT install external bloat audio libraries unless strictly required.
- **Animation/Motion:** Native Svelte primitives (`svelte/motion`, `svelte/transition`).
- **PWA Tooling:** `@vite-pwa/sveltekit` (offline service workers, caching assets & audio samples).
- **Storage:** LocalStorage / IndexedDB for local settings and session analytics.

---

## 3. Strict Rules for AI Coding Assistants

1. **No React Mental Models:**
   - Never generate Virtual DOM idioms, `useEffect`, `useMemo`, or artificial dependency arrays.
   - Use Svelte's idiomatic reactivity (Runes: `$state`, `$derived`, `$props`).
2. **Performance First:**
   - Keep JavaScript bundles minimal. Reject unnecessary npm dependencies.
   - For real-time updates (e.g., ticking timer, audio visualizers), minimize DOM reflows and repaints.
3. **Web Audio Safety:**
   - Always handle user interaction policies: `AudioContext` must only resume/start after an explicit user click/tap.
   - Prevent audio memory leaks: cleanly disconnect nodes and revoke object URLs when components unmount.
4. **TypeScript Discipline:**
   - No `any` types. Provide explicit interfaces for timer states, preset configurations, and sound tracks.
5. **Component Scaffolding:**
   - Keep files modular under `src/lib/components/` and `src/lib/audio/`.
   - Ensure clean separation of concerns: the audio engine must remain decoupled from UI rendering logic.
