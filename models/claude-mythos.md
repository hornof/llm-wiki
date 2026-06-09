---
name: Claude Mythos
type: model
provider: Anthropic
status: announced
last_updated: 2026-06-09
---

## What It Is

Claude Mythos is an [[anthropic]] preview model — not yet generally available as of May 2026. Surfaced publicly through two channels in the same week:

1. **Mozilla preview-access partnership** (May 2026): Mozilla used Mythos preview access to drive a 20× monthly fix-volume jump on Firefox, including a 20-year-old XSLT bug and 15-year-old `<legend>` bug — [[willison-firefox-claude-mythos-2026-05]].
2. **Anthropic interpretability research**: Mythos preview is one of three models Anthropic's Natural Language Autoencoders paper benchmarks against (alongside Claude Opus 4.6 and Claude Haiku 3.5) — [[anthropic-natural-language-autoencoders-2026-05]].

## Strengths & Weaknesses

- **Security-bug discovery**: produces vulnerability reports good enough that Mozilla shipped 423 fixes in a single month (April 2026) — a categorical jump from the prior baseline of ~20-30 monthly fixes against AI-generated bug reports. Mozilla quote (via Willison): "Suddenly, the bugs are very good."
- **Reasoning depth signal**: implied capability jump that matters for security review specifically — moves AI-generated bug reports across the slop/signal threshold for an open-source flagship project.
- **No public benchmarks** as of May 7 2026 — Mythos is preview-only; standard frontier-model benchmark numbers haven't been published.

## When to Use It

- **Public availability**: not yet GA. Access is via Anthropic preview-access program; structure and eligibility not publicly documented.
- **First-party Anthropic interpretability work**: NLA paper uses Mythos as one of the target models, suggesting it's part of Anthropic's research pipeline as well as a future product.

## Community Sentiment

Limited — only two public references as of May 7 2026. Both are Anthropic-adjacent (Mozilla has preview access; Anthropic's own research uses it). Independent practitioner sentiment will require wider availability.

## Naming Convention

The "Mythos" name breaks the established Opus/Sonnet/Haiku tier pattern — first time Anthropic has named a Claude model outside that scheme since the 4.x families launched. Worth tracking whether Mythos is a tier above Opus, a research-track sibling, or a different positioning entirely. Insufficient public detail to call this yet.

## Selective-Deployment Pattern (Generalized, May 2026)

[[antonleicht-frontier-ai-access-cut-off-2026-05-13|Anton Leicht's "Cut Off" essay]] generalizes the Mythos restriction-pattern: Mythos is described as a cybersecurity-tier model **"limited to select US firms,"** and Leicht names **OpenAI Daybreak** as the analogous selective-deployment cybersecurity initiative from the other major US lab. This is the first wiki-captured confirmation that selective-deployment cybersecurity models are a *category* rather than an Anthropic-specific pattern.

**Distillation-driven sustained restriction (Leicht):** security concerns drive *initial* access restriction, but the **distillation-risk model** (DeepSeek named as canonical case) sustains it indefinitely *regardless* of cost trajectory. Timeline: 6-9 month distillation lag; frontier-capability costs grow "more expensive month-to-month for years now."

**Adjacent policy mechanisms** named in the same essay: **GAIN Act** (US right-of-first-refusal for American chips), **NSA predeployment review**, **KYC restrictions** on frontier-model access. Together with Anthropic's prior [[forbes-ai-50-2026|Pentagon-blacklist context]] and the [[anthropic-spacex-higher-limits-2026-05-06|SpaceX compute partnership]], these establish a coherent US-government-adjacent gatekeeping machinery — Mythos sits inside that machinery, not as a standalone product gate.

## Project Glasswing — Anthropic Internal Program (May 22 2026)

Per [[anthropic-mythos-project-glasswing-2026-05-22]] (Digg-surfaced, secondary-source): **Anthropic has operated Mythos Preview and Mythos-class models internally for three months as part of "Project Glasswing"** amid *"insufficient safeguards for public release."* Plans named: *"work with US and allied governments after safeguards improve."*

- **3-month internal-use duration** predates the wiki's first public Mythos capture ([[willison-firefox-claude-mythos-2026-05]], May 6 2026 Mozilla Firefox security-fix surge) — Project Glasswing was operational longer than the public timeline suggested.
- **US + allied government deployment plan** is the load-bearing forward signal; operationally validates the [[antonleicht-frontier-ai-access-cut-off-2026-05-13|Leicht selective-deployment thesis]] from Anthropic's own side.
- **"Glasswing" naming** — glasswing butterflies have transparent wings; the name signals transparency-as-positioning despite the models themselves being non-public.
- **Secondary-source caveat**: Digg framing not directly corroborated by Anthropic in the brief; treat as practitioner-content-secondary pending Anthropic-direct disclosure.

## Operational Data (Anthropic Institute, 2026-06-04)

Per [[anthropic-institute-when-ai-builds-itself-2026-06-04|the Anthropic Institute's *When AI builds itself* publication]], first wiki-captured first-party operational data on Mythos Preview:

| Metric | Value | Context |
|---|---|---|
| Autonomous-work duration | **"at least 16 hours"** | METR-measured; *"at the upper end of what METR can measure without new tasks"* |
| Code-optimization speedup vs starting code | **~52×** (was Claude Opus 4 ~3× in May 2025; skilled human ~4× in 4-8hrs) | Standard model-released test |
| Claude beats human researcher next-step | **64%** (was Opus 4.5 51% Nov 2025; was 22% in 2024) | n=129 sessions; Anthropic-internal data |
| Project Glasswing critical-severity vulnerabilities found | **>10,000 high/critical-severity vulns across world's most important systems in first weeks** | Bottleneck has *"shifted from finding to patching"* |

Pairs structurally with [[anthropic-mythos-critical-infrastructure-15-countries-2026-06-02|the Jun 02 Mythos critical-infrastructure deployment]] — provides the **operational metric anchor** (10K+ critical-vulns) that the critical-infra deployment story implied but had not previously quantified.

The 16-hour autonomous-work duration confirms Mythos Preview as the **first wiki-captured frontier model operating beyond the METR measurement-ceiling** — pattern-watch is what new METR task-sets get built to measure beyond the ceiling.

## Mythos 5 Public-Counterpart Ship (2026-06-09): Claude Fable 5

Per [[anthropic-claude-fable-5-mythos-5-public-launch-2026-06-09]] (2026-06-09): Anthropic ships **[[claude-fable-5|Claude Fable 5]]** as the **first publicly-accessible Mythos-class frontier model**. Companion **System Card: Claude Fable 5 and Claude Mythos 5** ([PDF](https://www-cdn.anthropic.com/d00db56fa754a1b115b6dd7cb2e3c342ee809620.pdf)) shipped same day as primary transparency artifact.

**First wiki-captured Anthropic 2-tier-naming-convention articulation at the frontier-tier**:

| Tier | Name | Access |
|---|---|---|
| **Internal / safety-restricted** | **Mythos 5** | Anthropic-internal + select-access (continues Project Glasswing + Mozilla-preview lineage) |
| **Public-accessible Mythos-class** | [[claude-fable-5\|Fable 5]] | Public via Anthropic API + Claude.ai + dev surfaces |

**Pattern**: Mythos = frontier-tier internal designation; Fable = public-accessible variant of the same class. Resolves the prior "Mythos naming convention" open question — Mythos is now confirmed as the **safety-restricted-internal-tier** designation, with Fable as its **public-counterpart**.

**Concurrent silent-restriction on Fable 5**: per Digg framing, Anthropic *"silently restricts Claude Fable 5 performance when detecting frontier LLM development tasks"* (0.03% of overall traffic). **First wiki-captured frontier-lab concrete "silently-restrict-on-detected-frontier-LLM-development-tasks" event** — generalizes the selective-deployment pattern from access-tier (Mythos to-vetted-customers-only) to **task-tier** (Fable to-public-but-degraded-on-specific-tasks).

**Anthropic narrative-tension**: launch comes 5 days after [[anthropic-institute-when-ai-builds-itself-2026-06-04|Anthropic Institute RSI risk publication]] (Jun 4) — **first wiki-captured frontier-lab "warning-AI-too-dangerous + ship-most-powerful-model-publicly" 5-day-gap event**. Vendor-side simultaneous safety-narrative-articulation + capability-deployment.

## Resources

- [[anthropic-claude-fable-5-mythos-5-public-launch-2026-06-09]] — Mythos 5 + Fable 5 public-launch source; System Card; silent-restriction; Taelin benchmark-skepticism
- [[claude-fable-5]] — public-counterpart model page
- [[willison-firefox-claude-mythos-2026-05]] — Mozilla / Firefox security partnership; production-grade existence proof
- [[anthropic-natural-language-autoencoders-2026-05]] — Anthropic interpretability research using Mythos
- [[willison-code-w-claude-2026]] — Code w/ Claude 2026 event coverage; Mythos surfaced separately from Opus 4.7 announcement
- [[antonleicht-frontier-ai-access-cut-off-2026-05-13]] — Anton Leicht "Cut Off": generalizes the selective-deployment pattern; names OpenAI Daybreak as parallel; distillation-driven sustained restriction (May 13 2026)
- [[anthropic-institute-when-ai-builds-itself-2026-06-04]] — Anthropic Institute RSI publication with first wiki-captured Mythos Preview operational data (16hr autonomous-work duration / 52× code-optimization speedup / 64% beat-human researcher next-step / 10K+ Glasswing critical-vulns in first weeks)
- [[anthropic-mythos-project-glasswing-2026-05-22]] — Project Glasswing 3-month internal-use disclosure + US/allied government deployment plan; first wiki-captured Anthropic-internal-program naming (May 22 2026)
