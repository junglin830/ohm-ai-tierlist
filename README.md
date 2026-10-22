# OhmAIRank 歐姆AI天梯榜

Single-file, zero-build HTML leaderboard for tracking the fast-moving 2026 AI model landscape across ten categories:

- LLM coding/reasoning ("LLM核心天梯")
- Image generation
- Image editing
- Video generation
- 3D generation
- Music/audio generation
- Voice generation
- General-purpose AI agents (OpenClaw-style)
- Personal assistant agents (Claude Duet / Meta Muse / Grok Bot / ChatGPT Dots)
- AI coding-agent software (IDE/CLI tools)

Plus a dedicated "各領域最佳AI快選榜" (best-AI-per-task quickpick) tab: 13 task categories, each showing the current top pick with its real, background-removed brand logo.

## Features

- Interactive tier list (T0–T3) with a live-adjustable weighting engine (logic/speed/price sliders) that re-sorts models in real time.
- Radar chart comparison across six scoring dimensions per category.
- Token-cost calculator for estimating monthly spend against the current top model.
- Real brand logos (background-removed, embedded as base64 — no runtime network dependency) shown next to matching models in both the quickpick tab and every leaderboard table row.
- A standalone "快選榜" tab, kept separate from the full leaderboard so the default page stays short.
- All data points are sourced from public benchmarks (e.g. Artificial Analysis indices), official release notes and pricing pages. Since v9.2 the in-page source cards were removed to keep the page clean; scores from different leaderboards are never mixed into one number.

## Usage

**Live page:** https://go.yuemoon-osclaw.workers.dev/tierlist (hosted on our own server).

This is a single static HTML file with no build step. Open `index.html` directly in a browser, or serve it with any static file server:

```bash
python -m http.server 8080
```

## Current version

**v9.5.2 — 2026-10-22**: expanded from 6 to 10 full leaderboard tabs (added image-editing, 3D generation, voice generation, personal-assistant-agent categories — the latter covering brand-new 2026-10 launches like Claude Duet, Meta Muse, Grok Bot, ChatGPT Dots), added a 13-category "各領域最佳AI快選榜" quickpick tab (its own tab now, not always-on), and extended real background-removed brand logos from the quickpick cards to every leaderboard table row.

## Data freshness

Rankings are manually curated and periodically audited against public sources (roughly monthly; see the in-page header/footer for the latest calibration date). This is a subjective, editorially-curated composite score for personal/team reference — not an official benchmark authority. Treat the underlying benchmark percentages (cited inline) as the ground truth, and the tier placement as one team's opinion.

## License

MIT — see [LICENSE](./LICENSE).
