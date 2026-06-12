---
name: Claude Fable 5
type: model
provider: Anthropic
status: available
last_updated: 2026-06-11
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

## Resources

- [[claudeai-fable-5-mythos-5-official-launch-2026-06-09]] — **Anthropic-canonical official launch announcement** (@claudeai); 3-category safeguard architecture + <5% aggregate fallback to Opus 4.8 + Mythos 5 = Glasswing-partners-only
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
