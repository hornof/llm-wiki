---
title: "Daily Brief roundup — 2026-08-21 (DOJ investigates a16z; Mechanistic Tomography; Bun 1.4 WebView; /wayfinder skill)"
type: source
medium: article
url:
ingested: 2026-08-21
---

## Summary

Daily Brief `Daily Briefs/2026-08-21.md`. Top headlines re-surface (Import AI 469, GLM-5.3 "Death of Params," Fable-5 redeploy, smolvm, Jeremy Morrell — all folded #247/#253). Net-new: a **DOJ antitrust probe of a16z** (→ new page), an interpretability framework, a Bun release, and a Matt Pocock planning skill.

## Net-new — page created / folded

- **DOJ investigates a16z board conflicts under a 112-year-old antitrust law** (TechCrunch) → **new page [[a16z]]**. First VC-focused action under **Clayton Act §8 (interlocking directorates)** — regulatory pressure on **concentrated AI-infrastructure board seats**. A16z was long overdue a page (coalition co-lead, [[garry-tan-new-rules-for-founders-a16z-2026-08-13|a16z-podcast]] host); this anchors it. *(Investigation, not a charge.)*
- **Mechanistic Tomography** (arXiv 2608.19338) → folded into [[mechanistic-interpretability]]. Reframes the interpretability toolkit (patching, gradients, Hessians) as **designed measurement under different assumptions** — the constraint becomes *"what can I access / what's my budget"* rather than *"which technique."* A rigor/unification advance for **control-oriented** interpretability.
- **Bun 1.4 — `Bun.WebView` shot-scraper-style JSON API** (Willison) → folded into [[bun]]. First concrete **post-Rust-rewrite** feature release: a headless-browser-as-a-library JSON API (in-process, no per-job Docker) — Willison's shot-scraper pattern on it. Traction datapoint that the Zig→Rust port is shipping user-facing capability.
- **Matt Pocock's `/wayfinder` skill** (Latent Space) → folded into [[matt-pocock]] + [[skill-md]]. A **greenfield-planning skill** for cutting through the *"fog of war"* of unclear projects — a concrete, named [[skill-md|SKILL.md]] workflow from a tracked skills-ecosystem voice.

## Net-new — noted, not folded (watch-items)

- **Medical/safety-critical ML** (owner health-AI adjacent): **Holtercare-Bench** (arXiv 2608.19297, 22.98K-QA long-term ECG multimodal benchmark), **Alzheimer's disease-continuum Bayesian severity** (arXiv 2608.19436, continuous vs discrete diagnosis from diffusion imaging), **ML helicopter weight estimation** aligned to EASA/EUROCAE ED-324 (arXiv 2608.19210, safety-critical aerospace). Note.
- **Proof-sharing limits in NN verification** (arXiv 2608.19351) — template-based robustness-verification acceleration breaks under architecture/dataset variance; formal-methods rigor, ties [[mechanistic-interpretability|Verifiable Transformers]] thread. Watch.
- **Sub-50ms TTS** (Qwen/NARI Labs) — real-time text-to-speech latency frontier; enabler for voice agents. Create-candidate `companies/nari-labs` if it recurs.
- **Poolside "$12B reverse-execuhire to NVIDIA"** (Latent Space AINews) — **flagged by the brief itself as "likely satire or heavily garbled; unverified."** Not folded onto [[poolside]] — captured here only as an unverified curiosity pending a coherent primary.

## Re-surfaces (already ingested — dedup, no action)

- **Import AI 469 (Science AI / RSI simulator)** → [[jack-clark]] (#247).
- **GLM 5.3 "Death of Params" post-training scaling** → [[ai-margin-collapse]] + [[glm-5-2]] (#253).
- **Fable 5 redeployment + jailbreak-severity framework** → [[anthropic-redeploying-fable-5-jailbreak-severity-framework-2026-06-30]].
- **smolvm untrusted-code sandbox + Jeremy Morrell extensibility** → [[simon-willison]] (#253).

## Pages Updated
- [[a16z]] (new), [[mechanistic-interpretability]], [[bun]], [[matt-pocock]], [[skill-md]]
