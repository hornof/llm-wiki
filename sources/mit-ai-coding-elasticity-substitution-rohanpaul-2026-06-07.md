---
title: "MIT study — 100K+ devs, 3 generations of AI tools, 0.25 elasticity of substitution (via @rohanpaul_ai + FT, 2026-06-07)"
type: source
medium: twitter-thread
url: https://x.com/rohanpaul_ai/status/2063756891193549168
ingested: 2026-06-08
---

## Summary

**Rohan Paul (@rohanpaul_ai)** surfaces (2026-06-07) a **new MIT study tracking 100,000+ GitHub developers across 3 generations of AI coding tools** (autocomplete → interactive coding agents → autonomous coding agents) — finding that **code volume gains decouple from shipped-product gains**: autonomous AI coding agents raised commits +180% but releases only +30%, with an estimated **"elasticity of substitution" of 0.25** between AI capability and human labor replaceable. Companion @rohanpaul_ai surface same day: **FT piece "AI is raising software supply faster than demand."** **First wiki-captured concrete empirical 0.25-elasticity-of-substitution figure for AI-coding-tools → human-engineering-labor**. **First wiki-captured concrete 100K+ developer N-sized 3-generation AI-tool natural experiment**. Anchors the **AI-ROI-gap topic at a quantitative empirical academic-research layer** (where prior surfaces were practitioner-content). Chen Avnery comment (2026-06-08): *"That 0.25 elasticity is the verification tax in one number"* — **first wiki-captured "verification tax" canonical naming** for the AI-output-shipping-gap.

## Key Claims / Takeaways

### The headline finding

> *"New MIT study. Code volume surges by 300%, but output increases by only 30%: The AI dividend meets an awkward reality. Autonomous AI coding agents raised commits by 180%, but releases rose only 30%."*

**Pattern**: 6× code-volume gain ↔ 30% shipped-output gain. The AI dividend is **front-loaded into the generate-code step** and absorbed by downstream review / integration / packaging / ship-step costs.

### The MIT methodology — 100K+ devs, 3 generations

> *"The authors compare more than 100,000 GitHub developers before and after they start using 3 generations of AI coding tools, from autocomplete to more independent coding agents."*

**3-generation AI-tool natural-experiment design** (first wiki capture):

| Generation | Commit gain |
|---|---|
| **Autocomplete** | +40% commits |
| **Interactive coding agents** | +140% commits |
| **Autonomous coding agents** | +180% commits |

**Pattern**: commit-volume gains compound across generations (+40 → +140 → +180%), but only proportional to **2× generational scale-up**, suggesting **diminishing-returns curve already evident** by the autonomous-agent generation.

### The shipped-output funnel

> *"The 180% commit gain shrank to 50% for the number of projects and 30% for actual releases."*

**First wiki-captured 3-stage commit → projects → releases funnel collapse**:

| Funnel stage | Gain |
|---|---|
| **Commits** | +180% |
| **Projects** | +50% |
| **Releases** | +30% |

**Pattern**: each downstream stage retains ~⅓ of the prior gain. The compound retention rate is ~17% (commits → releases). The verification / integration / packaging / shipping bottleneck absorbs 83% of the AI-generated commit-volume.

### Elasticity of substitution = 0.25

> *"The estimated 'elasticity of substitution' is 0.25 i.e. for every big improvement in AI's usefulness, only a small amount of human work can be replaced. Because AI can write code faster, but humans are still needed to decide what to build, check if the code works, connect it with the rest of the product, fix messy edge cases, and actually ship it."*

**First wiki-captured concrete 0.25 elasticity-of-substitution figure** for AI-coding-tools → human-engineering-labor. Critical empirical anchor for the [[topics/ai-roi-gap|AI ROI gap topic]] and the [[concepts/verifiability-and-jagged-intelligence|verifiability concept]]. **Operationalizes the qualitative practitioner-content framings** ([[sankar-token-spend-roi-gap-2026-05-25|Sankar token-spend funnel]] + [[levie-ceo-ai-psychosis-2026-05-23|Levie CEO AI psychosis]] + [[cyb3rops-four-stages-ai-coding-hype-2026-05-26|cyb3rops 4-stages]] + [[techcrunch-bort-ceo-ai-psychosis-2026-05-27|TechCrunch / Bort]]) as a **quantitative academic-research-grade figure**.

### Marketplace evidence — app supply rises, usage doesn't

> *"The authors also check app marketplaces and find more new apps, but no increase in total usage, which means more software appeared without clear evidence that users adopted more software. The marketplace evidence points the same way: more new apps appeared, but total usage did not rise."*

**First wiki-captured marketplace-side evidence of AI-supply / consumer-demand decoupling**. Pairs structurally with [[ai-roi-gap|AI-ROI-gap]] supply-vs-demand framing. **Pattern**: AI-output-volume gains are not absorbed by demand-side expansion — apps generated, not used. Anchors the *"AI is raising software supply faster than demand"* FT-piece framing.

### FT companion piece (2026-06-07)

> *"FT publisehd a piece. AI is raising software supply faster than demand."*
> *"AI is producing far more work inside companies, but the new evidence says much of that extra motion is getting lost before it becomes shipped product or customer demand."*

**First wiki-captured FT mainstream-press synthesis** of the AI-supply-vs-demand framing. Pairs with [[techcrunch-bort-ceo-ai-psychosis-2026-05-27|TechCrunch / Bort]] as **2-surface mainstream-press AI-ROI-gap synthesis cluster** (TechCrunch May 27 + FT June 7). URL: `ft.com/content/8e9ae7a4-7209-4e2c-aa36-f3af77d6ce1f`.

### Chen Avnery — "verification tax in one number"

Comment by Chen Avnery (@MindTheGapMTG) — 2026-06-08:

> *"That 0.25 elasticity is the verification tax in one number. Writing code got cheap; proving it's correct, connected, and safe to ship didn't. The bottleneck was never generation — it's the review step humans still own. Faster commits pile up against the same gate."*

**First wiki-captured "verification tax" canonical naming** for the AI-output-shipping-gap. Pairs structurally with:

- [[concepts/verifiability-and-jagged-intelligence|Karpathy's verifiability framing]]: verifiability is the AGI gap; verification-tax is its operationalization at the AI-coding-output layer
- [[mvanhorn-wtf-is-a-loop-2026-06-07|Van Horn's "the loop is not the magic; the feedback inside it is"]]: the loop has to encode verification; otherwise the verification-tax dominates
- [[steipete-loops-engineering-vision-md-2026-06-07|Steinberger Mo "loop with something that can say no"]]: the *"can say no"* primitive IS the verification step humans own
- [[trq-dynamic-workflows-harness-2026-06-02|Thariq's "self-preferential bias" failure mode]] + [[bcherny-5-tips-opus-autonomous-2026-06-05|Cherny tip 5 "self-verify end to end"]]: both Anthropic-internal voices frame self-verification as the load-bearing primitive — Avnery names the cost-side as a tax

**Pattern**: *verification tax* is the unifying name for the cost the loop / harness / workflow must absorb to convert AI-generated work into shipped product. Strong candidate for a wiki concept page.

## Cross-cutting framings

- **First wiki-captured concrete 0.25 elasticity-of-substitution figure** for AI-coding-tools → human-engineering-labor — quantitative academic-research-grade anchor for the [[topics/ai-roi-gap|AI-ROI-gap topic]]
- **First wiki-captured 100K+ GitHub developer N-sized 3-generation AI-tool natural experiment** — methodological gold standard for the AI-ROI-gap debate
- **First wiki-captured 3-stage commit → projects → releases funnel collapse** (180% → 50% → 30%)
- **First wiki-captured marketplace-side evidence** of AI-supply / consumer-demand decoupling (more apps, no usage gain)
- **First wiki-captured FT mainstream-press synthesis** of AI-supply-vs-demand framing — pairs with TechCrunch May 27 as 2-surface mainstream-press AI-ROI-gap cluster
- **First wiki-captured "verification tax" canonical naming** (Chen Avnery / @MindTheGapMTG) — unifies the verifiability + loop-feedback + push-back-primitive + Cherny self-verify framings as the cost the workflow must absorb
- **AI-ROI-gap topic ascends from practitioner-content layer to academic-research empirical layer** — prior surfaces ([[sankar-token-spend-roi-gap-2026-05-25|Sankar]] + [[levie-ceo-ai-psychosis-2026-05-23|Levie]] + [[cyb3rops-four-stages-ai-coding-hype-2026-05-26|cyb3rops]] + [[techcrunch-bort-ceo-ai-psychosis-2026-05-27|TechCrunch/Bort]] + [[uber-ai-tool-cap-1500-2026-06-03|Uber $1500/mo cap]]) were practitioner-content + mainstream-press; MIT study + FT + Chen Avnery framing now adds academic-research empirical + verification-tax naming layers
- **Pairs with [[mvanhorn-wtf-is-a-loop-2026-06-07|Van Horn synthesis]] cost-locus framing**: Van Horn's *"the loop, not the model, is now the expensive part"* (cost-locus shift to loop) + Chen Avnery's *"verification tax"* (cost-locus shift to verification step) = **first wiki-captured 2-vector cost-locus-shift framing for AI-coding-economics** in 1 week

## Pages Updated

- [[topics/ai-roi-gap]] — major update: MIT 0.25 elasticity-of-substitution figure + 3-stage funnel-collapse + marketplace supply-demand decoupling + FT-piece mainstream-press synthesis + Chen Avnery "verification tax" canonical naming
- [[concepts/verifiability-and-jagged-intelligence]] — Chen Avnery "verification tax" framing added as operationalization of Karpathy verifiability framing at the AI-coding-output layer
- [[rohan-paul]] — entity-page candidate flagged (first substantive wiki surface; single-source defer); high-signal X aggregator surfacing AI-research findings

## Adjacent sources

- [[0xchromium-claude-cowork-workflows-guide-2026-06-04]] — same-week 0xchromium Cowork workflows guide (Cowork-side practitioner-content companion; Vexo200 "automate outcomes not tasks" counter-take similar to verification-tax framing)
- [[mvanhorn-wtf-is-a-loop-2026-06-07]] — same-week Van Horn Loop Engineering synthesis; cost-locus shift framing paired
- [[bcherny-5-tips-opus-autonomous-2026-06-05]] — Cherny 5-tip recipe; tip 5 "self-verify end to end" is the verification-tax primitive Cherny embeds in the recipe
- [[steipete-loops-engineering-vision-md-2026-06-07]] — Steinberger Loops + Mo "loop with something that can say no" — the push-back primitive that absorbs the verification tax
- [[trq-dynamic-workflows-harness-2026-06-02]] — Thariq's "self-preferential bias" failure mode (verification-tax-by-another-name)
- [[sankar-token-spend-roi-gap-2026-05-25]] — Sankar token-spend funnel (prior practitioner-content AI-ROI-gap surface)
- [[levie-ceo-ai-psychosis-2026-05-23]] — Levie CEO AI psychosis (prior practitioner-content AI-ROI-gap surface)
- [[cyb3rops-four-stages-ai-coding-hype-2026-05-26]] — cyb3rops 4-stages (prior practitioner-content AI-ROI-gap surface)
- [[techcrunch-bort-ceo-ai-psychosis-2026-05-27]] — TechCrunch / Bort mainstream-press AI-ROI-gap surface; pairs with FT-piece here as 2-surface cluster
- [[uber-ai-tool-cap-1500-2026-06-03]] — Uber $1500/mo Claude Code + Cursor cap; load-bearing operational-incumbent AI-ROI-gap signal

## Verification-pending

- **MIT paper primary**: papers.ssrn.com/sol3/papers.cfm?abstract_id=6859839 (not fetched — verify full methodology + authors + sample-period dates + elasticity-of-substitution model specification)
- **FT piece primary**: ft.com/content/8e9ae7a4-7209-4e2c-aa36-f3af77d6ce1f (paywalled; not fetched; verify article author + headline + specific claims beyond *"AI is raising software supply faster than demand"*)
- Rohan Paul full identity / affiliation / X-bio context — entity-page-candidate flagged
- Chen Avnery (@MindTheGapMTG) full identity / affiliation
- Whether MIT study cites elasticity-of-substitution estimation methodology used (CES production function? Cobb-Douglas? other?)
- Specific AI-tools tracked per generation (autocomplete = Copilot? interactive = Cursor/Claude Code? autonomous = Devin/agentic? — paper-specific terminology verification-pending)
- Sample period dates and whether the autonomous-agent generation N is representative or skewed toward early-adopters
- Marketplace evidence specifics — which app marketplaces? what time period? GMV / DAU / usage definition?
- Whether the MIT paper makes specific verifiability / verification-tax framing or whether that's Chen Avnery's secondary framing
