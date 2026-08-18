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
- All data points are sourced from public benchmarks, official pricing pages, and reputable tech media — every model card links back to its citations at the bottom of the page.

## Usage

This is a single static HTML file with no build step. Open `index.html` directly in a browser, or serve it with any static file server:

```bash
python -m http.server 8080
```

## Data freshness

Rankings are manually curated and periodically audited against public sources (see in-page footer for the latest calibration date per category). This is a subjective, editorially-curated composite score for personal/team reference — not an official benchmark authority. Treat the underlying benchmark percentages (cited inline) as the ground truth, and the tier placement as one team's opinion.

## License

MIT — see [LICENSE](./LICENSE).
