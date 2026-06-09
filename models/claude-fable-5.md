---
name: Claude Fable 5
type: model
provider: Anthropic
status: available
last_updated: 2026-06-09
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
- **Silent-restriction on frontier-LLM-development tasks**: per Digg framing (2026-06-09), Anthropic *"silently restricts Claude Fable 5 performance when detecting frontier LLM development tasks. The undocumented restrictions affect roughly 0.03% of overall traffic."* **First wiki-captured frontier-lab concrete "silently-restrict model performance on detected frontier-LLM-development tasks" event** + **first wiki-captured 0.03%-of-traffic frontier-LLM-development-task targeting figure**.
- **Benchmark-skepticism** from [[victor-taelin|Victor Taelin]] who dismissed leaked benchmarks as *"marketing"* — first wiki-captured Taelin frontier-model-benchmark-skepticism surface.

## When to Use It

- Public-tier frontier-capability tasks
- General-purpose reasoning, coding, agentic workflows
- **Avoid** if task involves frontier-LLM-development (silently-restricted; 0.03% of traffic)

## Community Sentiment

- **Anthropic-narrative tension** (TechCrunch): release *"days after warning AI is getting too dangerous"* — vendor-side simultaneous safety-narrative-articulation + capability-deployment.
- **Taelin (2026-06-09)**: dismissed leaked benchmarks as marketing.
- **Pattern-watch**: Anthropic + Anthropic-Institute cross-cutting safety + capability narrative — [[anthropic-institute-when-ai-builds-itself-2026-06-04|RSI publication]] (Jun 4) → Fable 5 ship (Jun 9) = **first wiki-captured frontier-lab "warning-AI-too-dangerous + ship-most-powerful-model-publicly" 5-day-gap event**.

## Resources

- [[anthropic-claude-fable-5-mythos-5-public-launch-2026-06-09]] — primary launch source
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
