---
name: AI Labor Market Impacts
type: concept
maturity: active-research
last_updated: 2026-06-02
---

## Definition

The measurable economic effects of AI / LLM diffusion on employment, hiring, wages, and occupational mix. As of May 2026, the field has converged on a **task-based exposure framework**: occupations are decomposed into tasks; tasks are scored for theoretical LLM capability (typically via Eloundou et al. 2023's β-metric: 1 = LLM alone can double speed, 0.5 = LLM + tools, 0 = not feasible); occupation-level exposure is the time-weighted average of task exposure. The cutting-edge refinement (Anthropic, March 2026) is **observed exposure** — adjusting theoretical capability by *actual usage* from Claude's first-party telemetry, weighted toward automated (rather than augmentative) and work-related (rather than personal) usage patterns.

## Why It Matters

For an AI engineering / VPE career:

- **Computer Programmers are the single most-exposed occupation** (75% observed exposure in Anthropic's measure; [[anthropic-labor-market-impacts-2026-03-05]]). The wiki owner's own profession is at the top of the list. This is the direct context for every "what does AI mean for my career" conversation.
- **The young-worker hiring signal is the actionable finding**: 22-25-year-olds entering exposed occupations have seen a ~14% drop in monthly job-finding rate post-ChatGPT (Anthropic); 6-16% fall in employment in the same demographic from ADP payroll data (Brynjolfsson, Chandar, Chen 2025 "Canaries in the Coal Mine"). Two independent datasets, same direction. Affects how to think about entry-level hiring pipelines, new-grad onboarding, and senior-leverage vs. junior-pipeline staffing patterns.
- **Aggregate unemployment effects are not detectable yet**: no statistically significant differential unemployment increase for top-quartile-exposure workers vs. zero-exposure workers since late 2022. The narrative outpaces the data. Useful counterweight to noisier sources.

## Current State

### The exposure-measurement framework

| Component | What it measures | Primary source |
|---|---|---|
| **β (theoretical capability)** | Can an LLM at least double the speed of a task? | Eloundou, Manning, Mishkin, Rock (2023, arXiv:2303.10130) |
| **O*NET task decomposition** | What tasks does each of ~800 occupations actually do? | US Department of Labor O*NET database |
| **Observed exposure** | β × actual usage × automated-weight × work-context-weight × task-time-fraction | Massenkoff & McCrory (Anthropic, March 2026): [[anthropic-labor-market-impacts-2026-03-05]] |

### Headline empirical findings (May 2026)

- **No systematic unemployment increase** for highly-exposed workers since late 2022 (Anthropic CPS-matched data). Confidence intervals would detect a ~1pp differential change.
- **Tentative young-worker hiring slowdown** in exposed occupations: ~14% relative decline in monthly job-finding rate for 22-25-year-olds (Anthropic), 6-16% employment fall in the same demographic (Brynjolfsson et al.). Two independent datasets converge.
- **Higher-exposure occupations have weaker BLS 2024-2034 growth projections**: every 10pp increase in coverage → 0.6pp lower projected employment growth (weighted regression). **No correlation using theoretical β alone** — the usage-data adjustment is what makes the framework predictive.
- **Worker characteristics** in top-quartile-exposure occupations (vs. zero-exposure): older, more female, more white / Asian, 47% higher earnings, ~4× more likely to have a graduate degree.

### Top-exposed occupations (Anthropic March 2026)

1. **Computer Programmers — 75% coverage**
2. **Customer Service Representatives** — main tasks "increasingly seen in first-party API traffic"
3. **Data Entry Keyers — 67% coverage**

### Zero-exposure occupations

**30% of workers** have zero coverage in the Anthropic measure. Examples: Cooks, Motorcycle Mechanics, Lifeguards, Bartenders, Dishwashers, Dressing Room Attendants. The "AI is coming for all jobs" framing is not what the data supports.

### Methodological caveats

- Authors of [[anthropic-labor-market-impacts-2026-03-05]] are explicit about prior approaches having weak track records (Blinder's offshorability metric flagged ~25% of US jobs as vulnerable; most of those occupations still grew). Framework is designed to be re-run as data emerges, not to make point predictions.
- **The young-worker finding is "just barely statistically significant"** in the Anthropic measure. Alternative interpretations: young workers staying in existing jobs, taking different jobs, returning to school. Survey mismeasurement also possible.
- The Brynjolfsson et al. ADP-payroll cross-confirmation is what elevates the signal above noise — same direction, different data.
- The Anthropic measure is anchored on Claude usage. Doesn't include OpenAI / Gemini usage, which would shift the exposure weights. Cross-lab usage-data fusion is the obvious next step.

## Adjacent / Counterposed Frameworks

- **β alone** (Eloundou et al. 2023) — theoretical capability without usage adjustment. Found *no* correlation with BLS projections.
- **O-Ring automation** (Gans & Goldfarb 2025) — argues employment effects appear only when *all* tasks have some AI penetration.
- **Concentration of exposure** (Hampole et al. 2025) — concentration of AI exposure in specific tasks can counteract mean-exposure displacement effects.
- **Expertise framing** (Autor & Thompson 2025) — focuses on the expertise level required for the *remaining* unautomated tasks.

The Anthropic measure is the first to use first-party-lab usage telemetry as the empirical anchor. Other labs (OpenAI, Google) have not yet published comparable usage-anchored exposure measures — would be a structural move if/when they do.

## Timeline-Calibration Hexangle (June 2026)

Six dated agentic-replacement / AI-capability-trajectory timeline claims captured in the wiki:

| Source | Prediction | Date stamp |
|---|---|---|
| **Elad Gil** (via [[eladgil-rsi-december-breakpoint-2026-05-31]]) | **RSI execution running in 6-24 months from May 2026** (Nov 2026 – May 2028) — Gil's refined position when challenged on the RSI-tools-exist vs RSI-running distinction | May 31 2026 |
| Anton Korinek (Anthropic) — [[import-ai-456-clark-rsi-radical-optionality-2026-05-11]] | **~6 years to explosive growth regime** under full software R&D automation + 5% economy-wide automation shock | May 11 2026 |
| MIT FutureTech (via [[techcrunch-bort-ceo-ai-psychosis-2026-05-27|TechCrunch / Bort]]) | **80–95% success on most text-tasks at "minimally sufficient quality" by 2029** (current LLM-improvement rate) | May 27 2026 |
| [[kris-lovejoy]] / Kyndryl (via [[eye-on-ai-lovejoy-agentic-enterprise-2026-05-15|Eye on A.I.]]) | **Half of traditional IT-admin tasks handled by AI agents by 2031** | May 15 2026 |
| [[andrej-karpathy]] (via [[zephyr-karpathy-10-year-agent-window-2026-05-14|Zephyr amplification]]) | **~10 years for agents to fully replace workers** | May 14 2026 |
| **Sam Altman** (via [[altman-three-observations-2025-02]], re-surfaced June 1 2026) | ***Anyone in 2035 should be able to marshall the intellectual capacity equivalent to everyone in 2025*** — **2035** as the *everyone-2025-intellectual-capacity-equivalent* horizon | Feb 2025 (re-surfaced 2026-06-01) |

The hexangle spans **Gil's 1-2 years to Karpathy's / Altman's ~10 years**. Useful as a calibration anchor for new timeline claims: any aggressive claim that doesn't engage with these six needs to either supersede them or be filed as hype. Any cautious claim needs to engage with Gil's lower bound (now superseded Korinek's prior lower bound).

**Altman 2035 is the most ambitious quantitative claim**: not "agents replace workers" (Karpathy) but the stronger "any *one* person commands the intellectual capacity of *all* of 2025." Pairs with Altman's [[altman-three-observations-2025-02|Three Observations]] super-exponential socioeconomic-value claim as the structural argument for the claim's plausibility.

**Gil's distinction is methodologically important**: Gil concedes (under challenge from @careerlevelup) that *"AI accelerating human-directed development"* — the past 6 months — is **not** the same as RSI itself. The 6-24-month window is for *RSI execution running*, not *RSI-tools-existing*. **First wiki-captured frontier-investor live position-refinement on RSI definition.**

**MIT framing's key qualifier**: *"minimally sufficient quality level"* — the floor of acceptability, not human-parity. *"Agents reach the floor of acceptability"* is a much weaker claim than *"agents replace workers"*; the qualifier is what keeps MIT's 2029 datum compatible with the longer-horizon claims above.

**Counter-prediction from Lovejoy (worth holding alongside)**: the *replacement profile* may not map to current programmer roles. *"Not coders, but people trained to ask the right questions"* will thrive. If correct, the [[anthropic-labor-market-impacts-2026-03-05|Computer Programmers 75% covered]] finding measures *displacement of current programmers* rather than displacement of *the work programming does* — those are different things, and the existing framework conflates them.

**Empirical anchor needed**: [[zephyr-karpathy-10-year-agent-window-2026-05-14]] surfaces Gerard Sans's citation of **Ríos-García et al. (arXiv:2604.18805)** — 25,000+ verifier experiments showing 68% of agent traces ignored gathered evidence, 71% had zero belief updates, 26% revised. If verified, this is a foundational failure rate (agents don't update from evidence) that has to close for any of the above timelines to be plausible. Worth elevating to a dedicated source if a primary surfaces.

## Cultural-Sentiment Companion (Deedy Das, May 2026)

The structural framework above measures the labor-market signal in employment, exposure, and timeline data. [[deedydas-sf-ai-wealth-divide-2026-05-15]] adds **the lived-experience cultural texture** that the data-side papers don't try to measure: a first-person SF essay naming four converging effects of the AI-capital concentration:

1. **"The corporate ladder looks like the wrong building to climb."** — Career re-alignment toward founder / frontier-lab / equity-bet; broad job-switching demand for higher salaries.
2. **"There's a deep malaise about work (and its future)."** — *"Why even work at all for peanuts? Will my job even exist in a few years?"* "Permanent underclass" conversation rising especially among young people.
3. **Middle-manager paralysis** — *"They don't particularly have any AI skills. They see the writing on the wall: middle management is being hollowed out."* This is **the same population** that [[benln-dorsey-mini-agi-2026-05-13|FundamentalAnalysis named as 'first to atrophy']] in the org-chart-flattening framing; Deedy's first-person texture and the structural argument converge from opposite starting points.
4. **Post-economic-founder lack-of-purpose** — *"And do what? Right now, everyone wants to talk to me. If I sell, I will only have money."*

**Vibecoding-as-escape-hatch framing**: *"A frequent side effect of this torment is to spin up the very products making everyone rich in hopes that you too can vibecode your path to economic enlightenment."* — Names the cultural logic by which AI-anxiety becomes AI-adoption. Same shape as the [[fastcompany-amazon-workers-ai-task-faking-2026-05|Goodhart-Law gaming]] under corporate AI mandates, different driver (cultural vs corporate).

**Counter-take worth tracking** (Hot Aisle): *"None of this is new."* Historical cycles (dot-com, mobile, crypto) produced similar discontinuous-outcome distributions. Whether AI is structurally different or just the same shape at larger scale is an open question this essay does not settle.

Treat as cultural-sentiment data point, not measurement: specific numbers ($20M retirement wealth threshold, ~10k people) are Deedy's estimates; framing is SF-centric.

## Open Questions

- **Will the young-worker signal hold up?** Currently "just barely statistically significant" in one measure, 6-16% in another. Re-runs over the next 6-12 months are the verification.
- **Where does junior hiring go instead?** If 22-25-year-olds aren't entering exposed occupations, the labor-force-exit / non-exposed-occupation / returning-to-school split is the actionable distinction.
- **Does the framework predict the *next* wave of exposure?** Computer Programmers at 75% means ~25% of tasks are still uncovered — what are they? Where does the next 10pp come from? The cookbook of "what programmers do that LLMs still can't" becomes the survival manual.
- **Does Anthropic publishing this paper bias its own product roadmap?** The same usage data that anchors the labor-market measure is the data Anthropic uses to prioritize features (cf. [[anthropic-finance-agents-2026-05-05]] — KYC screener / statement auditor are the Customer-Service-Rep-adjacent automation surfaces). Feedback loop worth tracking.

## Key Papers / Posts

- **[[anthropic-labor-market-impacts-2026-03-05]]** — Massenkoff & McCrory, Anthropic Economic Index, March 2026. Primary source for `observed exposure`. Foundational citation.
- **Brynjolfsson, Chandar, Chen (2025)** — "Canaries in the Coal Mine: six facts about the recent employment effects of artificial intelligence." Independent ADP-payroll data; 6-16% young-worker employment decline in exposed occupations. *Not yet ingested as a separate source; cited in [[anthropic-labor-market-impacts-2026-03-05]].*
- **Eloundou, Manning, Mishkin, Rock (2023)** — "GPTs are GPTs." arXiv:2303.10130. The β-metric origin paper. *Not yet ingested as a separate source.*
- **Handa, Tamkin, McCain et al. (2025)** — "Which Economic Tasks are Performed with AI? Evidence from Millions of Claude Conversations." Anthropic Economic Index foundational paper.
- **[[eye-on-ai-lovejoy-agentic-enterprise-2026-05-15]]** — Kris Lovejoy (Kyndryl) on *Eye on A.I.*; 2031 prediction (50% of IT-admin tasks); "bullet train on 30 mph tracks" enterprise-readiness framing; ITSM-as-entry-point thesis.
- **[[zephyr-karpathy-10-year-agent-window-2026-05-14]]** — Karpathy 10-year-timeline quote surfaced via Zephyr; Gerard Sans citation of Ríos-García et al. (arXiv:2604.18805) on verifier-belief-update failure rates.
- **[[deedydas-sf-ai-wealth-divide-2026-05-15]]** — first-person SF cultural-sentiment companion; four-effect taxonomy; vibecoding-as-escape-hatch framing (May 15 2026).

## C-Suite-Emergence Path: Chief AI Officer (May 2026)

The structural framework above measures the labor-market signal in employment, exposure, and timeline data. [[nateherk-caio-opportunity-2026-05-17]] surfaces an IBM survey of 2,000 CEOs (median $5.8B revenue) that adds **C-suite-role-creation data** to the framework:

- **76% of CEOs surveyed have or are hiring a Chief AI Officer (CAIO) in 2026** — up from 26% in 2024.
- **86% of employees have the skills; only 25% actually use AI at work — 61-point adoption gap.** The bottleneck isn't capability; it's connecting capable employees to the workflows that need it.
- **57% of CAIOs were promoted from inside** (per a separate IBM 600-CAIO study). The role goes to existing AI-fluent employees, not external hires.
- **85% of CEOs say every functional leader (CMO, CFO, COO, head of sales) has to become AI-fluent**; **77% say talent leadership and tech leadership are converging into one job**.
- **40% of CAIOs report to CEO, 24% to CIO**, rest scattered across CTO/COO — *"nobody can agree on what this role 100% is"* — first-definers win.

### The CISO analogy (compressed timeline)

- CISO role didn't exist in 1980; took ~15 years to become universal at major companies after the internet matured. CAIO emergence took **24 months** to go from 26% → 76% — same shape, 7× compression.
- *"Internet-marketer-as-disappearing-qualifier"* analogy: once AI saturates every function, "AI consultant" → "consultant"; the qualifier disappears. IBM-cited framing: *"Today, AI augments people. By 2030, people will augment AI."*

### Two career paths into the seat

- **Path A (External)**: AI consultant / agency → pulled in-house by client → CAIO.
- **Path B (Internal)**: already employed → become the most AI-fluent person in the building → promoted into the seat. **57% of current CAIOs took Path B.**

### CEO predictions get marked-to-market badly

- In 2024, half of these CEOs predicted AI would be primarily driving growth by 2026; today only 10% say it actually is. **CEOs were off by ~40 percentage points in one year on their own AI growth-driver prediction.** Worth holding alongside the 76%-CAIO-adoption datum — both come from the same survey, only one is a forward prediction the other is a present-tense headcount commitment.

### Caveats

- Survey is large publicly traded companies, $5.8B median revenue — not globally representative. nateherk himself: *"Globally I'd be shocked if it's over 30%."*
- Path-allocation between A and B (57% inside vs 43% outside) is the strongest single argument against the dominant content-creator narrative that consulting/agency is the only AI-native career path.

## Practitioner-Content Register: Hassid + Kearns Cost-Collapse Cluster (May 2026)

Three same-week practitioner-content-register surfaces converging on the **development-as-defensible-skill collapse** thesis from different angles:

- **[[hassid-cant-beat-ai-cost-collapse-2026-05-18|Ruben Hassid (2026-05-18)]]**: *"AI gets 5× cheaper every single year. Do you?"* + *"In 4 years AI is 6,000× cheaper."* Three-hidden-costs framework: AI attacks know-enough + think-enough + produce-enough. *"Cheap tools don't need to be perfect. They need to be good enough for people to use them 100 times more."* **Junior-jobs-crashing directly named** — *"the market decided. It's better to use AI than juniors. And you can't say it out loud."*
- **[[herk-kearns-100m-ai-agency-playbook-2026-05-25|Devin Kearns / Custom AI Studio (2026-05-25)]]**: *"The value of actually doing development is trending towards zero. It's like very very stark and very very clear that it's happening."* + *"Most AI work being sold today won't survive 2027."* Agency-side framing of the same call: most operators are unconsciously building lifestyle businesses on the doing-development layer that's collapsing.
- **[[lennysan-shipper-10-takeaways-2026-05-24|Dan Shipper takeaway 7 (2026-05-24)]]**: *"AI job apocalypse not happening, but you need to evolve. Models make yesterday's human competence cheap. The key: 'ride the models.'"* Pairs the cost-collapse thesis with a non-doom guidance: substitute up-the-stack toward judgment + integration rather than execution.

**Three independent surfaces, same week, converging on the same structural call.** Different prescriptions (Hassid: subscribe to my newsletter; Kearns: build enterprise-value AI agency; Shipper: ride the models). Same diagnosis.

## AI-ROI-Gap Counter-Anchor (May 2026)

The [[ai-roi-gap]] thesis crystallized 2026-05-23 → 2026-05-27 across three independent practitioner surfaces and one mainstream-press synthesis. The relevant labor-market-impact additions:

### Layoffs.fyi 2026-vs-2025 numbers ([[techcrunch-bort-ceo-ai-psychosis-2026-05-27|TechCrunch / Bort, 2026-05-27]])

- **115,430 tech employees fired across 152 companies in first 5 months of 2026** — nearly matching all of 2025 (124,636 across 275 companies).
- 2026 on pace for ~2× the 2025 layoff total at the current rate.
- **Concentration shift**: 152 vs 275 companies = fewer-but-larger cuts in 2026 (avg cut/company ~760 in 2026 vs ~453 in 2025).
- **Macro counterweight to the Anthropic Economic Index *no-detectable-unemployment-differential-yet* finding**. The disagreement isn't about the data: Anthropic measures *occupation-level CPS-matched unemployment differentials*; layoffs.fyi measures *firm-attributed-AI-or-AI-adjacent reductions*. Both can be simultaneously true (no statistically significant CPS differential *and* a doubling of AI-attributed firm-level cuts) because the layoff-attribution channel and the unemployment-rate channel measure different things.

### AI-washing skepticism layer

- TechCrunch's framing: when public companies attribute layoffs to AI, it could be (a) actual displacement, (b) rhetorical cover for macro cost-cutting, or (c) AI-premium stock-positioning. These are not mutually exclusive.
- See [[ai-roi-gap#The "AI Washing" Question (Layoff-Attribution Skepticism)|the AI-ROI-Gap "AI Washing" Question]] for the tracking-signal framework.
- **Implication for the labor-market exposure framework**: the Anthropic Economic Index's *observed exposure* measure (β × actual usage) is robust to AI-washing because it doesn't depend on firm-attribution narratives. This is a methodological strength of the framework relative to layoff-tracker data.

### Berkeley meta-analysis: "no robust relationship" (October 2025)

- **UC Berkeley California Management Review**: meta-analysis of AI-and-productivity research finds *"no robust relationship between AI adoption and aggregate productivity gain."* ([cmr.berkeley.edu](https://cmr.berkeley.edu/2025/10/seven-myths-about-ai-and-productivity-what-the-evidence-really-says/), per TechCrunch citation).
- **Why it matters for labor-market impacts**: if aggregate productivity gains are not robustly measurable, the *mechanism* by which AI exposure produces labor-market displacement (productivity gain → headcount reduction at constant output) is weakened. The exposure framework still works for tracking *which occupations are theoretically vulnerable*; the open question becomes *under what conditions vulnerability translates to displacement*.
- **Not yet ingested as a separate source.** Worth primary-fetch.

### NBER w34984: the productivity paradox (March 2026)

- **NBER (March 2026)**: AI adoption *does* improve productivity — but *"a productivity paradox, in which perceived productivity gains are larger than measured productivity gains."*
- **Pairs with the [[anthropic-labor-market-impacts-2026-03-05|Anthropic Economic Index]] perception-vs-measurement gap**: the Anthropic measure anchors on usage telemetry (β × actual usage), which is closer to *measured* than *perceived* productivity. The NBER paradox is the macro-econometric mirror of why the Anthropic measure outperforms naive β-only frameworks.
- **Not yet ingested as a separate source.** Worth primary-fetch as a foundational citation alongside Eloundou and Brynjolfsson.

### MIT FutureTech 80-95%-by-2029 anchor

- See the [[ai-labor-market-impacts#Timeline-Calibration Quadrangle (May 2026)|Timeline-Calibration Quadrangle]] above — MIT FutureTech becomes the 4th corner.
- **Key reframe**: MIT's framing is *"agents reach the floor of acceptability,"* not *"agents replace workers."* This is the empirical foundation for the [[ai-roi-gap]] thesis that capability-of-the-model and value-shipped-in-production are different curves — the model crossing the *"minimally sufficient quality"* line doesn't mean the deployment-to-shipped-value funnel closes.

### HBR: bottleneck shifts to executive authorization (May 2026)

- **Harvard Business Review (May 2026)**: when everyone uses AI to produce more output, *"the bottleneck simply shifts to executives. Their work awaits the people that must authorize all the stuff everyone is producing."*
- **Structurally important for labor-market impacts**: the AI-productivity story isn't *just* about throughput — it's about which roles become bottlenecks. The *executive-authorization bottleneck* could shift labor-market value *toward* roles that have authority-and-judgment (middle-manager-to-executive transition surface) and *away* from roles that have output-production capacity. **Pairs structurally** with the [[ai-labor-market-impacts#C-Suite-Emergence Path: Chief AI Officer (May 2026)|CAIO emergence path]] and the *"by 2030, people will augment AI"* IBM framing.

### CEO-distance-from-last-mile mechanism ([[levie-ceo-ai-psychosis-2026-05-23|Levie, 2026-05-23]])

- *"CEOs are uniquely prone to AI psychosis because they're sufficiently distant from the last mile of work that still has to happen to generate most value with AI."*
- **Cultural-sentiment companion** to the structural Anthropic-Economic-Index data. The mechanism Levie names is *why* the executive-prediction-vs-reality gap shows up in CEO survey data ([[ai-labor-market-impacts#CEO predictions get marked-to-market badly|CEOs off by ~40 percentage points in one year on their own AI growth-driver prediction]]). Same gap, named from two different angles.

### 4-stage hype-cycle psychological-investment ratchet ([[cyb3rops-four-stages-ai-coding-hype-2026-05-26|cyb3rops, 2026-05-26]])

- **The mechanism by which the [[ai-roi-gap]] persists despite measurement**: stages 1-2 (Amazement → Expansion) create social/professional commitments that make stage-4 (Realization) admission costly even when data supports it.
- **Implication for labor-market displacement tracking**: layoff-attribution narratives are downstream of the same ratchet. Once a company has invested narratively in *"AI productivity will replace X% of work,"* the layoff announcement that follows is doubly committed (cost + narrative) and harder to walk back even if displacement targets don't materialize.

## Frontier-Lab Labor-Policy Posture (May 2026)

First wiki-captured concrete labor-policy commitment from a frontier-model provider:

- **[[openai|OpenAI]] Foundation $250M workforce-transitions initiative (2026-05-27)**: impact measurement + labor-policy research focused on AI's workforce consequences. [[dailybrief-roundup-2026-05-27|Brief framing]]: *"Public commitment to impact measurement and labor-policy research. Signals OpenAI's posture on AI's economic consequences."*

**Why it matters**: OpenAI is positioning itself on the *policy side* of the same labor-market trend it's accelerating. Pairs with [[saas-disruption-thesis|the ClickUp + Intuit two-in-six-days restructuring signals]] — the trend is real enough that the frontier lab is funding the labor-policy research framework around it. The $250M number is substantial relative to academic labor-economics research budgets; if Foundation grants actually flow to research, it could reshape who produces the canonical labor-impact measurements (currently Anthropic Economic Index + Brynjolfsson Stanford Digital Economy Lab). Worth tracking grant recipients and research outputs.

**Verification-pending**: $250M specifics — committed vs deployed, time horizon, research-priority list, whether Foundation operates independently of OpenAI commercial decisions.

## Economist-Side Modeling Layer (METR / Cunningham vs Greenblatt, May 29 2026)

[[metr-cunningham-agent-diminishing-returns-2026-05-29|Tom Cunningham (METR)]] argues **AI agents face faster diminishing returns to scaling than human labor**; **Ryan Greenblatt** counters that *scalability favors agent spending despite the diminishing returns curve.*

**First wiki-captured economist-side theoretical model for the agent-vs-human-labor cost-curve debate.** Sits above the [[anthropic-labor-market-impacts-2026-03-05|Anthropic Economic Index empirical exposure framework]] as a *theoretical-curve-shape layer* the framework's empirical data will validate or refute over 2026-2027.

**Why it matters for this concept**:
- The [[ai-labor-market-impacts#Headline empirical findings (May 2026)|young-worker hiring slowdown]] (14% drop in monthly job-finding rate for 22-25-year-olds in exposed occupations) can be re-read through Cunningham's curve-shape lens: if agents have steeper diminishing returns than juniors, the substitution-of-juniors-by-agents is bounded by the operational scale at which the curves cross. Greenblatt's parallelism rebuttal implies the crossing happens later (favoring agents longer); Cunningham's framing implies it happens earlier (limiting agent-substitution-by-curve-shape).
- **METR institutional placement matters**: Cunningham working at METR (Model Evaluation and Threat Research — most-cited for the *METR Doubling Law* on agent task-horizon length) places economist-modeling *inside the AI-evaluation-org institutional frame*. Track for whether METR builds out an economics arm — that would be a structural addition to the labor-market-impacts measurement framework.

Pairs with [[ai-roi-gap#Economist-Side Modeling Layer (METR / Cunningham vs Greenblatt, May 29 2026)|the ROI-gap economist-side section]] which captures the parallel debate at the demand-side altitude.

## Related Concepts

- [[agentic-engineering]] — the professional discipline of working with agents at the high-leverage end of the exposure curve.
- [[saas-disruption-thesis]] — the labor-market mirror image is the SaaS-vendor-disruption thesis (the same workflows that displace workers also displace incumbent SaaS).
- [[ai-roi-gap]] — the demand-side / ROI mirror image; labor-market displacement data is one of three empirical anchor surfaces for the gap (token-spend funnel + layoff numbers + productivity research).
- [[ai-native-organizations]] — org-design adaptation to high-exposure environments.
- [[end-of-finetuning]] — capability-side complement; if base models keep absorbing fine-tuning use cases, the coverage curve climbs faster.
