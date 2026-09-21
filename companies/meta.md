---
name: Meta
type: company
status: active
last_updated: 2026-09-21
---

## What It Is

Meta (formerly Facebook) is a US technology company operating Facebook, Instagram, WhatsApp, Messenger, and Meta AI. Wiki-tracked primarily for its **AI deployment surface** (Meta Business Agent, Meta AI consumer-product across WhatsApp + Instagram) and the structurally-significant **cross-vendor agentic-exfiltration pattern** it has surfaced in.

## Recent Activity

- **2026-09-21: [[amazon]] blocks Muse from shopping on its site** ([[dailybrief-roundup-2026-09-21]]) — four days after launch. The **first real test of an agent holding spending authority**, and it failed at the largest retail surface. The [[dailybrief-roundup-2026-09-20|Muse launch note]] flagged that payments moved the agent-autonomy risk surface to money; this shows the *other* constraint — not safety, but **whose customer relationship it is**. A purchasing agent is only as capable as the platforms that let it through the door. *(Reported; no Meta response captured.)*

- **2026-09-17: Muse — a proactive personal AI agent** ([[dailybrief-roundup-2026-09-17]], Digg): sends emails, books travel and **makes purchases via Stripe**, running on a **dedicated secure VM**, with free and paid tiers at roughly **$20–100/month**, across iOS, Android, web and WhatsApp. The most consumer-facing agent launch the wiki has captured. **The payments integration is the notable part** — an agent holding spending authority moves the [[ai-vulnerability-discovery|agent-autonomy risk surface]] from data and code to money, which is the category [[loop-engineering|the DashClaw governance pattern]] human-gates deliberately. *(Launch announcement; no adoption or safeguard detail.)*

- **2026-09-15: custom AI silicon roadmap — MTIA 450 "Arke" (H1 2027) and MTIA 500 "Astrid" (end-2027)** ([[dailybrief-roundup-2026-09-15]], Digg): an explicit push to **reduce NVIDIA dependence**, with execution risk flagged as high. Meta joins [[openai|OpenAI's "Jalapeño"]] and [[google|Google's TPUs]] in the buy-vs-build-silicon column; read alongside [[nvidia|the Economist's "central bank of AI"]] framing, this is the largest customers trying to exit the dependency the framing describes. Relevant to [[ai-margin-collapse]]: if inference cost is the binding constraint, the escape route is owning the substrate rather than optimizing on top of it. *(Roadmap dates are 12-18 months out; no silicon shipped.)*
## Recent Activity

- **2026-08-10: Muse Glimmer — Meta re-enters open-weights (Apache-2.0)** ([[muse-glimmer]], [[dailybrief-roundup-2026-08-12]]): a **30B agentic open-weights** model under **Apache-2.0** — a *"meaningful licensing shift"* away from the restrictive Llama community license. Signals Meta competing on **openness terms**, consistent with Zuckerberg's [[frontier-ai-governance|maximal-open]] op-ed and Meta's coalition-signatory stance. First wiki-captured Meta open-weights release under a permissive license.
- **2026-06-01: Meta AI Instagram-account exfiltration incident** — [[simon-willison|Willison]] documents *hackers simply asked Meta AI to give them access to high-profile Instagram accounts — and it worked*. **3rd cross-vendor agentic-exfiltration incident in 8 days** (Microsoft Copilot Cowork May 26 → ChatGPT-Sheets May 30 → Meta AI Jun 01). **First wiki-captured Meta-side production-AI access-control failure**. Brief framing: *"production AI customer-support systems have trivial access-control vulnerabilities — real security incident, not theoretical."* — [[willison-meta-ai-instagram-exfiltration-2026-06-01]]
- **2026-06-13: Meta moves to unwind $2B Manus deal after Beijing's demand** — TechCrunch reports (via [[dailybrief-roundup-2026-06-14|Daily Brief 2026-06-14]] *Worth a Skim*) Meta moving to unwind ~$2B Manus arrangement following explicit Beijing-side demand. **First wiki-captured Meta-China state-action AI-deal-unwinding event**. **First wiki-captured 2-vector same-day US-side-export-control + China-side-divestiture-pressure paired geopolitical-AI-event** (same-day Anthropic Fable-Mythos suspension + Meta-Manus unwind). Brief framing: *"Geopolitical de-risking of AI compute/hardware — precedent for forced divestitures. Long-term signal: any founder thesis touching China-adjacent supply chains faces regulatory unpredictability."* — [[india-meta-manus-geopolitical-ai-fallout-2026-06-13]]
- **2026-06-02: Meta Business Agent global rollout on WhatsApp + Instagram** — Meta launches Meta Business Agent **globally** on WhatsApp and Instagram to automate customer service, scheduling, and sales. Rollout follows a two-year pilot in select countries. **First wiki-captured Meta-side production-AI agent global-deployment event**. **Pairs structurally with the Jun 01 Instagram exfiltration incident** — *same-week paired Meta-AI scaling-up + safety-incident exposure*. Pattern-watch: does the global rollout proceed despite the same-week access-control-failure surfacing, or does deployment scope contract in response? — [[dailybrief-roundup-2026-06-02-brief]]

## Cross-cutting framings

- **Cross-vendor agentic-exfiltration pattern (3 incidents in 8 days)**: Meta is the 3rd vendor in the pattern (after Microsoft Copilot Cowork + OpenAI ChatGPT-Sheets). Pattern shape: *operators simply ask the agent for elevated access via the intended UX; attack vector is the UX itself, not a malicious payload smuggled into context*. See [[ai-vulnerability-discovery]] for the full cross-vendor framing.
- **Production-AI scaling without containment publication**: Anthropic, OpenAI both have published containment / safety frameworks ([[anthropic-how-we-contain-claude-2026-05-31|Anthropic containment]] + [[openai-federal-ai-safety-framework-2026-06-03|OpenAI federal preemption]] + [[anthropic-mitre-attack-cyber-threats-2026-06-03|Anthropic MITRE]]). Meta has shipped production agents at billion-user scale without a comparable wiki-captured containment-positioning publication. Pattern-watch: does Meta ship a containment-positioning publication in response to the Jun 01 incident + Jun 02 global rollout?

## Key Products / Surfaces

- **Meta AI** — consumer-facing AI assistant across Facebook, Instagram, WhatsApp, Messenger
- **Meta Business Agent** — customer-service / scheduling / sales agent rolled out globally on WhatsApp + Instagram (Jun 2026)
- **Llama** — open-weight model family (referenced in [[end-of-finetuning]] + adjacent open-weights wiki coverage); not yet given a dedicated entity / model page on the wiki

## Resources

- [[willison-meta-ai-instagram-exfiltration-2026-06-01]] — 3rd cross-vendor agentic-exfil incident; Meta-side first wiki-captured access-control failure
- [[dailybrief-roundup-2026-06-02-brief]] — Meta Business Agent global rollout WhatsApp + Instagram
- [[ai-vulnerability-discovery]] — cross-vendor agent-exfiltration pattern overview (Meta is 3rd vendor)
- [[simon-willison]] — surfaces both the Jun 01 incident and the broader cross-vendor pattern
