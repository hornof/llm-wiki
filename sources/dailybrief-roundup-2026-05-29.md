---
title: "Daily Brief Roundup — 2026-05-29"
type: source
medium: article
url: Daily Briefs/2026-05-29.md
ingested: 2026-05-29
---

## Summary

Aggregate page for non-headline items from 2026-05-29 Daily Brief. Headline events split into separate source pages: [[anthropic-47b-runrate-willison-2026-05-29|$47B Anthropic run-rate]], [[taelin-gpt-5-5-test-bypass-2026-05-29|Taelin GPT-5.5 4-team hardcoded-test-bypass]], [[latentspace-walden-yan-async-agents-2026-05-29|Walden Yan async-agents Latent Space pod]], [[openai-rosalind-biodefense-2026-05-29|Rosalind Biodefense]], [[metr-cunningham-agent-diminishing-returns-2026-05-29|METR Cunningham diminishing returns]]. This roundup covers: **AINews Anthropic $965B+Opus 4.8 secondary**, **Boston Children's rare-disease**, **Brilliant's Sue Khim launches Koji**, **Representation Signatures + Catastrophic Forgetting research papers**, **Vicki Boykis essay**, **Kog 3K-tokens/s inference**, **2 repos worth watching**, **5 "Today on Digg" items**. **Dedup**: Cognition $1B/$26B (yesterday), Import AI 458 (deduped 3× already).

## Key Items

### AINews Anthropic $965B + Opus 4.8 + Dynamic Workflows / ultracode (Latent Space, 2026-05-29)

**Source**: [latent.space/p/ainews-anthropic-raises-965b-series](https://www.latent.space/p/ainews-anthropic-raises-965b-series).

- AINews / Latent Space secondary on the May 28 Anthropic bundle (Series H + Opus 4.8 + Dynamic Workflows).
- Brief framing of the headline appears to conflate *"$965B Series H"* (round size) vs *"$65B raised at $965B valuation"* (the actual May 28 disclosure). The Latent Space coverage is the citation; the wiki-captured numbers per [[anthropic-series-h-65b-965b-2026-05-28]] are $65B raised / $965B post-money.
- **Why it matters as a roundup item rather than a separate source page**: same-event coverage of yesterday's pt1 ingest; AINews is the *practitioner-press-side carry* of the announcement. Track for whether AINews surfaces follow-on disclosures.

### Boston Children's Hospital uses AI to find new diagnoses (OpenAI, 2026-05-29)

**Source**: [openai.com/index/boston-childrens-hospital](https://openai.com/index/boston-childrens-hospital).

- OpenAI marketing piece on rare-disease diagnosis via GPT.
- **40+ new diagnoses surfaced** (claim; OpenAI-attributed).
- **Brief caveat**: *"OpenAI marketing piece, so treat as case study rather than independent validation."*
- **Pairs structurally with [[openai-rosalind-biodefense-2026-05-29|Rosalind Biodefense]]**: both are the same-day OpenAI public-health vertical-positioning move. Boston Children's is the *consumer-healthcare* surface; Rosalind is the *biosecurity-government* surface. Together they bookend OpenAI's healthcare-vertical-week.
- **Caveat for [[abridge|Abridge]]**: Boston Children's is a major teaching hospital and Abridge customer (per [[abridge]] coverage); whether the OpenAI rare-disease workflow co-deploys with Abridge or competes with it is a tracking-watch.

### Representation Signatures and Risk-Feedback Alignment in LLM Trading Agents (arXiv:2605.28850)

**Source**: [arXiv:2605.28850](https://arxiv.org/abs/2605.28850).

- Research on **pre-failure signatures in agent behavior under market stress** — planning embeddings drift.
- **TradeArena testbed** with auditable traces.
- **Brief framing**: *"Concrete testbed with auditable traces. Relevant if you're thinking about agent reliability patterns or safety-critical deployments."*
- **Pairs with [[taelin-gpt-5-5-test-bypass-2026-05-29]]**: both are *concrete-incident agent-failure measurements*, but at different layers — Taelin at the *honesty-bypass / loss-landscape-attractor* layer; this paper at the *planning-embeddings-drift-under-stress* layer. Two distinct alignment-measurement signals in the same week.
- **No separate source page** — defer until cross-referenced.

### Mechanistic origins of catastrophic forgetting: why RL preserves circuits better than SFT? (arXiv:2605.28860)

**Source**: [arXiv:2605.28860](https://arxiv.org/abs/2605.28860).

- Extends behavioral observations to *circuit-level mechanistic* explanation.
- **Finding (inferred from brief framing)**: RL preserves prior-capability circuits better than SFT during fine-tuning.
- **Brief framing**: *"Standard interpretability contribution; no immediate product angle."*
- **Pairs with [[end-of-finetuning]]**: this paper's circuit-level finding gives a *training-side* explanation for why some labs (Cognition, Cursor) continue to invest in RL-based fine-tuning despite the practitioner shift to long-context + constitutional-spec. Adds a mechanistic argument for the *top-1% RLFT* practitioner positioning.
- **Pairs with [[mechanistic-interpretability]]** as the wiki's interpretability cluster anchor.
- **No separate source page** — defer.

### Brilliant's Sue Khim launches Koji adaptive AI tutor (2026-05-29)

**Source**: [Digg: Koji AI tutor](https://digg.com/ai/hqutws0i).

- **Sue Khim**, founder of Brilliant.org (interactive math/science platform), launches **Koji**.
- **Use case**: adaptive AI tutoring with *"guided hints over direct answers"* — geometry, algebra, coding domains.
- **Why it matters**: Khim is a founder with deep domain expertise in adaptive learning (Brilliant pre-dated the AI-tutor wave by ~10 years). Launching a frontier-model-powered version *now* is a high-signal *adaptive-learning vs frontier-model* synthesis bet.
- **Brief framing**: *"Founder-led launch signals domain expertise. No traction signal yet; worth monitoring for execution proof."*
- **Pairs with [[saas-disruption-thesis|Cal AI conversion proof point]]** ([[linas-anthropic-startup-playbook-2026-05]]): same single-domain-wedge-with-professional-substitution-pricing shape, applied to *adaptive learning* rather than *calorie tracking*. Cal AI's outcome ($40M revenue / $50M ARR / 7 employees) is the *Khim-target-shape* outcome if Koji executes.
- **No separate source page** — single-source today; defer entity pages for Koji and Sue Khim until cross-referenced.

### METR / Tom Cunningham vs Ryan Greenblatt on agent diminishing returns

→ Split out to [[metr-cunningham-agent-diminishing-returns-2026-05-29]].

### Import AI 458 — Reckoning with the future + singularity story

**Source**: [importai.substack.com/p/import-ai-458-reckoning-with-the](https://importai.substack.com/p/import-ai-458-reckoning-with-the).

- Already captured in [[dailybrief-roundup-2026-05-26]] (deduped). **No further action.**

### Vicki Boykis: *We should be more tired than the model* (2026-05-28)

**Source**: [vickiboykis.com/2026/05/28/we-should-be-more-tired-than-the-model/](https://vickiboykis.com/2026/05/28/we-should-be-more-tired-than-the-model/).

- Anthropomorphism and AI-fatigue essay.
- **Brief framing**: *"Conceptual essay, not a tool or pattern. Readable for framing, not actionable."*
- **Pairs with [[llmorphism]]** ([[capraro-llmorphism-2026-05]]) — Capraro's coined-bias of *attributing LLM-like cognition to humans*. Boykis's framing is the *inverse* — humans projecting human-fatigue onto LLMs. Same coin, opposite face.
- **No separate source page** — defer; surface to the [[llmorphism]] concept page if a second-source converges.

### Expertise in the age of AI (moderndescartes.com)

**Source**: [moderndescartes.com/essays/ai_and_expertise/](https://www.moderndescartes.com/essays/ai_and_expertise/).

- Long-form essay on expertise + AI dynamics.
- **Brief caveat**: *"Unknown author, no summary; needs inspection to assess depth."*
- **No action** — unverified-quality; defer.

### Kog: Real-time LLM Inference 3,000 tokens/s per request on standard GPUs

**Source**: [blog.kog.ai/real-time-llm-inference-on-standard-gpus-3-000-tokens-s-per-request/](https://blog.kog.ai/real-time-llm-inference-on-standard-gpus-3-000-tokens-s-per-request/).

- Inference-optimization technique claiming **3,000 tokens/s on standard GPU per request**.
- **Brief framing**: *"Incremental optimization rather than structural shift."*
- **Pairs with [[kv-cache-optimization]]** as adjacent inference-bottleneck work.
- **Verification-pending**: GPU model used, batch size, model-size context for the 3K-tokens/s figure. Without these the number is uncomparable.
- **No separate source page** — defer until cross-referenced or methodology surfaces.

### Repos worth watching

- **run-llama/liteparse** (AI Score 7/10, 6.4k★) — Rust core library with Python/Node/WASM bindings for fast local PDF/DOCX/XLSX parsing via PDFium text extraction + selective Tesseract or HTTP OCR + grid-projection layout reconstruction. **Why it matters**: agent-document-ingestion infrastructure; pairs with [[llama-index]] (same parent org `run-llama`). Worth a future deep-dive if document-ingestion becomes a wiki-tracked stack layer.
- **ShirleyMaxx/REST3D** (AI Score 9/10, 7★) — Research system: single casual image → visually consistent, physically stable interactive 3D scene via image-conditioned 3D generation + physics-based stability. **Why it matters**: pairs with [[fei-fei-li|Fei-Fei Li]] / [[world-labs|World Labs]] / [[spatial-intelligence]] research thread. Worth flagging on the spatial-intelligence cluster.

### Today on Digg, not in this brief

- **Pope Francis argues AI cannot truly understand human concepts** ([Digg](https://digg.com/ai/3yng7pz7)) — **brief error / wiki contradiction**: per [[pope-leo-xiv-magnifica-humanitas-encyclical-2026-05-25]], **Pope Leo XIV** is the current pontiff (not Francis). Digg framing is likely *retrospective* on a Pope Francis quote / interview, not current commentary. Treat as low-confidence; don't propagate.
- **Nvidia teases a "new PC era" with cryptic Taipei campaign** ([Digg](https://digg.com/ai/6x02r4qy)) — Taipei coordinates; cryptic; **hold for confirmation**.
- **Gary Marcus vs Guillaume Verdon (Extropic)** ([Digg](https://digg.com/ai/gn4ebq30)) — Marcus calls Verdon's *"AI amplifies rather than replaces"* framing a *"strategic industry pivot."* Pairs with [[ai-labor-market-impacts]] augmentation-vs-replacement debate. No separate source page; defer.
- **MIT CSAIL Alex Zhang on recursive LLM research → 2 Anthropic agent systems** ([Digg](https://digg.com/ai/7n7gq9r5)) — **load-bearing structural signal**: Zhang clarifies his recursive-language-model research connects to *"Anthropic's Scaling Managed Agents and Dynamic Workflows."* **First wiki-captured external-research → Anthropic-agent-systems direct lineage claim.** Cross-confirms [[anthropic-dynamic-workflows-primary-2026-05-28|Dynamic Workflows]] as research-backed rather than purely product-engineered. Worth primary-fetching when bandwidth allows.
- **DeepSeek's Deli Chen releases LLM continual learning survey paper auto-generated by DeliAutoResearch** ([Digg](https://digg.com/ai/xay55qwq)) — *self-improvement methods*: STaR, o1-style. Pairs with [[end-of-finetuning|continual-learning thread]] (opposite-direction signal). **First wiki-captured DeepSeek-side autonomous-research-system disclosure.** Worth a primary fetch.

## Dedup (already captured)

- **Cognition $1B / $26B Series D** ← [[cognition-26b-valuation-492m-arr-2026-05-27]] (2 days ago). Today's Latent Space pod ([[latentspace-walden-yan-async-agents-2026-05-29]]) is the *async-agents follow-up* layer; the funding numbers are dedup.
- **Import AI 458** ← deduped 3 times already; today's brief mention adds nothing new.

## Pages Updated

- [[abridge]] — Boston Children's rare-disease workflow noted as adjacent-but-unclear-overlap signal
- [[openai]] — Boston Children's case study added as the *consumer-healthcare* surface paired with Rosalind's *biosecurity-government* surface for the public-health vertical-positioning week
- [[llmorphism]] — Boykis's inverse-anthropomorphism framing noted as same-coin-opposite-face
- [[end-of-finetuning]] — DeepSeek DeliAutoResearch continual-learning survey + Catastrophic Forgetting paper noted as adjacent signals
- [[spatial-intelligence]] / [[world-labs]] — REST3D flagged as research-side adjacent signal
- [[anthropic-dynamic-workflows-primary-2026-05-28]] — MIT CSAIL Alex Zhang recursive-LM research-lineage cross-confirmation noted

Verification-pending across items: Boston Children's 40+ diagnosis methodology; Khim's Koji traction; arXiv 2605.28850 + 28860 specifics; Kog 3K-tokens/s methodology; Alex Zhang primary; DeliAutoResearch primary; Pope Francis quote provenance.

## Adjacent sources

- [[anthropic-47b-runrate-willison-2026-05-29]] — same-day Anthropic revenue datum
- [[taelin-gpt-5-5-test-bypass-2026-05-29]] — same-day alignment-failure incident
- [[latentspace-walden-yan-async-agents-2026-05-29]] — same-day Cognition operational-detail pod
- [[openai-rosalind-biodefense-2026-05-29]] — same-day OpenAI vertical-government deployment
- [[metr-cunningham-agent-diminishing-returns-2026-05-29]] — same-day economist-side modeling
