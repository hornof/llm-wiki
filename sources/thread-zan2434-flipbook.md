---
title: "Thread by @zan2434 — Flipbook: Model-Rendered UI"
type: source
medium: twitter-thread
url: https://x.com/zan2434/status/2046982383430496444
ingested: 2026-04-22
---

## Summary
Zain Shah (@zan2434), Eddie Jiao, and Drew O'Carr built Flipbook — a prototype that streams every pixel of a UI directly from a video model, with no HTML, no layout engine, no code. The UI adapts its layout to the window size and any region of the image can be made interactive. Live at flipbook.page.

## Key Claims / Takeaways
- **No layout engine**: every pixel streamed live from a model — "just exactly what you want to see"
- **Fluid layouts**: illustrations reshape to fit the window; any image region can be interactive, not just predefined buttons
- **Implementation**: heavily optimized LTX Studio video model; streams live 1080p at 24fps via WebSockets to Modal Labs serverless GPU infra
- **Current scope**: limited to visual explanations; demos in the thread are sped up/edited — live version is early and slow
- **Expansion thesis**: "As models get more accurate and more stateful, the set of things worth doing this way will expand" — including coding UIs
- **Related work**: commenter points to "Neural Computers" (arxiv.org/abs/2604.06425) — video models that roll out screen frames from instructions, pixels, and user actions in CLI and GUI settings

## Pages Updated
- [[model-rendered-ui]] — new concept page
