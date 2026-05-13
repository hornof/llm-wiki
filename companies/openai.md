---
name: OpenAI
type: company
status: active
last_updated: 2026-05-13
---

## What It Is
AI research lab and product company. Creator of GPT model family, ChatGPT, DALL-E, Whisper, Codex, and the OpenAI API. One of the two dominant frontier AI labs alongside Google DeepMind (and Anthropic). Transitioned from nonprofit to capped-profit structure.

## Key Products
- **ChatGPT**: consumer AI assistant; largest user base in AI applications. **Free tier now ad-supported (May 2026)** — see Traction Signals.
- **GPT-4o / GPT-4 family**: flagship LLMs
- **GPT-Image-2**: image generation model (launched April 2026) — [[gpt-image-2]]
- **OpenAI API**: developer platform; includes Assistants API, Batch API, Files API
- **Realtime voice API** (May 2026): single-pass voice models with **reasoning + translation** built in; transcription + understanding + generation in one model pass — [[openai-realtime-voice-api-2026-05-08]] (primary not yet ingested, secondary-source synopsis)
- **OpenAI Agents SDK**: framework for building agentic applications — referenced in [[agentic-ai]]
- **Codex**: code-generation agent. May 2026 production-safety post documents four-layer operational pattern (sandboxing / network policies / approval flows / agent-native telemetry) — [[openai-running-codex-safely-2026-05-08]] (primary not yet ingested)

## Key People
- Sam Altman — CEO
- Andrej Karpathy — co-founder (departed, returned, now independent again) — [[andrej-karpathy]]
- [[alex-lupsasca]] — theoretical physicist on OpenAI's Science team; 2024 Breakthrough Prize in Fundamental Physics; coined the term [[vibe-physics]] for using GPT-5.x to derive novel theoretical physics results (May 2026)

## Traction Signals
- ChatGPT has largest consumer AI user base
- GPT-Image-2 launch (April 2026) received strong community reaction — [[thread-minchoi-gpt-image-2]]
- Inference costs for GPT-3.5 level performance fell 280x (2022–2024) — [[thread-aakashgupta-1b-model]]
- **Forbes 2026 AI 50**: $182.6B total funding; annualized revenue >$25B as of February 2026 — [[forbes-ai-50-2026]]
- Codex product named alongside Anthropic's Claude Code as dominant tools in the coding agent market, pressuring standalone players like Cursor — [[forbes-ai-50-2026]]
- xAI (Elon Musk) acquired by SpaceX, removing a competitor from the private AI list — [[forbes-ai-50-2026]]
- 2026-05-06: **OpenAI Science team / vibe physics** — Latent Space interview with [[alex-lupsasca]] documents GPT-5.x deriving novel gluon-amplitude and graviton results that had stumped expert humans for over a year. Categorically different signal than [[alphafold]]-style application: model produces frontier theoretical conjectures, not interpolation on a well-defined problem. Not yet independently reproduced; verification still requires expert humans (3 weeks for the 110-page graviton paper). — [[latent-space-lupsasca-vibe-physics-2026-05]] / [[vibe-physics]]
- 2026-05-06: **MRC (Multipath Reliable Connection)** — released for AI training clusters via OCP for broader adoption; positions OpenAI as defining infrastructure standards for resilient distributed training. Source URL returned 403 to WebFetch on initial capture; framing here drawn from the 2026-05-06 Daily Brief synopsis only — primary article not yet ingested. Companion to [[google-deepmind]]'s Decoupled DiLoCo announcement same week.
- 2026-05-08: **Testing ads in ChatGPT free tier** — direct counterpoint to [[anthropic]]'s [[realbigbrainai-dario-b2b-vs-consumer-2026-05-07|B2B-first business-model framing]] published 48 hours earlier. Dario's stated worry — *"I have a lot of worries about consumer AI that it kind of leads to needing to maximize engagement. It leads to slop. We've seen a lot of stuff around ads from some of the other players"* — is now operationally realized in OpenAI's product surface. The two announcements together produce a clean A/B framing for the consumer-vs-enterprise AI business-model split between the two leading frontier labs in May 2026. — [[openai-testing-ads-in-chatgpt-2026-05-08]] (primary not yet ingested; secondary-source synopsis)
  - **2026-05 follow-up**: Anthropic published [[anthropic-claude-space-to-think-2026-05]] the same week — a formal commitment that Claude will **not** be ad-supported, with the explicit argument that conversational AI is structurally different from search and that ads create misalignment between model and user. The two posts together are the cleanest paired-public-divergence on consumer monetization the wiki has tracked between OpenAI and Anthropic.
- 2026-05-08: **Realtime voice API with reasoning + translation** — single-pass voice models. Practitioner significance: voice can now be a first-class agent input/output modality with reasoning intact, not just a thin wrapper around text-mode LLMs. Widens OpenAI's competitive surface relative to Anthropic in non-coding agent use cases (Claude Cowork's Tool Priority Ladder is text-and-screen oriented). — [[openai-realtime-voice-api-2026-05-08]]
- 2026-05-08: **Codex production-safety patterns** — four-layer operational pattern (sandboxing / network policies / approval flows / agent-native telemetry) for code-generation agents at scale. Operational counterpart to [[claude-code]]'s production posture (cf. [[cat-wu]]'s "trusting Claude Code on your production databases" framing at Code w/ Claude 2026). Both labs are now publishing production-grade agentic coding posture as a competitive surface. — [[openai-running-codex-safely-2026-05-08]]
- 2026-05-13: **Finetuning APIs deprecated** — May 2026 deprecation surfaces in [[latentspace-end-of-finetuning-2026-05-13]] (swyx). Practitioner read: OpenAI is catching up to a multi-year shift in default tool stack toward long-context prompting + constitutional-style behavioral spec. Anthropic, Cognition, and Cursor are named as *still investing* in finetuning surfaces (with Cognition + Cursor *increasing* open-model RLFT). Cleanest May 2026 product-strategy divergence between OpenAI and Anthropic on **how teams adapt models to domains**. — [[latentspace-end-of-finetuning-2026-05-13]], [[end-of-finetuning]]
- 2026-05-13: **First-time Ramp AI Index loss to Anthropic** — Ramp's AI Index (50,000+ companies) shows Anthropic **34.4%** vs. OpenAI **32.3%** for paid business customers — OpenAI's first time below Anthropic on this index. OpenAI declined ~1% over the prior 12 months while Anthropic went 9% → 35.4%. OpenRouter cross-confirms: OpenAI last led Anthropic in **December 2025**. Ramp's customer base skews US / finance / tech / professional services, so this is a leading indicator on the high-adoption B2B segment, not a clean market-share measure across global enterprise. Pairs with the May 8 [[openai-testing-ads-in-chatgpt-2026-05-08]] consumer-monetization move — both labs are visibly choosing different revenue mixes. — [[techcrunch-anthropic-ramp-business-customers-2026-05-13]]

## Resources
- [[thread-minchoi-gpt-image-2]] — GPT-Image-2 launch
- [[thread-aakashgupta-1b-model]] — efficiency trends referencing GPT-4o vs. GPT-4
- [[forbes-ai-50-2026]] — Forbes 2026 AI 50; revenue and funding data
- [[latent-space-lupsasca-vibe-physics-2026-05]] — Lupsasca interview; OpenAI Science / vibe physics primary source (May 2026)
- [[latentspace-end-of-finetuning-2026-05-13]] — May 2026 finetuning-API deprecation (swyx framing)
- [[techcrunch-anthropic-ramp-business-customers-2026-05-13]] — first Ramp AI Index loss to Anthropic (May 13 2026)
