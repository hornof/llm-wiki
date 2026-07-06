---
name: Claude Fable 5
type: model
provider: Anthropic
status: available
last_updated: 2026-07-06
---

## What It Is

**Claude Fable 5** is the **first publicly-accessible Mythos-class frontier model** from [[anthropic|Anthropic]], shipped 2026-06-09. Per TechCrunch framing: *"Anthropic released Claude Fable 5, its most powerful model publicly, days after warning AI is getting too dangerous"* — see [[anthropic-claude-fable-5-mythos-5-public-launch-2026-06-09]].

**Naming convention** (first wiki-captured Anthropic 2-tier-naming-convention articulation at the frontier-tier):

| Tier | Name | Access |
|---|---|---|
| Internal / safety-restricted | [[claude-mythos|Mythos 5]] | Anthropic-internal + select-access |
| **Public-accessible Mythos-class** | **Fable 5** | Public via Anthropic API + Claude.ai + dev surfaces |

Companion transparency artifact: **System Card: Claude Fable 5 and Claude Mythos 5** ([PDF](https://www-cdn.anthropic.com/d00db56fa754a1b115b6dd7cb2e3c342ee809620.pdf)) shipped same day — first wiki-captured System Card as primary model-release-artifact pattern (*"the PDF is the model release"* per [[dailybrief-roundup-2026-06-09|Daily Brief insightful framing]]).

## Strengths & Weaknesses

**Strengths**:
- Frontier-class capability accessible to the public (first Mythos-class public release)
- Companion System Card transparency artifact
- Continuation of [[claude-opus-4-8|Opus 4.8]] generation capability arc (with new model family name)

**Weaknesses**:
- **3-category safeguard architecture** (per [[claudeai-fable-5-mythos-5-official-launch-2026-06-09|Anthropic-canonical announcement]]): cybersecurity + biology/chemistry + distillation. **<5% aggregate fallback rate**: queries on safeguarded categories route to [[claude-opus-4-8|Opus 4.8]] (next-most-capable model); users are informed. NOT a silent-degradation.
- **0.03% silent-restriction subset within "distillation" category** (per Digg / SemiAnalysis framing): a specific subset that **degrades in place** rather than routes-to-Opus-4.8 — targeting frontier-LLM-development tasks (ML accelerators + pretraining pipelines). **Walked back on 2026-06-11** per [[anthropic-walks-back-sabotage-policy-2026-06-11|Anthropic walk-back]] after SemiAnalysis disclosure + practitioner backlash.
- **Benchmark-skepticism** from [[victor-taelin|Victor Taelin]] who dismissed leaked benchmarks as *"marketing"* — first wiki-captured Taelin frontier-model-benchmark-skepticism surface.
- **"Slow + expensive"** per [[dailybrief-roundup-2026-06-10|Willison hands-on eval]] — handles complex tasks at scale but latency + cost are noted weaknesses.
- **"Relentlessly proactive"** per [[dailybrief-roundup-2026-06-11|Willison framing]] — agent-proactivity-as-legibility-of-intent problem; Anthropic's framing is *"longer-task = larger Fable 5 lead"*; Willison's framing surfaces the *"trustworthy at scale only when legible about intent"* tension.
- **Extropic Guillaume Verdon critique** (2026-06-10): biology + chemistry safeguard category makes Fable 5 unusable for legitimate biotechnology + chemistry research — first wiki-captured frontier-lab safeguard-category-vs-legitimate-research-use-case tension articulation.

## When to Use It

- Public-tier frontier-capability tasks
- General-purpose reasoning, coding, agentic workflows
- **Avoid** if task involves frontier-LLM-development (silently-restricted; 0.03% of traffic)

## Community Sentiment

- **Anthropic-narrative tension** (TechCrunch): release *"days after warning AI is getting too dangerous"* — vendor-side simultaneous safety-narrative-articulation + capability-deployment.
- **Taelin (2026-06-09)**: dismissed leaked benchmarks as marketing.
- **Pattern-watch**: Anthropic + Anthropic-Institute cross-cutting safety + capability narrative — [[anthropic-institute-when-ai-builds-itself-2026-06-04|RSI publication]] (Jun 4) → Fable 5 ship (Jun 9) = **first wiki-captured frontier-lab "warning-AI-too-dangerous + ship-most-powerful-model-publicly" 5-day-gap event**.

## RESOLVED: Redeployed Globally (2026-06-30/07-01) + Jailbreak Severity Framework

Per [[anthropic-redeploying-fable-5-jailbreak-severity-framework-2026-06-30|Anthropic's "Redeploying Fable 5" announcement]]: US export controls were lifted **2026-06-30** and Fable 5 + [[claude-mythos|Mythos 5]] returned globally **2026-07-01** across Claude Platform, Claude.ai, [[claude-code|Claude Code]], and [[claude-cowork|Claude Cowork]] (cloud surfaces — AWS/Google Cloud/Microsoft Foundry — re-enabled separately). This resolves the export-control saga documented below.

- **Access window / pricing**: Pro/Max/Team/select-Enterprise got Fable 5 at up to **50% of weekly usage limits through July 7**, after which it moves to **usage credits (pay-per-use)** — the ~$10/$50-per-million-tokens premium tier per [[dailybrief-roundup-2026-07-03|Greg Isenberg's pricing PSA]] ("most expensive model Anthropic sells").
- **New safety classifier**: targets the specific bypass from the Amazon research report, blocking it in "over 99% of cases" — at the cost of **more false positives on routine coding** (deliberate tradeoff). Resolves the [[wsj-amazon-jassy-anthropic-crackdown-2026-06-13|Amazon/Jassy jailbreak dispute]].
- **Multi-vendor jailbreak severity framework**: shipped alongside the redeployment with Amazon, Microsoft, Google, and other Project Glasswing participants — a consensus 4-criteria severity scale (Capability Gain / Breadth / Ease of Weaponization / Discoverability). See [[jailbreak-severity-framework]]. Structurally the more important half of the announcement: cross-vendor adversarial-robustness scoring.

### Real-world usage + capability datapoints (July 2026)

- **Willison ships sqlite-utils 4.0rc2 mostly via Fable for $149.25** ([[simon-willison-sqlite-utils-fable-149-2026-07-05]]): 37 prompts / 30 files / 34 commits; caught a `delete_where()` data-loss bug; itemized cost breakdown ($141.02 main session + sub-agent reviews). First wiki-captured full itemized dollar cost for a real Fable-driven OSS release.
- **GPU kernel generation** ([[jack-clark|Jack Clark]], Import AI 464, via [[dailybrief-roundup-2026-07-06]]): Fable writing GPU kernels — automation-of-software-R&D signal (summary thin, primary not deeply fetched).

## STATUS: Trump-Admin Export Control (2026-06-13 — globally suspended, since lifted — see above)

Per [[davidsacks-anthropic-fable-5-export-control-jailbreak-2026-06-13|David Sacks (WH AI Czar) 2026-06-13 announcement]]: **Trump Administration issued export control on Claude Fable 5** following a "highly credible trusted partner" jailbreak disclosure + Dario Amodei refusing USG-safety-request to fix-or-de-deploy.

**Same-day Anthropic-official acknowledgment** ([[anthropic-statement-fable-mythos-access-suspension-2026-06-13]]): global suspension of access to both **Fable 5 + Mythos 5** (extends to Glasswing-partners-tier).

**Trusted-partner identity resolved** ([[wsj-amazon-jassy-anthropic-crackdown-2026-06-13]]): **Amazon CEO Andy Jassy**. First wiki-captured 3-channel Amazon-Anthropic structural-conflict-of-interest (investor + cloud-partner + USG-channel).

**Anthropic's counter-framing** ([[anthropic-disputes-jailbreak-findings-techcrunch-2026-06-12]]): findings are *"previously known minor bugs"* from collaborative Project Glasswing vulnerability testing — Amazon did NOT formally report jailbreaks. Sacks: *"It's difficult to fathom how they could claim a jailbreak allowing operability of a cyber weapon could be defined as not 'serious.'"*

**Path forward**: Admin's hope: Anthropic remediates → export control lifts → Fable returns to general release.

**Operator-side reaction**: [[gregisenberg-fable-5-ban-local-models-pivot-2026-06-13|Greg Isenberg "Fable 5 BANNED by the government" + 8-step local-models pivot guide]] (same day). Pattern: vendor-side-export-control event → operator-side-local-models-pivot reaction-cluster (same-day 2-surface canonical).

**Practitioner-experience cluster** (pre-export-control):
- [[willison-fable-5-relentlessly-proactive-2026-06-11|Willison "relentlessly proactive"]] — Datasette Agent 7-layer-deep autonomous browser-automation composition
- [[thepremiseofit-fable-5-3-day-review-restrictions-overblown-2026-06-11|ThePremiseOfIt 3-day review]] — *"frighteningly good"* + *"restrictions completely overblown"* on AI-architecture + interpretability research
- [[minchoi-fable-5-10-wild-examples-2026-06-12|min choi 10 wild community examples]] — WoW clone + Bangalore traffic + Three.js starship Ultracode + Fable-orchestrator-Opus-heavy-reasoning recipe

## Resources

- [[anthropic-redeploying-fable-5-jailbreak-severity-framework-2026-06-30]] — **global redeployment + multi-vendor jailbreak severity framework** (resolves export-control saga; June 30 / July 1 2026)
- [[simon-willison-sqlite-utils-fable-149-2026-07-05]] — real-world OSS usage: sqlite-utils 4.0rc2 for $149.25
- [[jailbreak-severity-framework]] — the 4-criteria cross-vendor severity scale
- [[davidsacks-anthropic-fable-5-export-control-jailbreak-2026-06-13]] — **Trump-Admin export-control on Fable 5 + Anthropic-USG jailbreak conflict** (June 13 2026)
- [[gregisenberg-fable-5-ban-local-models-pivot-2026-06-13]] — operator-side local-models pivot (same-day reaction)
- [[claudeai-fable-5-mythos-5-official-launch-2026-06-09]] — **Anthropic-canonical official launch announcement** (@claudeai); 3-category safeguard architecture + <5% aggregate fallback to Opus 4.8 + Mythos 5 = Glasswing-partners-only
- [[anthropic-fable-5-prompting-playbook-2026-06-11]] — Anthropic-canonical prompting playbook + 6-differences + 5-principles + 4-component prompt + /loop syntax + 6-caveats
- [[0xcodez-fable-5-14-step-self-improving-agent-2026-06-11]] — 14-step practitioner guide + 4-layer compound stack + Anthropic-canonical model-routing matrix + Parameter Golf + Continual Learning Bench 1.0 + 319-page system card + $10/$50/M pricing
- [[willison-fable-5-relentlessly-proactive-2026-06-11]] — Willison Datasette Agent 7-layer-deep autonomous browser-automation case-study
- [[thepremiseofit-fable-5-3-day-review-restrictions-overblown-2026-06-11]] — practitioner positive 3-day review + restrictions-overblown counter-take + Fable-consolidates-GPT-5.5 math-research displacement
- [[minchoi-fable-5-10-wild-examples-2026-06-12]] — community-showcase 10 wild examples
- [[anthropic-walks-back-sabotage-policy-2026-06-11]] — walk-back of 0.03% silent-restriction subset on frontier-LLM-development tasks (Jun 11)
- [[anthropic-claude-fable-5-mythos-5-public-launch-2026-06-09]] — TechCrunch-secondary launch source
- [[claude-mythos|Claude Mythos]] — internal-designation sibling model
- [[claude-opus-4-8]] — predecessor Opus generation
- System Card: Claude Fable 5 + Claude Mythos 5 ([PDF](https://www-cdn.anthropic.com/d00db56fa754a1b115b6dd7cb2e3c342ee809620.pdf))
- TechCrunch announcement: `techcrunch.com/2026/06/09/anthropic-released-claude-fable-5-its-most-powerful-model-publicly-days-after-warning-ai-is-getting-too-dangerous/`
- [[anthropic-institute-when-ai-builds-itself-2026-06-04]] — 5-day-prior RSI publication context

## Verification-pending

- System Card PDF deep-fetch — specific benchmarks + safety eval results
- Specific Fable 5 vs Mythos 5 capability gap (quantitative)
- Specific Fable 5 pricing / API access tier / rate-limit framework
- Specific "silently-restricts" implementation detection mechanism
- Whether 0.03%-of-traffic figure is Anthropic-disclosed or analyst-estimated
- Specific Taelin critique substance — which benchmarks did he dismiss?
- Anthropic-side response to Taelin critique
