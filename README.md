# Climbing Periodization Planner

A small offline-capable PWA that lays out a full climbing periodization training
cycle — Aerobic Base → Max Strength → Power → Power-Endurance/Anaerobic Capacity
→ Peak/Taper — on a real calendar, with per-day exercises, lactate/power-curve
effects, and nutrition guidance.

**Live app:** published via GitHub Pages from this repo (see Settings → Pages).

## Features

- Pick a plan start date and mark vacation days; the schedule automatically
  shifts around them.
- Proper month-by-month calendar (not just a scrolling week strip) — correct
  weekday alignment, adjacent-month days shown dimmed and clickable to
  navigate, today's date always highlighted with an accent ring.
- A "Today" status card summarizing where you are in the plan, with a
  progress bar.
- Tap any training day for its volume, exercises, curve effects, and
  nutrition notes.
- Installable as a Progressive Web App (Add to Home Screen / desktop
  install prompt) and fully usable offline once loaded — a service worker
  caches the app shell, and your start date + vacation days are saved to
  `localStorage` on-device.

## Development

This is a static, dependency-free site — `index.html`, `manifest.webmanifest`,
`sw.js`, and `icons/`. Serve the folder with any static file server, e.g.:

```sh
python3 -m http.server 8080
```

then open `http://localhost:8080`.

## Deployment

`.github/workflows/deploy-pages.yml` publishes the repository root to GitHub
Pages via `actions/deploy-pages` on every push to `main`. In the repo's
**Settings → Pages**, set the source to **GitHub Actions** (only needed once).
