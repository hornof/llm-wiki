---
title: "Google I/O 2026: Gemini 3.5 Flash + Omni + Spark + Antigravity"
type: source
medium: article
url: https://simonwillison.net/2026/May/20/google-io/
ingested: 2026-05-20
---

## Summary

Consolidated capture of Google's I/O 2026 product surface (May 2026), drawn from three layers: (1) [[simon-willison|Simon Willison's]] same-day post on the I/O announcements; (2) Latent Space / AINews recap (*"Google I/O 2026: Gemini 3.5 Flash"*); (3) @GoogleAI X thread on **Gemini Omni** (video-generation model). Four named products / surfaces: **Gemini 3.5 Flash** (now GA), **Gemini Omni** (video-input-to-video-output multimodal model), **Gemini Spark** (background agents), **Antigravity 2.0** (Google's agent SDK / platform). None of the primaries was deeply fetched in this ingest pass — capture is brief-tier-plus-X-primary across the four named items.

## Key Claims / Takeaways

### Gemini 3.5 Flash (GA)

- **GA released**. Deployment positioning: *"Google plans to use it for everything"* (Willison framing). Single fast model across consumer and enterprise surfaces.
- **Pricing**: $1.5 / million input tokens; $9 / million output tokens (per Cloud Console leak captured in [[dailybrief-roundup-2026-05-19]]).
- **Brief's read on cost**: *"3.5 Flash's higher cost-per-token but GA status suggests a bet on throughput over margin"* — Google appears to be optimizing for **deployment volume** rather than **cost-per-token leadership**.
- **Logan Kilpatrick (Google AI Studio / Gemini API)**: *"Gemini 3.5 marks the start of a new era for the model family after 2.5 years building infrastructure and teams."*
- **Counter-take from Lucas Beyer (researcher)**: questions the *"3.5"* naming for what Kilpatrick frames as a fundamental shift — the version-number suggests incremental upgrade, the framing suggests architectural break. Worth tracking whether subsequent benchmarks bear out "new era" framing or "incremental upgrade" framing.

### Gemini Omni (video-input → video-output multimodal model)

- **GoogleAI X framing (primary)**: *"Gemini Omni, our new model designed to create anything from any input, starting with video."*
- **Four named capabilities** (from the GoogleAI X thread):
  1. **World understanding** — *"built on Gemini's vast knowledge of history, science, and culture, so it can produce videos that are grounded in how the world actually works."*
  2. **Reference anything** — *"extends Gemini's native multimodality, allowing you to blend combinations of text, audio, image, and video inputs into a high-quality, consistent video."*
  3. **Conversational editing** — *"edit your videos using natural language (like Nano Banana, but for video)."* The Nano Banana comparison is significant — Nano Banana was Google's conversational-editing image model that landed earlier in 2026; Omni applies the same paradigm to video.
  4. **Distribution**: Google AI Plus, Pro, and Ultra subscribers via @geminiapp, @GoogleFlow, @GoogleFlowMusic, and **free on @YouTube Shorts and the YouTube Create app**.
- **YouTube Shorts integration is the load-bearing distribution signal** — Google is using its existing consumer-video distribution surface (YouTube Shorts, ~2B MAU) as the AI-video-generation funnel. Pairs with Google Search → conversational AI pivot captured in [[dailybrief-roundup-2026-05-19]] as a coordinated **consumer-surface AI-integration play**.

### Gemini Spark (background agents)

- **What it is**: background-agent surface for Gemini. Specific capabilities and developer interface not captured in brief synopsis; Willison's post likely has detail.
- **Why it matters**: Google's equivalent of Anthropic's [[claude-cowork]] / Claude Code background-agent surfaces and OpenAI Codex. **First wiki-tracked Google background-agent product** at the Gemini consumer-product level.

### Antigravity 2.0

- **What it is**: Google's agent SDK / platform; *"Antigravity"* name surfaced earlier in [[dailybrief-roundup-2026-05-19|the previous brief]] via the GitHub repo (`google-antigravity/antigravity-sdk-python`). The 2.0 designation suggests rapid iteration; 1.0 timeline not captured.
- **Brief's framing**: *"consolidates Google's product strategy."* Antigravity sits underneath Gemini Spark and Gemini Omni as the **agent-platform layer**.
- **Companion repo signal**: `run-llama/antigravity-demo` (3★) — Python CLI that *"publishes local directories to GitHub and provisions an Antigravity agent environment using LlamaParse or LiteParse"* — third-party tooling forming around Antigravity within 24 hours of the I/O announcement.

### Willison's caveat

Willison explicitly notes his coverage preference is **GA-only** — so non-GA announcements (research previews, internal-only deployments) are not captured in his post. Latent Space's roundup is broader but routine-launch-cadence framing per the brief.

## Why It Matters

- **First wiki capture of Google's four-named-product I/O 2026 surface**. Prior wiki captures had Gemini 3.5 Flash leak ([[dailybrief-roundup-2026-05-19]]) and `google-antigravity/antigravity-sdk-python` repo signal but no I/O-coordinated framing.
- **Single-fast-model strategy (Gemini 3.5 Flash) signals deployment-volume bet over cost-per-token leadership.** This is structurally different from Anthropic's tiered Haiku/Sonnet/Opus model-routing-default framing ([[svpino-subagent-pilled-2026-05-15]] / [[zephyr-7-claude-setups-2026-05-15]]) where task-appropriate model selection is load-bearing. Google's bet: **one good-enough model + massive distribution surface** vs Anthropic's **multiple models + practitioner-discipline-on-routing**.
- **Gemini Omni's YouTube-Shorts integration** is the most material consumer-AI-distribution move captured this week. Pairs with Google Search conversational-AI pivot as a **two-surface coordinated consumer integration** — both leverage Google's existing distribution moats (search + video).
- **Antigravity 2.0 + Gemini Spark = Google's agent-platform stack landing**. Google's prior agent positioning has been fragmented (Genie, Bard, AI Studio, Vertex); the I/O 2026 surface consolidates around Antigravity-as-SDK + Spark-as-product. Worth tracking whether this consolidation lands or fragments further over the next 60 days.
- **The "Nano Banana, but for video" framing** for Omni's conversational editing is the cleanest single-sentence positioning of conversational-multimodal-editing as a Google-native product category. Conversational image editing (Nano Banana) is now consumer-product-validated; conversational video editing (Omni) is the next surface.

## Caveats

- **Three of four primaries not deeply fetched** (Willison post, Latent Space recap, the underlying Google I/O 2026 keynote and product pages). GoogleAI X thread captured in full (it's the @GoogleAI raw drop). Specific benchmark scores, exact pricing for Spark/Antigravity, Omni quality vs Veo / Sora / Runway, and developer-platform pricing terms are all not captured.
- **"Gemini 3.5" naming is contested internally** — Lucas Beyer's pushback on Kilpatrick's framing suggests the model family's positioning is itself unsettled. Whether 3.5 is incremental or architectural matters for forward-looking signal.
- **Antigravity 2.0 vs 1.0 not differentiated**. The version number suggests rapid iteration but the brief doesn't surface what changed.
- **YouTube Shorts integration framing is from the @GoogleAI X thread** — not independently verified against actual deployment status. Captured as Google's stated rollout posture; treat as marketing-tier framing until practitioner reports surface.
- **No Gemini-model entity page exists in the wiki** as of this ingest. Worth creating on a follow-up pass.

## Cross-references

- [[google-deepmind]] — entity page; updated with Gemini 3.5 Flash GA + Omni + Spark + Antigravity surface.
- [[simon-willison]] — Willison's I/O coverage; same-day post.
- [[dailybrief-roundup-2026-05-19]] — Gemini 3.5 Flash leak + Project Genie + Street View + Antigravity-SDK repo signals from the day before.
- Google Search — conversational-AI pivot; same-week coordinated consumer-surface play.
- [[claude-cowork]] / [[claude-code]] — Anthropic counterparts to Gemini Spark (background agents) and Antigravity (agent SDK).
- [[openai|OpenAI Codex]] — third major background-agent / coding-agent surface.
- [[karpathy-html-output-taxonomy-2026-05-08]] / [[model-rendered-ui]] — Omni's conversational-video-editing is one step further along the trajectory toward interactive neural artifacts that Karpathy gestures at.
- [[zephyr-7-claude-setups-2026-05-15]] / [[svpino-subagent-pilled-2026-05-15]] — Anthropic model-routing-default discipline; structurally inverse to Google's single-fast-model bet.

## Pages Updated

- [[google-deepmind]] (updated — Google I/O 2026 product surface (Gemini 3.5 Flash GA + Omni + Spark + Antigravity 2.0) added under traction signals; single-fast-model deployment strategy framing; YouTube Shorts integration as consumer-surface distribution moat; date bumped to 2026-05-20)
