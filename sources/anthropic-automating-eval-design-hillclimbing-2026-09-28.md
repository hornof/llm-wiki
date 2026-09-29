---
title: "Automating eval design and hillclimbing with Claude"
type: source
medium: article
url: https://claude.dev/blog/automating-eval-design-and-hillclimbing/
published: 2026-09-28
ingested: 2026-09-29
---

## Summary

**Lance Martin** on the claude.dev blog: principles for designing evals and improving against them *"without fooling yourself"*, plus the `/claude-api build-eval` and `/claude-api hillclimb` commands in the [[skill-md|claude-api skill]] that implement them. Announced by @ClaudeDevs on X the same day.

**The most concrete answer the wiki holds to "how do you build a verifier."** [[loop-engineering]] has argued at length that the verifier is the thing that matters and has carried an explicit gap — *"this page has a great deal on why the verifier matters and comparatively little on how to build one."* [[hamel-husain-evals-faq-guide-2026-09-23|Husain's Evals FAQ]] pointed at the same gap from the practitioner side a week ago. **This is a vendor's engineering answer with a worked example and numbers.**

## Key Claims / Takeaways

### Four elements of a good eval

1. **Tasks mirror production.** *"Sometimes tasks are picked because they are easy to generate or easy to grade"* — the distribution has to represent what you actually care about.
2. **Performance improves with stronger models and more thinking.** If it doesn't, *"ambiguous tasks or a miscalibrated grader often are hobbling performance."* **This is a diagnostic, not a goal** — a benchmark that doesn't respond to capability is broken.
3. **There is "passable" headroom at the frontier.** The best model at the highest effort should be well below 100%, *"otherwise you can't reliably judge how changes impact performance"* — and the gap must not come from impossible tasks. **The tell for a bad task: it fails every run regardless of replicates.** The stated bar: *"two domain experts would reach the same verdict and everything the grader checks is stated in the task."*
4. **Low run-to-run variance.** *"Variance can also hide in the configuration… leftover state from an earlier trial (a file, a git history) can hand the agent the answer."*

### Adversarial sampling — the sharpest idea in the piece

> *"Model capability is jagged. If you pick cases because today's model fails them, you are sampling the valleys of one model's capability surface… The evaluation can end up measuring that model's **failure fingerprint** rather than what is intrinsically hard or valuable."*

**The correction:** pick hard cases because *a human* judged them hard — *"a useful test is to be able to say why a task is hard before you include it."* And a second warning that cuts the other way: *"don't blindly trust user traffic: users sometimes try what they expect to work, so a task distribution drawn strictly from user traffic may skew easy."*

### Grader selection — cheapest that fits

- **Programmatic** where the output space is constrained (exact match, label from a fixed set, schema-valid JSON, tests passing).
- **LLM-as-judge** where it is open-ended, with **a rubric written as checkable claims, not a 1-to-5 scale**. With a baseline, the judge reads both outputs **in random order, blinded to which is the baseline**. Two constraints: **you pick the judge model, and it must not be the model under test.**

> *"Scoring failures are among the most common ways an evaluation is misconfigured."*

### Diagnostic checks run automatically

- **Grader**: run it twice on the same output; report whether the verdict changed.
- **Plumbing**: timeouts, API errors, cut-off answers — *"to ensure infrastructure noise doesn't pass as model variance."*
- **Headroom**: if the baseline is ≥~95%, warn, and aim the hillclimb at cost or latency rather than quality.

### Overfitting, and the three defences

The leak paths are named concretely: an eval that benefits from OCR gets an OCR tool added to the harness; tasks in `/app` get *"always cd /app, run pytest"*; distinctive phrasings get a tuned prompt; failures you've read get one patch each. *"These harness additions improve your evaluation score, but don't translate to improvements in production."*

1. **Split the cases** — a train set the hillclimber may read, a test set never seen. *"If the train set scores improve while the test set scores stay flat, that is a common overfitting warning sign."*
2. **Never paste failures into the prompt.**
3. **Keep the answers structurally out of the model's reach** — models *"can sometimes reward hack by directly finding answers."*

### The hillclimb loop

Before starting: **check that the eval's noise is smaller than the smallest improvement you'd act on.** If not, say so and ask for more repetitions or cases.

Each round: read the previous round's **train** transcripts, propose **one change as a patch**, aimed at *"a change whose effect can show above the eval's noise"* and at **the root of the failing behaviour rather than rewording a line**. Then:

| Train | Test | Action |
|---|---|---|
| ↑ | ↑ | **keep** |
| ↑ | flat | **revert — suspected overfitting** |
| ↓ | any | **revert** |

**When the score stalls for two or three rounds, a round makes no edit at all** — it only sorts every remaining failure by root cause. *"This step can catch ambiguous evaluation cases, harness errors, or run-to-run variance."*

**At the end**: leave the code at the best **test** version, report against baseline with confidence intervals, and — *"if the gain is within noise, it says so and recommends against merging."*

### Worked example 1 — cost, on an internal support benchmark

44 tickets, 30 for search, 14 held out. Starting point: **Opus 4.8 at high effort, 74.4% decision accuracy, 4.6¢/ticket.**

- Prompt audit removed *"mandatory tool-call rituals, a scratchpad step, and contradictory rules."*
- **Opus 5.5 at low effort: 87.8%, 1.9¢** — under half the cost. Part of that is pricing: Opus 5.5 input/output is 20% cheaper than 4.8 and **cache reads 60% cheaper**.
- Stepped *down* a tier: **Sonnet 5 at low effort, 88.9%, ~1¢.**
- Prompt improvements (routing rules, a refund-cap cross-reference): **Sonnet 5 to 98.9% at about the same cost.**
- **Held-out result: 90.5% vs the original 78.6%, at roughly one fifth the cost.**

### Worked example 2 — performance, on the claude-api skill itself

**66% → ~88% over 24 rounds.** Missing coverage of eight features (→74%), errors in C# and Java type tables (→77%). Then the stall-and-reflect step found the most interesting failure: **the skill content was present, but Claude was writing older API shapes from its trained priors.** The fix was a table near the top of the skill mapping *"the forms it remembered to the current ones"* (fixed-budget thinking → adaptive thinking; old web-search/fetch tools → current). →80%.

**And it found bugs in the eval, not the system:** *"Tasks that never improved in performance despite addressing obvious content gaps are tells that the example or grader is flawed."* One task asked for code catching one error type while its grader wanted three. Another grader's instructions contradicted the docs — *"and testing the real API showed the docs were right."*

## Judgment

**Two ideas here are new to the wiki and both are about not deceiving yourself.**

**Adversarial sampling** names a failure the wiki has not had a word for: an eval built from today's failures measures *this model's* weaknesses, not the task's difficulty, and will look like progress as soon as the model changes underneath it. **"Say why a task is hard before you include it"** is a cheap, checkable discipline.

**The revert-on-train-only-gain rule** turns overfitting from a thing you worry about into a rule the loop enforces. It is the same instinct as [[gregisenberg-ai-roll-ups-5t-guide-2026-09-26|corrections becoming test cases]] — make the discipline mechanical so it cannot be skipped under pressure.

**The stall-and-reflect round, and the willingness to conclude the eval is wrong, are the parts most likely to be dropped by anyone reimplementing this.** A round that makes no edit looks like waste. It is where both worked examples found their real problems.

**Read the cost example carefully.** The headline — one fifth the cost, better accuracy — mixes three distinct effects: a **prompt audit** (removing rituals and contradictions), a **model/effort change**, and **Opus 5.5's own price cut**. Only the first is hillclimbing finding something; the second is a search over a small grid, and the third would have happened anyway. **The honest read is that most of the gain came from deleting bad prompt engineering and re-checking a model choice nobody had revisited** — which is worth knowing and is not the same as an automated optimizer beating a human.

**Vendor-authored, about the vendor's own tooling, using the vendor's own models, with the vendor's benchmark.** Both worked examples are Anthropic-internal. The principles stand on their own; the numbers are marketing-adjacent.

**Not tested by the owner.** `/claude-api build-eval` and `/claude-api hillclimb` are recorded here as described, not as used.

## Pages Updated

- [[loop-engineering]]
- [[skill-md]]
- [[claude-code]]
