# OhmAIRank 歐姆AI天梯榜

Single-file, zero-build HTML leaderboard for tracking the fast-moving 2026 AI model landscape across six categories:

- LLM coding/reasoning ("LLM 硬核天梯")
- Image generation
- Video generation
- Music/audio generation
- General-purpose AI agents (OpenClaw-style)
- AI coding-agent software (IDE/CLI tools)

## Features

- Interactive tier list (T0–T3) with a live-adjustable weighting engine (logic/speed/price sliders) that re-sorts models in real time.
- Radar chart comparison across six scoring dimensions per category.
- Token-cost calculator for estimating monthly spend against the current top model.
- All data points are sourced from public benchmarks (e.g. Artificial Analysis indices), official release notes and pricing pages. Since v9.2 the in-page source cards were removed to keep the page clean; scores from different leaderboards are never mixed into one number.

## Usage

**Live page:** https://go.yuemoon-osclaw.workers.dev/tierlist (hosted on our own server).

This is a single static HTML file with no build step. Open `index.html` directly in a browser, or serve it with any static file server:

```bash
python -m http.server 8080
```

## Current version

**v9.3.1 — calibrated 2026-10-18** (all six categories), e.g. Gemini 4 Argon, Claude Haiku 5.5, DeepSeek V4.1 Flash, Meta Muse Wonder / Wonder Full, Nano Banana 2.1, Kling 4.0, Suno v6, OpenClaw v2026.10.4.

## Data freshness

Rankings are manually curated and periodically audited against public sources (roughly monthly; see the in-page header/footer for the latest calibration date). This is a subjective, editorially-curated composite score for personal/team reference — not an official benchmark authority. Treat the underlying benchmark percentages (cited inline) as the ground truth, and the tier placement as one team's opinion.

## License

MIT — see [LICENSE](./LICENSE).
