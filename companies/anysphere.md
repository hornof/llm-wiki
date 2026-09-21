---
name: Anysphere (Cursor)
type: company
status: acquired (SpaceX, closed 2026-08-14)
last_updated: 2026-09-20
---

> [!note] Merged page
> `companies/cursor` was folded into this page at lint on 2026-09-14. They were the same legal entity filed twice — **Anysphere is the company, Cursor is the product** — and they had drifted into contradicting each other on the central fact (see the deal timeline below). Inbound `[[cursor]]` links now point here.

## What It Is

**Anysphere** (founded 2022, San Francisco) is the company behind **Cursor**, the AI-first code editor that became the canonical practitioner-tier AI-coding-product surface through 2025-2026. Valued at **$29.3B as of April 2026** on **$3.3B raised**; listed on the Forbes 2026 AI 50.

**Acquired by [[spacex|SpaceX]] in a $60B all-stock merger that closed 2026-08-14**, and now a wholly owned subsidiary. See the deal timeline below.

## The SpaceX deal — dated progression

**Status: CLOSED 2026-08-14.** *(Verified by web lookup 2026-09-20. The wiki carried "close unconfirmed" for five weeks after the deal had actually closed — the projected-close row was treated as an open tracking item when the answer was public. A reminder that "no news" is not evidence of no event; the wiki only knows what was ingested.)* Recorded as a progression rather than a single claim, because the wiki previously held two incompatible versions of it on two pages.

| Date | Claim | Standing |
|---|---|---|
| **2026-06-07** | SpaceX–Cursor acquisition **rumor**, from a comment-thread aside — *"I guess that's why SpaceX decided to acquire them…"* Bundled with two other unverified claims: Cursor valuation **$60B** (vs the $29.3B April figure) and revenue-per-employee *"exceeding Goldman Sachs + Google + Apple combined."* | Speculative. No mainstream-press corroboration captured. — [[linas-cursor-revenue-per-employee-spacex-acquisition-rumor-2026-06-07]] |
| **2026-06-16** | **$60B all-stock merger announced**, projected **Q3 2026 close**. Reported in the 06-16 Daily Brief as confirming and quantifying the Jun 7 rumor. | The strongest surface the wiki holds. Primary deal terms not fetched. — [[spacex-cursor-anysphere-60b-merger-microsoft-cowork-usage-pricing-2026-06-16]] |
| **2026-08-14** | **CLOSED.** SpaceX finalized the all-stock acquisition, confirmed via **SEC Form 8-K**. Subsidiary **X67 Inc.** merged directly into Anysphere; Cursor's common and preferred stock converted into **~389.3M SpaceX shares** (~391M Class A issued in total including assumed RSUs and options). Cursor now operates as a **wholly owned subsidiary**, reportedly folded into a **"SpaceXAI"** division. | **Confirmed** — [SEC 8-K via Yahoo Finance](https://finance.yahoo.com/technology/ai/articles/spacex-completes-record-60-billion-131311785.html), [CNBC (June announcement)](https://www.cnbc.com/2026/06/16/spacex-spcx-cursor-acquisition-ipo.html). *Verified by web lookup 2026-09-20.* |

> [!warning] What went wrong here, kept as a worked example
> For three months the wiki asserted both versions at once. `companies/anysphere` (updated 06-16) stated the merger as fact with `status: acquisition-target`. `companies/cursor` was updated **two weeks later, on 07-01**, and still described the deal as a *"VERIFICATION-CRITICAL"* rumor, never mentioning the 06-16 announcement — so the later-edited page was the staler one. Meanwhile [[codex|tools/codex]] asserted a flat *"Acquired by SpaceX"*, past tense, for a deal that had only been announced. Found by the contradiction sweep in `meta/lint-report-2026-09-13.md`.

If the acquisition completes it extends the [[spacex|SpaceX vertical-integration thesis]] to the AI-coding-tools tier.

## Strategic Position

### SpaceX 3-layer AI vertical integration

| Layer | Asset | Source |
|---|---|---|
| **Compute substrate** | xAI Colossus + Tesla compute capacity | [[willison-anthropic-xai-colossus-2026-05]] |
| **Frontier model** | [[xai\|xAI Grok]] family | xAI organizational anchor |
| **AI-coding product** | **Anysphere / Cursor** | Jun 16 announcement |

Operationalizes [[satya-nadella-frontier-ecosystem-not-frontier-model-2026-06-14|Nadella's *frontier-ecosystem-not-frontier-model* positioning]]: Nadella articulates it at firm-CEO-vocabulary tier; SpaceX executes it as an ecosystem acquisition. Sits in a 3-acquirer 3-day cluster with [[salesforce-fin-ai-3-6b-acquisition-2026-06-15|Salesforce–Fin ($3.6B, Jun 15)]] — the $60B price is **16.7×** larger — and [[openai-ona-acquisition-deployment-simulation-2026-06-16|OpenAI–Ona (Jun 16)]].

### Competitive position

Cursor competes directly with [[claude-code|Claude Code]], Codex and [[goose|Goose]] — i.e. with the labs whose models it depends on. Forbes framed it as a player that *"must innovate to compete"* as the frontier labs move into the coding-agent market, which is the structural tension: a $29.3B valuation built on top of suppliers who are now competitors.

## Traction Signals

- **$3.3B raised; $29.3B valuation** (April 2026) — [[forbes-ai-50-2026]]; Forbes 2026 AI 50 inclusion
- **2026-05-20: doubles Teams-plan usage limits** for new users for one month (announced by Michael Truell on X). One of **three same-month coding-agent retention moves** alongside [[latentspace-codex-rises-claude-meters-2026-05-14|Codex's two-months-free-for-switchers]] and Anthropic's subscription-metering formalization — competing on usage-cap generosity as the cheapest anti-churn lever. — [[dailybrief-roundup-2026-05-21]]
- **2026-06-29: Cursor for iOS** — cloud-agents plus mobile dev-management extension. — [[dailybrief-roundup-2026-06-29]]
- **2026-07-01: scaling forward-deployed-engineer teams for enterprise deployment** (Latent Space). Real-world validation of [[forward-deployed-engineer|Andrew Ng's AI-FDE-vs-AI-Engineer thesis]] (Jun 1); first wiki-captured Cursor FDE enterprise surface. — [[dailybrief-roundup-2026-07-01]]
- Revenue, ARR and customer-count metrics remain **verification-pending**.

## Key People

- **Michael Truell** — CEO. Confirmed via his 2026-05-20 X announcement of the Teams-limits promo ([[dailybrief-roundup-2026-05-21]]).

> [!warning] Unresolved founder attribution
> This page previously stated *"Founded by Tomas Reimers."* That looks like two same-day items from the 06-16 brief getting conflated: Reimers launched **Origin** (a Git-compatible version-control platform for AI agents) on 2026-06-16, the same day the merger was announced. The wiki's only sourced leadership claim for Anysphere is **Michael Truell as CEO**. **Neither attribution is being asserted here** — the founder line needs a primary check before it goes back on the page.

## Internal Org-Design Signal (May 2026, verification-pending)

@Av1dlive on X surfaces a 9-minute Cursor-CEO video claiming Cursor *"ships at 100x speed using team of agents"* and pays engineers **$1.1M/year** to *"run teams of AI agents that ship code while they sleep."* Paraphrased mechanics: engineers manage dozens of parallel agents each on its own remote machine; a validation contract precedes code rather than following it, with humans only at scoping and review; the agent team runs planning → coding → testing → shipping with role-specialized agents.

**Primary not captured** — no Cursor exec quoted directly, video not fetched — and the 100× figure carries no methodology or baseline. Both the speed and comp claims are secondary pending direct verification. Same-week multi-agent-orchestration cluster: [[eng-khairallah-multi-agent-team-course-2026-05-15]], [[sairahul1-solo-founder-13-agent-playbook-2026-05-15]]. — [[av1dlive-cursor-1m-agent-orchestrator-2026-05-15]]

## Resources

- [[spacex-cursor-anysphere-60b-merger-microsoft-cowork-usage-pricing-2026-06-16]] — Jun 16 $60B all-stock announcement
- [[linas-cursor-revenue-per-employee-spacex-acquisition-rumor-2026-06-07]] — Jun 7 rumor, 1st surface
- [[forbes-ai-50-2026]] — AI 50 coverage; competitive framing against Claude Code and Codex
- [[av1dlive-cursor-1m-agent-orchestrator-2026-05-15]] — org-design and agent-orchestrator comp claims
- [[spacex]] — announced acquirer · [[xai]] — SpaceX-side frontier-model layer
- [[claude-code]] — direct competitor · [[ai-50-2026-snapshot]] — coding-agents sector analysis
- [[satya-nadella-frontier-ecosystem-not-frontier-model-2026-06-14]] — the positioning this acquisition operationalizes
- **Origin** — Tomas Reimers's Git-for-AI-agents platform, launched 2026-06-16 (not a tracked entity; see founder-attribution note above)
