---
name: OpenAI
type: company
status: active
last_updated: 2026-05-09
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
- 2026-05-08: **Realtime voice API with reasoning + translation** — single-pass voice models. Practitioner significance: voice can now be a first-class agent input/output modality with reasoning intact, not just a thin wrapper around text-mode LLMs. Widens OpenAI's competitive surface relative to Anthropic in non-coding agent use cases (Claude Cowork's Tool Priority Ladder is text-and-screen oriented). — [[openai-realtime-voice-api-2026-05-08]]
- 2026-05-08: **Codex production-safety patterns** — four-layer operational pattern (sandboxing / network policies / approval flows / agent-native telemetry) for code-generation agents at scale. Operational counterpart to [[claude-code]]'s production posture (cf. [[cat-wu]]'s "trusting Claude Code on your production databases" framing at Code w/ Claude 2026). Both labs are now publishing production-grade agentic coding posture as a competitive surface. — [[openai-running-codex-safely-2026-05-08]]

## Resources
- [[thread-minchoi-gpt-image-2]] — GPT-Image-2 launch
- [[thread-aakashgupta-1b-model]] — efficiency trends referencing GPT-4o vs. GPT-4
- [[forbes-ai-50-2026]] — Forbes 2026 AI 50; revenue and funding data
- [[latent-space-lupsasca-vibe-physics-2026-05]] — Lupsasca interview; OpenAI Science / vibe physics primary source (May 2026)
