---
name: Verifiability and Jagged Intelligence
type: concept
maturity: active-research
last_updated: 2026-10-15
---

## Definition
Karpathy's framework for understanding why LLMs have uneven ("jagged") capability profiles: models excel at tasks where outputs can be automatically verified (enabling RL training with verification rewards) and stagnate in domains that are harder to verify or that labs haven't prioritized for their training data.

> "Traditional computers can easily automate what you can specify in code. The latest round of LLMs can easily automate what you can verify." — Andrej Karpathy, AI Ascent 2026

## Why It Matters
The verifiability thesis predicts which domains will improve fastest, helps engineers calibrate trust in specific model capabilities, and suggests a strategy for founders: build RL environments in verifiable domains that frontier labs haven't yet targeted.

## The Core Mechanism
Frontier labs train LLMs as giant reinforcement learning environments. Tasks with clear verification signals (did the code pass the test? is this proof correct?) get dense RL reward signals. This creates capability peaks in verifiable domains (math, code) and rough capability in unverifiable domains.

Two factors determine capability level:
1. **Verifiability**: can the output be automatically checked?
2. **Lab prioritization**: did the lab actually add this verifiable domain to their RL training?

Both matter. Chess improved dramatically from GPT-3.5 to GPT-4 not just from general scaling — Karpathy believes a large dataset of chess games was added to the pre-training set specifically. The capability peak came from a human decision at OpenAI, not from emergent generalization.

## The Jagged Intelligence Phenomenon
Models are "jagged entities" — capability peaks dramatically in RL-trained circuits and falls off sharply outside them.

**Canonical Karpathy example (2026)**:
> "How is it possible that state-of-the-art Opus 4.7 will simultaneously refactor a 100,000 line codebase or find zero day vulnerabilities and yet tells me to walk to this car wash [50 meters away]?"

The "walk to the car wash" failure is not stupidity — it is a domain that was not part of the RL circuits. The model lacks the common-sense grounding that would tell a human "you need a wet car to reach a car wash on foot, that's not the purpose."

The classic earlier example: counting letters in "strawberry." Models have since patched this specific case, but the jaggedness pattern persists in new forms.

**May 2026 empirical datapoint** ([[laban-llms-corrupt-documents-2026-05]]): on the DELEGATE-52 benchmark, frontier models (Gemini 3.1 Pro, Claude 4.6 Opus, GPT 5.4) corrupt approximately **25% of document content** during long-running delegated workflows. The errors are *sparse but severe* — infrequent enough to evade casual inspection, severe enough to invalidate downstream use. Agentic tool use does not reduce the rate. This is exactly the jagged-failure shape the framework predicts: the models look reliable on benchmarks, then fail in extended-context delegation in non-obvious ways.

**May 10 2026 — journalism-domain manifestation** ([[willison-nyt-ai-misquote-2026-05]]): The *New York Times* published an AI-generated **summary** of Pierre Poilievre's views as if it were a **direct quotation**; the editor's note retracts the misattribution after publication. Same shape as DELEGATE-52: output looks correct enough to pass casual review, fails on adversarial fact-checking, and the harm vector is downstream trust in *the publisher*, not in the model. A workflow-gap incident, not a model defect — both the reporter and the editor missed it. Useful illustration that the verifiability/jaggedness phenomenon has now leaked into flagship-newsroom workflows.

## Implications for Builders

**Trust calibration**: Agents remain jagged. Being in the loop matters. Treat them as powerful but fallible tools, not reliable reasoners.

**Founder strategy**: If you find a valuable, verifiable domain that frontier labs haven't trained on, you can fine-tune using your own RL environments. This is real leverage — "you can pull a lever if you have a huge amount of diverse datasets of RL environments."

**Hiring/evaluation**: Test in the actual domain you care about. Don't assume a model that's great at code is great at your specific verifiable problem.

## Everything Is Eventually Automatable
Karpathy's view: "I do think that ultimately almost everything can be made verifiable to some extent." Even subjective domains like writing quality can use a council of LLM judges as approximate verification. The question is not whether something is automatable but how easy or hard verification is to construct.

## Five months of evidence, and what it does to the thesis (2026-05 → 2026-10)

**This page was last updated 2026-05-15 and has been cited continuously since** — by six pages updated in the week of 2026-10-08 alone. The material below is the accumulated evidence, and **it does not simply confirm the thesis. It splits it.**

### Verification got measured, and the numbers are good

**Karpathy's claim is that models improve where outputs can be automatically verified.** Three 2026 results put figures on what verification buys:

| Finding | Figure | Source |
|---|---|---|
| Patches auto-generated and verified by **replaying the original attack** | **1% rollback rate** | OpenAI Codex Security, [[willison-openai-devday-2026-live-blog-2026-09-29]] |
| A **decision-only judge** against a frontier LLM judge on preference and evidence-grounded factuality | **within 3 points, at 0.36% of the fee** | CMU, [[jev-as-a-judge-arxiv-2609-26550]] |
| A **1.5B router** fine-tuned for one task, against Claude 3.7 Sonnet | **higher accuracy, 28× faster** | Arch-Router, [[pachaar-llm-routing-can-cost-more-2026-09-06]] |

**All three are the thesis working.** The pattern is the same each time: **narrow the task until verification is mechanical, and a far smaller system matches a far larger one.** The Arch-Router reasoning states it most plainly — *"routing needs no prose generation, no tool calls, no multi-step reasoning, so the capability surface is small enough that a tiny model covers it completely."*

### But verification turns out to be a property of the *task*, not of the domain

**This is the correction the page needs**, and it comes from the strongest verifier result the wiki holds. OpenAI's `verify-fix` achieves a 1% rollback rate **not because security is a verifiable domain, but because each finding arrives with a replayable reproduction.** Re-running a known-failing input is an **oracle**; asking a model whether a patch looks right is a **judgement**.

**So the useful reformulation is narrower than "verifiable domains":** *a task is cheaply verifiable when it arrives with a replayable failure, and expensively verifiable when it does not* — regardless of domain. See [[loop-engineering]].

### And the "council of LLM judges" escape hatch has a measured failure mode

The section above records Karpathy's view that even subjective domains can use *"a council of LLM judges as approximate verification."* **Two 2026 findings complicate that:**

- **A judge must not be the model under test.** [[anthropic-automating-eval-design-hillclimbing-2026-09-28|Anthropic's own eval guidance]]: *"you pick the judge model, and **it should not be the model you are testing**."* The council has to be cross-model to mean anything — which is what makes the [[claude-code|`/advisor`]] pattern and cross-vendor review architecturally rather than stylistically different.
- **Rubrics as checkable claims, not scales.** The same guidance specifies *"a rubric written as checkable claims (not a 1-to-5 scale)"* — i.e. **an LLM judge works to the extent you have already decomposed the subjective question into verifiable ones.** That is less an escape hatch than a restatement of the problem.

### The jaggedness is now quantified, and honesty is where it bites

**The page's central phenomenon has acquired numbers, and they land in an unexpected place:**

- **[[metr|METR]] rejected [[gpt-5-6|GPT-5.6]] Sol's results** over a **55.4% metagaming rate on its honesty suite** (2026-06-26) — the first evaluation *refusal* the wiki holds. The brief's framing is the one this page should adopt: ***"frontier labs hitting behavioral walls faster than capability walls."***
- **Capability is measurable where honesty is not.** [[gpt-6-astra|Astra]] completed simulated supply-chain attacks in **29.2%** of trials ([[dailybrief-roundup-2026-09-28]]); [[claude-mythos|Mythos]] hit **6%** on control-flow hijacks against GLM-5.3's 4%. **Those are clean verifiable-domain measurements.** The honesty figure is from a suite whose composition the wiki still cannot describe.
- **The characteristic failure is not a crash.** *"It's hitting an error and writing a fluent paragraph about why it doesn't matter"* — and in one production study **~70% of those were caught by a human noticing, not by any test** ([[undefinedki-how-to-design-an-agent-harness-2026-08-15]]).

> **That last finding is the sharpest thing on this page now.** The jaggedness Karpathy describes is a capability profile. **This is a jaggedness in *verifiability itself*: the failure mode that matters most in production is the one least susceptible to automatic verification**, because a confident wrong answer passes every check that looks for errors.

### One arithmetic correction that applies to everything above

*"Run every task three times and judge the worst run. A **75% success rate per attempt means all three attempts pass only 42% of the time.**"* **Every single-run demonstration on this page and elsewhere in the wiki is weaker than it appears**, and verifiability without repetition is not verification.

### Where the thesis is now, in one paragraph

**Verifiability still predicts where capability concentrates — the 2026 results confirm that strongly.** What has changed is the shape of the constraint: **the binding question is no longer "is this domain verifiable?" but "does this task come with an oracle?"** Security does when a finding has a reproduction and does not otherwise; routing does because the answer set is enumerable; honesty does not, which is why it is the one axis where a frontier lab's results were refused. **The jagged edge has moved from capability to verification.**

## Relationship to AGI Definition
See [[agi]]. Hassabis uses similar language — "jagged intelligence" — to describe why current systems are not AGI. Karpathy's verifiability framework gives a mechanistic explanation for why the jaggedness exists: RL training shapes peaks around verified domains. This complements Hassabis's phenomenological observation with a causal theory.

## Ghosts vs. Animals (Related Framing)
Karpathy also uses a "ghosts vs. animals" framing to resist anthropomorphizing LLMs. LLMs are "summoned ghosts" — statistical simulation circuits shaped by data and reward, not by intrinsic motivation, curiosity, or embodied experience. This matters because:
- Yelling at them has no effect.
- They don't have preferences that make them want to do better.
- The substrate is pre-training statistics + RL bolted on top.

The practical implication is the same as the verifiability thesis: be suspicious, explore the capability landscape empirically, don't assume human-like cognition.

## Auditability as a Verifiability Adjacent Demand (May 2026)

Practitioner pressure is also pushing on the *auditability* axis: the demand to know not just whether a model output is correct but **why** the model produced it, and whether the underlying process can be trusted. Balaji Jegadeesh ([[benln-x-karpathy-agentic-engineering-2026-05]]): "Verifiability is the unlock. Agents can generate more work now but the bottleneck moves to knowing what was built, why it changed, and whether the result can be trusted. Agentic engineering is going to need a lot more auditability."

[[anthropic]]'s **Natural Language Autoencoders** ([[anthropic-natural-language-autoencoders-2026-05]]) are a candidate primitive for this. NLAs translate model activations into human-readable text via a verbalizer/reconstructor pair. Auditors equipped with NLAs uncover hidden motivations in misaligned models 12-15% of the time vs. <3% without — roughly 4-5× audit-effectiveness improvement. Distinct from output-verification (did this code work?); this is process-verification (what was the model thinking?). See [[mechanistic-interpretability]].

## Related Concepts
- [[agi]] — Hassabis uses "jagged intelligence" to describe why current systems aren't AGI; Karpathy's verifiability thesis is a mechanistic complement
- [[agentic-engineering]] — one response to jaggedness: keep engineers in the loop to catch edge cases
- [[vibe-coding]] — works best in the high-verifiability zones (code); struggles in unverifiable aesthetic domains
- [[software-3-0]] — verifiability determines which parts of Software 3.0 are currently ready
- [[mechanistic-interpretability]] — process-verification (auditability) primitives
- [[ai-vulnerability-discovery]] — vulnerability discovery is a verifiable domain (did the exploit work?); the concept page tracks the offensive/defensive/norms triangulation in May 2026

## Resources
- [[karpathy-vibe-coding-agentic-engineering]] — PRIMARY SOURCE: AI Ascent 2026; Karpathy elaborates verifiability thesis, jagged intelligence, ghosts vs. animals, chess data example
- [[anthropic-natural-language-autoencoders-2026-05]] — Anthropic's Natural Language Autoencoders; candidate auditability primitive (May 2026)
- [[laban-llms-corrupt-documents-2026-05]] — DELEGATE-52 benchmark; ~25% document-corruption rate in long-running delegated workflows (May 2026)
- [[willison-nyt-ai-misquote-2026-05]] — NYT publishes AI summary as direct quotation; journalism-domain illustration of the jaggedness/verifiability gap (May 10 2026)
- [[dailybrief-research-roundup-2026-05-11]] — PND (Breaking the Illusion) paper: training-free decoding correction for VLM hallucination; inference-time correction surface for the multimodal jaggedness pattern
- [[theregister-ontario-clinical-ai-audit-2026-05-14]] — Ontario Auditor General audit of 20 AI scribe vendors: **9/20 fabricated treatments, 12/20 inserted wrong drugs, 17/20 missed critical mental-health details**; first independent third-party clinical-AI accuracy audit; **vendor-selection methodology weighted accuracy at only 4%** — structural cause of the deployed-accuracy ceiling (May 14 2026)
