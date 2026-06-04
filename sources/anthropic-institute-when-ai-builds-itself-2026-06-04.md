---
title: "Anthropic Institute — When AI builds itself: progress toward recursive self-improvement and its implications (2026-06-04)"
type: source
medium: article
url: https://www.anthropic.com/institute/recursive-self-improvement
ingested: 2026-06-04
---

## Summary

The **Anthropic Institute** publishes *"When AI builds itself"* (2026-06-04) — the first major Anthropic Institute publication to land in the wiki and **first wiki-captured first-party Anthropic data on recursive self-improvement (RSI)**. Co-authored by **Marina Favaro** and [[jack-clark|Jack Clark]] (editorial support: Santi Ruiz; data: Brian Calvert + Jun Shern Chan; feedback contributors include Anton Korinek, Holden Karnofsky, Avital Balwit, Andy Jones). The piece argues *"AI is already accelerating the development of AI systems"* using previously unreported internal Anthropic data, and explicitly asks for a **verifiable global frontier-AI slowdown mechanism** as a tool the Institute will research. Amplified same-day by [@AnthropicAI](https://x.com/AnthropicAI/status/2062568862479208923).

## Key Claims / Takeaways

### Headline data points (first-party Anthropic)

| Metric | Value | Time-window |
|---|---|---|
| Code per Anthropic engineer per quarter | **8× Q2 2024 level** | Q2 2026 |
| Anthropic-merged code authored by Claude | **>80%** | May 2026 (was *"low single digits"* before Claude Code Feb 2025) |
| Open-ended task success rate | **76%** (up 50 percentage points in 6 months) | May 2026 |
| Code optimization speedup vs starting code | Mythos Preview **~52×** (was Opus 4 ~3× in May 2025; skilled human ~4× in 4-8 hours) | April 2026 |
| Claude beats human researcher next-step | Mythos **64%** (was Opus 4.5 51% Nov 2025; was 22% in 2024) | April 2026 |
| Mythos Preview autonomous-work duration | **"at least 16 hours"** (METR-measured; *"at the upper end of what METR can measure without new tasks"*) | 2026 |
| Anthropic API-error-fix campaign | **800 fixes reducing a class of API errors by 1000×** (engineer estimate: a human would have taken 4 years) | April 2026 |
| Project Glasswing | **"more than ten thousand high- and critical-severity software vulnerabilities across the world's most important systems in its first weeks"** — bottleneck has shifted from finding to patching | First weeks of operation |

### METR time-horizon doubling acceleration

The task-length that AI models can *reliably complete on their own* now doubles **roughly every 4 months** (up from the earlier ~7-month trend). Trajectory:

- March 2024: Claude Opus 3 → 4-minute software tasks
- ~1 year later: Claude Sonnet 3.7 → ~1.5-hour tasks
- ~1 year after that: Claude Opus 4.6 → 12-hour tasks
- **If the trend holds**: skilled-person-*days* tasks come into range *this year* (2026); skilled-person-*weeks* tasks by 2027

**First wiki-captured Anthropic-Institute-side confirmation of the METR time-horizon doubling acceleration** — pairs with [[ai-labor-market-impacts|the Timeline-Calibration Hexangle]] as a first-party-frontier-lab anchor.

### April 2026 W2S researcher result — Claude running open-ended research end-to-end

Anthropic's [automated W2S researcher publication](https://alignment.anthropic.com/2026/automated-w2s-researcher/) (April 2026, primary not wiki-captured yet): Claude-powered agents tackled an open AI-safety question (*can a weaker model reliably supervise a stronger one?*) end-to-end:

- **Two human researchers in ~1 week**: recovered ~23% of the floor-to-ceiling gap
- **Agents in 800 cumulative hours / ~$18K compute**: recovered **97% of the gap**
- Humans still chose the problem and created the scoring rubric; agents designed every experiment themselves

**First wiki-captured concrete data point on the "Claude-runs-open-ended-research-end-to-end" capability**. Pairs structurally with [[altman-three-observations-2025-02|Altman's "1,000 software-engineering agents" thought experiment]] — now operationally demonstrated at Anthropic, with caveats (didn't transfer cleanly to production-scale models).

### The narrowing-human-role 5-stage progression (timeline visualized in essay)

| Era | Description |
|---|---|
| 2021–2023 | Building the first Claude — work like any tech company; humans write code + docs |
| 2023–2025 | Chatbots — humans use early chatbots for snippets; copy-paste output |
| 2025–2026 | Coding agents — agents write and edit code on their own, sometimes entire files |
| **Today (mid-2026)** | **Autonomous agents — agents run code themselves and delegate hours of work to other agents** |
| "20XX?" | Closing the loop — agents become capable enough to build and train models themselves |

### The 3-scenario future framework

1. **The trend stalls, but today's capabilities are widely diffused** (essay rates this *"not likely"* — *"every capability we can measure has so far followed the same curve. We have not yet seen that curve bend"*). Even in this scenario, [[claude-mythos|Project Glasswing]]'s 10K+ vulnerability finding rate has *"already shifted the bottleneck from finding to patching"*, and 100-person companies can do the work of 1,000-person companies.
2. **AI labs continue to see compounding efficiency gains; humans set direction, AI executes** (essay's most-likely scenario). *"100-person companies could do the work of 10,000- or 100,000-person organizations"* — but **Amdahl's law applies**: speeding up one part of the process shifts the bottleneck elsewhere. Anthropic has *"already encountered one signature of Amdahl's law: as we've begun to push more code around the organization, human code review has become a new bottleneck."*
3. **Full recursive self-improvement: AI builds its successors** — pace of AI progress becomes *"determined entirely by the availability of compute (or the speed of discovering various efficiencies in algorithmic training or inference) for AI systems."* Humans move to oversight/validation/verification of an expanding *"virtual lab"*. **Alignment is the load-bearing uncertainty**: rare misalignment in today's models could *"compound as the models build their successors, growing more frequent but less understood until we lose control of them."*

### Verifiable global slowdown ask

> *"It would be good for the world to have the option to slow or temporarily pause frontier AI development to enable societal structures and alignment research to keep up with the advance of the technology. The Anthropic Institute will conduct research—in collaboration with many others—and take actions to help build the systems that a credible slowdown or pause would require."*

**First wiki-captured concrete frontier-lab commitment to building verifiable-slowdown infrastructure**. Frames the problem at arms-control-detection-and-verification scale, explicitly citing the Intermediate-Range Nuclear Forces Treaty as a (multi-decade) precedent. Notes the verification-vs-detectability asymmetry: training runs are *"far easier to conceal than missile silos."*

**Required conditions**: multiple well-resourced labs at or near the frontier, in multiple countries, agreeing to stop under the same conditions, with verification mechanisms. A unilateral pause by one lab *"changes who the front-runner is, but does not create the wider deliberative process that is currently missing."*

### Footnote 4 — GitHub commit-volume data cross-confirms [[github-daigle-agent-strategy-2026-06-03]]

> *"This surge in code production is straining the infrastructure everyone shares. GitHub—the platform most of the world's software is built on—saw roughly **one billion code commits in all of 2025**; by mid-2026 it saw **275 million a week, on pace for roughly 14 billion over the year**. The company's COO has said that it is 'pushing incredibly hard' on capacity just to keep up."*

**First wiki-captured concrete cross-confirmation of the [[github-daigle-agent-strategy-2026-06-03|GitHub Daigle platform-strain framing]]** with concrete commit-volume numbers — **14× year-over-year code commit volume growth** at GitHub. Pairs with Kyle Daigle's brief framings on platform-side bottleneck-shift.

### Anthropic Institute as research arm

This is the **first wiki-captured concrete Anthropic Institute publication**. The Institute was referenced in prior wiki sources but never directly captured. The publication establishes:

- **Authorship pattern**: dedicated co-author pair (Favaro + Clark) with editorial support + visuals team + data team + extensive feedback-contributor list (includes [[anton-korinek|Anton Korinek]] from [[import-ai-456-clark-rsi-radical-optionality-2026-05-11|Import AI 456 RSI-growth-modeling]])
- **Research agenda commitment**: verifiable-slowdown infrastructure
- **Convening role**: *"in the coming months, we will organize conversations where policymakers, researchers, civil society, and other AI companies can help answer some of the questions this piece raises"*

### Cross-cutting framings

- **First-party-Anthropic-data is the strongest [[ai-roi-gap|ROI-gap Read-A]] counter-anchor to date**: capital allocators saw 8× per-engineer productivity + 76% open-ended success + 50pt jump in 6 months = *capital correctly pricing the trajectory*. Cuts cleanly against [[cyb3rops-four-stages-ai-coding-hype-2026-05-26|cyb3rops grind-phase framing]] from the inside — Anthropic's *"engineer subjective estimate ~4× productivity"* + measured 8× lines-of-code corroborate the productivity gain even after Anthropic's own *"true uplift somewhat lower"* caveat.
- **Anthropic-as-experiment Read-A position**: the *"100-person can do work of 10,000-100,000-person"* framing makes Anthropic itself the operational instantiation of [[saas-disruption-thesis|the SaaS-disruption thesis]]. **First-party frontier-lab data confirming the org-scale-collapse mechanism**.
- **13th component of the same-week Anthropic strategic-coordination bundle** (was 12 after [[anthropic-mitre-attack-cyber-threats-2026-06-03]]): capital + capability + values + curriculum + workflows + revenue + talent + containment + distribution + IPO-readiness + critical-infra-scaling + threat-intel-mapping + **RSI-position-paper-and-slowdown-research-commitment**.
- **Pairs structurally with [[import-ai-456-clark-rsi-radical-optionality-2026-05-11|Korinek RSI growth-regime modeling]]**: Korinek's bracketed-trajectory framework (RSI growth upside) gets its concrete-evidence anchor from this publication. *Same author (Clark) on both* — Import AI is the editorial-curation surface; the Institute publication is the first-party-data-laden surface. **First wiki-captured paired Clark-side bracketed-trajectory framework completion** (Korinek RSI upside + Clark extinction-risk-pricing downside + this publication first-party-evidence anchor = three-leg complete framework).
- **Pairs with [[andrewng-ai-fde-vs-ai-engineer-2026-06-01|Ng's 5 future-specialist-role predictions]]**: the essay's *"the human role is narrowing at each step in the AI development process. Once human- and AI-authored code quality reach parity, humans will stop writing code entirely, and shift to only reviewing it. But if they can't review code as quickly as Claude can generate it, human review will become the bottleneck"* — the Amdahl's-law-bottleneck-shift implies which of Ng's 5 roles (LLMOps + Evals + AI Data + Harness + FDE) absorb the displaced engineering capacity. **First wiki-captured first-party-frontier-lab confirmation that human code-review is the operational bottleneck.**
- **First wiki-captured concrete Glasswing operational data**: 10K+ critical vulnerabilities in first weeks. Pairs with [[anthropic-mythos-critical-infrastructure-15-countries-2026-06-02|Mythos critical-infra deployment]] + [[anthropic-mitre-attack-cyber-threats-2026-06-03|MITRE ATT&CK mapping]] as **3-layer defensive-deployment-and-disclosure feedback loop concrete-instantiation** with measured operational metrics.
- **Pairs with [[github-daigle-agent-strategy-2026-06-03|GitHub Daigle platform-strain framing]]**: footnote 4 supplies the concrete numbers (1B commits 2025 → 14B annualized 2026 = 14× growth) for the structural problem Daigle articulated. **First wiki-captured cross-vendor confirmation** of the GitHub platform-strain framing with first-party data from a separate frontier lab.
- **Pairs with [[anthropic-how-we-contain-claude-2026-05-31|Anthropic containment publication]]** + RSI-position-paper as **paired-week Anthropic position-paper sequence**: containment (May 31) + critical-infra-scaling (Jun 02) + MITRE mapping (Jun 03) + RSI position paper (Jun 04). **4 Anthropic Institute / safety-positioning publications in 5 days**.

### Authorship + feedback notes worth surfacing

- **Co-authors**: Marina Favaro + [[jack-clark|Jack Clark]]. **First wiki-captured Marina Favaro surface** (new entity-page-candidate). Jack Clark's 3rd wiki surface (Import AI 456 + 459 + this).
- **Editorial**: Santi Ruiz.
- **Visuals**: Shan Carter + Romello Goodman + Nikki Makagiansar.
- **Data**: Brian Calvert + Jun Shern Chan.
- **Feedback contributors**: Daniel Freeman, Jim Baker, Max Young, Sarah Pollack, Francesco Mosconi, Holden Karnofsky, Andy Jones, **Anton Korinek**, Meg Tong, Andrew Ho, Dan Altman, Drake Thomas, Jack Shen, Sasha de Marigny, Avital Balwit.
- **Notable**: Anton Korinek (RSI growth-regime modeling from Import AI 456) and Holden Karnofsky (Open Philanthropy / longtermism-adjacent) both listed as feedback contributors — **establishes the Anthropic Institute as connected to broader AI-governance research ecosystem**.

### Notably-absent

- **No explicit timeline for full RSI** — the *"20XX?"* placeholder is deliberately vague; the essay declines to commit to a year.
- **No quantitative break-even or threshold for *when* RSI becomes plausible** — the framing remains scenario-based rather than predictive.
- **No mention of [[openai|OpenAI]] / [[google-deepmind|Google DeepMind]] / [[xai|xAI]]** as RSI-trajectory competitors — Anthropic is framing the slowdown ask without naming peers.
- **No specific Anthropic Institute organizational details** (size, budget, governance, research agenda beyond verifiable-slowdown work).
- **No mention of [[anthropic-s1-filing-2026-06-01|Anthropic S-1 filing]]** despite the publication landing 3 days post-filing — *deliberate separation of policy-positioning from corporate-finance positioning, or coincidence?*

## Pages Updated

- [[anthropic]] — Anthropic Institute publication added as 13th-component-of-bundle; first-party productivity data section added
- [[jack-clark]] — 3rd wiki surface added as co-author of Anthropic Institute RSI publication
- [[marina-favaro]] — **new entity page created** at first-wiki-surface-as-frontier-lab-publication-co-author
- [[recursive-self-improvement]] — **new concept page created** as load-bearing organizing-frame for the RSI thesis
- [[claude-mythos]] — Mythos Preview operational data (16hr+ continuous; 52× code-optimization speedup; 64% beat-human next-step; 10K+ Glasswing critical-vulns in first weeks) added
- [[ai-labor-market-impacts]] — Anthropic-Institute-side first-party time-horizon anchor + 8× per-engineer productivity data added to the Timeline-Calibration framework
- [[ai-roi-gap]] — Anthropic Institute first-party data added as strongest Read-A counter-anchor to date
- [[saas-disruption-thesis]] — *"100-person company doing work of 10,000-100,000-person"* first-party framing added as confirmation of org-scale-collapse mechanism
- [[github]] — footnote 4 cross-confirmation (1B → 14B commits/year) added as concrete platform-strain data
- [[ai-vulnerability-discovery]] — Glasswing 10K+ critical-vuln operational metric added
- [[anton-korinek]] — listed as feedback contributor; pairs with Import AI 456 RSI-growth-regime modeling (entity-page-candidate flagged if not already existing)

## Adjacent sources

- [[anthropic-how-we-contain-claude-2026-05-31]] — paired-week containment publication; pairs structurally as the safety-positioning sibling
- [[anthropic-mitre-attack-cyber-threats-2026-06-03]] — same-week (Jun 03) MITRE ATT&CK mapping; 12th-component-of-bundle prior to this publication
- [[anthropic-mythos-critical-infrastructure-15-countries-2026-06-02]] — same-week (Jun 02) Mythos critical-infra deployment; provides the Glasswing operational context this publication supplies the 10K-vuln number for
- [[anthropic-s1-filing-2026-06-01]] — IPO filing 3 days prior; notable separation of policy-positioning from corporate-finance positioning
- [[import-ai-456-clark-rsi-radical-optionality-2026-05-11]] — Korinek RSI growth-regime modeling that this publication anchors with first-party-evidence
- [[import-ai-459-clark-oversight-protein-extinction-2026-06-01]] — Clark extinction-risk-pricing surface; same Clark author
- [[github-daigle-agent-strategy-2026-06-03]] — Daigle platform-strain framing that footnote 4 confirms with concrete numbers
- [[altman-three-observations-2025-02]] — *"1,000 software-engineering agents"* thought experiment that the W2S researcher result operationally demonstrates
- [[andrewng-ai-fde-vs-ai-engineer-2026-06-01]] — Ng's 5-future-specialist-role predictions; Anthropic confirms human code-review as operational bottleneck

## Verification-pending

- Whether the >80% Claude-authored code metric uses the same attribution pipeline across the Q2 2024 → Q2 2026 comparison (footnote 3 notes the attribution pipeline has gaps)
- Whether the *"April 2026 800 fixes / 1000× error reduction"* campaign relates to the [[anthropic-how-we-contain-claude-2026-05-31|containment publication]] data or is a separate incident
- Anton Korinek's specific contribution scope (feedback only? data-side? methodology?)
- Marina Favaro's background and prior wiki-relevant work (new entity page covers what's surfaceable from the publication)
- Whether the *"automated W2S researcher"* April 2026 publication contains operational data Anthropic Institute publication compresses
- Whether *"Holden Karnofsky"* listed as feedback contributor is the Open Philanthropy / Cosmos-AI Holden Karnofsky (most likely; entity-page-candidate flagged)
- Specific Anthropic Institute research-agenda publication (referenced as `https://www.anthropic.com/research/anthropic-institute-agenda` — primary not fetched)
- Whether the verifiable-slowdown infrastructure publication referenced as the next deliverable has a target ship date
- Specific Glasswing 10K-vuln-first-weeks methodology (which target systems? what severity threshold? false-positive rate?)
