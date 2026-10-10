---
name: Jev
type: model
provider: TypeSafe AI
status: available
last_updated: 2026-10-10
---

## What It Is

**Jev** is a decision model from **TypeSafe AI**, released out of stealth on **2026-09-15** in early access. It **cannot hold a conversation, write code, or generate a paragraph** — and that is the design. TypeSafe calls it a **System One model**: unstructured state goes in, **typed answers with probabilities** come out.

It exists for the class of call that a generative model handles badly: the thousands of small judgments inside software and agent loops — *is this ticket urgent, which model should handle this request, is this shell command dangerous, does this passage answer the question.* Those go to an LLM today, which produces the answer one token at a time and leaves the application to parse, validate and retry.

> *"Language generation is the wrong interface when code already knows the possible answers."* — [[akshay-pachaar|Akshay Pachaar]], [[jev-typesafe-system-one-model-2026-09-18]]

## How It Works

Input is **state** plus **questions**, each declaring its answer shape up front. Three primitives:

| Primitive | Returns |
|---|---|
| **Choice** | one option from a caller-defined list, with a probability for **every** option |
| **Score** | a position on a caller-defined ordered scale |
| **Noul** | probability that a yes/no statement is true |

The caller's code keeps control — it receives a distribution, not prose, and decides what to do with it. *"There is no paragraph to interpret and no fourth team for the model to invent."*

## Strengths & Weaknesses

**Strengths**
- **Schema-bounded output.** It cannot return an option you did not declare, and cannot emit malformed prose where your code expected a label.
- **Latency and cost** on decision calls — the vendor claims **100×–200×** faster and cheaper than a frontier model. *Vendor figures.* **A demo-grade unit cost now exists**: **1,700 emails sorted for 18 cents** — ~**$0.0001 per decision** — with responses **within 200 ms** ([[isenberg-ryan-vogel-jev-is-here-2026-09-18]], 2026-09-18). That is the same order of magnitude as CMU's independently measured **0.36% of a strong judge's fee**, from a completely different direction.
- **Probabilities rather than assertions**, which is what makes the confidence pattern below possible.

**Weaknesses**
- **"Cannot hallucinate" is true only narrowly.** Pachaar's correction is the version to use: *"Jev cannot break the declared output schema, but it can still be wrong."* **Type safety prevents invalid shapes; it does not guarantee correct judgment** — and a schema-valid mistake can still refund the wrong customer or approve a dangerous command.
- **Calibration is the entire product and is unverified.** Training is named as **RLCD (Reinforcement Learning for Calibrated Decisions)**, with the goal that confidence tracks accuracy. No reliability diagram or held-out calibration data has been captured. **If the confidence number is not well calibrated, the threshold pattern below is worse than no pattern**, because it converts an unreliable number into an automated action. **Partial evidence now exists in the caveat's favour, not against it**: CMU finds Jev's error gap *concentrated in low-confidence decisions* on several benchmarks ([[jev-as-a-judge-arxiv-2609-26550]]), which is calibration doing its job — but on a subset of benchmarks, from an abstract, with no reliability diagram.
- Early access; no production receipts. Access runs through **Vercel's AI Gateway** with a waitlist ([[isenberg-ryan-vogel-jev-is-here-2026-09-18]]) — which puts [[guillermo-rauch|Rauch's]] platform in front of the cheap-judgment layer as its distribution path.

## When to Use It

**The vendor's own scope rule** ([[isenberg-ryan-vogel-jev-is-here-2026-09-18]]): *"at any point where a business makes fast, repeatable decisions on incoming data."* Named applications are **lead scoring, support routing, video clipping and browser control** — the last of which is listed without explanation and is a materially larger claim than the other three.

**Alongside an LLM, not instead of one.** The LLM plans, writes, explains and calls tools; Jev handles the frequent judgments around that work. The named placement is **model routing** — score the request, pick the cheapest model likely to complete it, which is the [[ai-margin-collapse|routing/decision layer]] getting a purpose-built model rather than a cheap general one doing a side job.

### The confidence-threshold pattern

The most portable idea here, and it generalizes beyond this model:

- **High confidence** → act automatically, where the consequence is small
- **Medium** → ask for confirmation, or escalate to a stronger model
- **Low** → route to a human, or gather more information

> *"The thresholds belong in code, where they can be reviewed and changed. A dashboard label may tolerate a weak prediction. A command that deletes data should require a much higher bar."*

The worked example is the useful part: a ticket routed `billing` at **0.52** against `technical` at **0.46**, with overall confidence **0.18**. Billing "won" — and acting on it would be reckless. A single-label API would have returned `"billing"` and hidden that entirely.

> **Nobody operates the low-confidence branch** ([[gregisenberg-escalate-to-human-button-2026-09-25]], 2026-09-25). [[greg-isenberg|Isenberg]] points out that *"every personal agent right now is fully AI — Muse, Instinct, all of them"*, and that none can hand a job to a person: *"there's the 1 thing a week that needs an actual person. Right now I'm the person."*
> **The threshold pattern above specifies three branches and the industry ships two.** Act and escalate-to-a-stronger-model are built; route-to-a-human is specified and unimplemented. Isenberg's argument for why it is now viable is one line — Meta's **M** died in 2018 because *"humans did 90 and the AI did 10"*, and *"that ratio is flipped now"* — which is unevidenced but falsifiable, and names the exact failure mode a revival would have to beat.

## The TypeSafe position — "Build Prod, Not God"

The manifesto is a real architectural argument, worth separating from the product:

- **"We already have general intelligence."** The claim is that *"the bottleneck isn't raw intelligence. It's that today's intelligence is hard to build on."*
- **The horseless carriage**: RLHF trains models to be *"a helpful, articulate, pleasant assistant… Reasonable goals if you assume a human is on the other side of the model. Yet the foreseeable consequence is AI that requires humans in the loop instead of running in the background."*
- **The proposal**: AI as *"a primitive that any programmer can invoke for semantic judgement and decisions, while still using code for what it's best at: exact computation."* Or: *"Computers can do so much by just branching on bits, imagine if they could also branch on common sense, understanding, and intent."*
- **"Intelligence today is like databases before SQL: powerful, but every use is bespoke."**
- **Safety as a precondition for composition**, which is the sharpest point: *"You let a component run unattended if it's reliable; you only build on top of it if it's trustworthy. It takes trust to bury a dependency five layers deep in a system."*

TypeSafe names the lineage itself: *"the dream of neuro-symbolic AI… sometimes cheekily summarized as 'smart if-statements.'"*

## Compared To

- **Structured outputs / tool calling on a general LLM** — the incumbent approach. Removes brittle parsing but the model is still generative, still sequential, still priced per token.
- **[[control-flow-agents]]** — the same instinct from the practitioner side (deterministic code holds the control flow, the model supplies judgment). Jev is that argument shipped as a model rather than a pattern.
- **[[graph-engineering]]** — *"deterministic code controls predictable routing"* is listed there as an open hard problem; this is a vendor attacking it directly.
- **[[loop-engineering]]** — Jev targets the judgment calls inside the loop, not the loop itself.

## Community Sentiment

**Independently evaluated — and the primary corrects this page (2026-09-28).** A **Carnegie Mellon** paper tests Jev as an LLM-as-judge substitute: **arXiv:2609.26550**, *"JEV-as-a-Judge: Accept When Confident, Escalate When Unsure"*, Yubo Li, Yidi Miao, Ramayya Krishnan and Rema Padman, submitted **2026-09-22** ([[jev-as-a-judge-arxiv-2609-26550]]). The wiki first folded this **secondhand** on 2026-09-27 from a practitioner thread ([[jev-as-judge-cmu-paper-and-plugin-evals-2026-09-27]]) and **overstated the failure**; the abstract, fetched 2026-09-28, is the version to trust.

**Method.** Compared against **sixteen** generative and reward-model judges, with **blinded human adjudication**. Neither detail survived the secondhand rendering, and both raise how much the headline result carries.

**Where it holds** — within **three percentage points** of a state-of-the-art LLM judge, the strongest comparator, on **ordinary preference** and **evidence-grounded factuality**, at **0.36% of that comparator's fee**.

**Where it falls behind** — *"larger gaps arise when judgments require **checking a derivation** or **resisting an elaborately written wrong answer**."* That boundary is confirmed in the primary and is the operationally important half: **the routing pattern is strongest on shallow, reference-grounded judgments.**

**Correction — confidence is more reliable than this page claimed.** The 09-27 fold, following the thread, recorded *"in those cases, confidence did not reliably expose the errors"* and treated it as CMU confirming the calibration warning above. **The abstract says close to the reverse:**

> *"On several benchmarks, JEV's gap to this comparator is **concentrated in low-confidence decisions**."*

**Errors clustering where confidence is low is the signal working** — and is precisely why the **frozen cascade retains 99% of the comparator's accuracy**. A confidence number that failed to expose its own errors could not support a cascade at all. The two readings are not flatly opposed — *"several benchmarks"* is not all of them, and the harder categories may behave differently — but **the calibration caveat above remains a caveat, not a confirmed finding.** It has partial evidence *for* calibration and none against.

**One number previously cited here is not in the paper.** The cascade was written up as running at *"roughly 57 percent of its fee"*. **The abstract says only "at lower cost"** and gives no percentage; **57% is the thread's, unsourced**, and has been removed. The **0.36%**, **three percentage points** and **99%** figures are confirmed verbatim.

*(Abstract only — the full PDF is unread, so per-benchmark breakdowns and the comparator's identity are unexamined.)*

**An ecosystem in twelve days.** A community plugin (`aaddrick/building-with-typesafe-jev`) ships best practices, **anti-patterns**, an API reference and links to **150+ community projects** — Jev launched 2026-09-15. Its author's own eval — six coding tasks × 10 runs, three conditions, **three judges from three providers with majority deciding** — scores **no plugin 0.65 / official plugin 0.77 / this plugin 0.96**. Better methodology than most vendor benchmarks, and self-run on his own plugin; a commenter's *"can you share some real use examples?"* is unanswered.

*(Plugin not fetched. The CMU paper is now sourced to the primary above; the plugin author's eval is still secondhand.)*

**The thesis is independently confirmed by a different vendor, nine days before Jev launched (backfill, 2026-09-06).** [[pachaar-llm-routing-can-cost-more-2026-09-06]] — by the same practitioner who wrote this page's explainer — reports **Katanemo's Arch-Router: 1.5B parameters fine-tuned for one job** (read a conversation, compare against route descriptions, emit JSON), which **beat Claude 3.7 Sonnet on routing accuracy while running 28× faster.** Its successor, **Plano-Orchestrator**, *"edges out GPT-5.1 and Claude Sonnet 4.5 on overall routing accuracy, with the widest margin on coding."*

**This is Jev's argument, measured, on a named task, against named comparators — and it is the stronger version of it.** The reasoning given is the one that matters: *"routing needs no prose generation, no tool calls, no multi-step reasoning, so **the capability surface is small enough that a tiny model covers it completely.**"* **That is the same insight as the llama.cpp finding below — the capability was never about a special model, it is about not generating text.**

**And it answers the double-inference objection this page has not addressed.** A classifier in front of every request is *"a fixed tax"* that can exceed the savings. Arch-Router avoids it by **running inside the proxy rather than as a billed API call**: *"the cost shows up as roughly 200ms of added latency, not as a second line on your invoice."* **Jev is sold as an API, which means Jev-as-router pays that tax and Arch-Router does not** — a structural disadvantage on the use case ([[ai-margin-collapse|model routing]]) this page names as its primary placement.

*(Sponsored content for DigitalOcean; the Arch-Router and Plano comparisons are the sponsor's own benchmarks of its own models, shown as images not read in this ingest.)*

**TypeSafe raises $870M at $7.5B — twenty-four days after launch (2026-10-09/10).** ([[dailybrief-roundup-2026-10-09]], TechCrunch and typesafe.ai). **Jev left stealth on 2026-09-15.**

**What the market is pricing, stated plainly: $7.5B for a model whose single load-bearing claim this page has recorded as unevidenced since the day it was created.** Calibration is the product — RLCD is named, and **no reliability diagram or held-out calibration data has been captured in three and a half weeks.** The only external measurement is CMU's, which is **suggestive in Jev's favour and explicitly partial** (*"on several benchmarks"*, [[jev-as-a-judge-arxiv-2609-26550]]).

**And it is being priced into a window where the interface stopped being scarce.** In the same twenty-four days: a hobby clone, **OpenAI's Decisions API shipped with third-party tooling**, **`llama.cpp` scoring options in a single forward pass**, and **Katanemo's 1.5B Arch-Router beating Claude 3.7 Sonnet at routing while running inside a proxy rather than as a billed call.** **The valuation is a bet that calibration is the moat.** That may well be right — it is the one thing none of the four reimplementations claims — **but the wiki should record that the bet is on the unevidenced part, not on the demonstrated part.**

**TypeSafe AI still has no company page.** Two surfaces now (launch, funding round) and a third-party valuation report; **create-candidate, and the $870M makes it a strong one.** *(TechCrunch plus the company's own announcement; no investors, terms, or revenue captured, and "non-text AI model" is TechCrunch's framing.)*

**The competitor shipped, with third-party tooling, in eight days (2026-10-07).** OpenAI's Decisions API — previewed at DevDay on 09-29 — is live, and [[simon-willison|Willison]] has published **`llm-openai-decisions 0.1a0`** against it ([[dailybrief-roundup-2026-10-07]]). **Preview to shipped endpoint to third-party plugin in eight days** is faster than this page's own ecosystem formed, and it resolves the open question from the 09-29 fold in the less favourable direction: **the incumbent is not experimenting.** What is still unanswered is the one that matters — **whether the endpoint returns a distribution or a label**, which is the entire basis of the confidence-threshold pattern below. *(Plugin listing via the brief; neither the API docs nor the plugin were fetched.)*

**The interface is now commodity, in eighteen days (2026-10-02).** Three independent implementations of Jev's shape have appeared since launch on 2026-09-15, and the third is the one that matters:

| Date | What | Where it sits |
|---|---|---|
| 2026-09-28 | `firelex/jeff` — *"Jev-compatible 0.8B decision models, trained at home, ~30 ms"* | hobbyist reimplementation |
| 2026-09-29 | **OpenAI's Decisions API** — Luna given *"a predefined set of options to choose from"* | incumbent with distribution |
| 2026-10-02 | **`llama.cpp` `/v1/systemone`** — *"scores supplied options and returns probabilities **in a single forward pass** instead of generating text"* | **the default local runtime** |

**The `llama.cpp` endpoint is the significant one and it is not about competition.** OpenAI's API is a competitor; a hobby clone is flattery. **`llama.cpp` adding a scoring endpoint makes the primitive available to anyone with any open-weights model and no API account at all** — and *"in a single forward pass"* is the whole trick, since it means the capability was never about a special model. **It is about not generating text.** Any model with a tokenizer can score a fixed option set; TypeSafe's contribution was noticing that this is a product.

**That sharpens the question this page has been circling.** If the *interface* is a forward pass anyone can implement, then **Jev's defensible asset is RLCD calibration and nothing else** — the claim that the returned probability tracks accuracy. The page has said from the start that calibration is the entire product; **three reimplementations in under three weeks, none of which claims calibration, is the strongest available evidence that the page framed it correctly.**

**And it raises the risk the page already named.** A schema-bound scorer with uncalibrated confidence is precisely the *worse-than-no-pattern* case, and the number of ways to get one has just gone from zero to three.

**Latent Space on the speed of the response (2026-10-01, [[dailybrief-roundup-2026-10-01]]):** *"How OpenAI shipped its Jev competitor in 1 Week."* **Independent confirmation of the read this page made from Willison's live blog** — and the brief's own gloss is worth keeping: *"the hard part isn't the model, it's integration & ops."* **If a frontier lab can ship the interface in a week, first-mover advantage on the interface is worth about a week.**

**OpenAI previews a Decisions API fourteen days after launch (2026-09-29).** At DevDay: an API that gives *"the Luna model a predefined set of options to choose from"* and responds *"in a fraction of a second"* ([[willison-openai-devday-2026-live-blog-2026-09-29]]). **[[simon-willison|Willison]], in the room, names it as the response**: *"sounds like their response to Jev, which came out of stealth less than two weeks ago."*

**This is the most consequential thing to happen to this page since the model launched, and it cuts against the economics argument above.** Jev's case rests on being a purpose-built decision model that is 100×–200× cheaper than asking a frontier model to do the same job. **A constrained-choice endpoint on an existing frontier line does not have to win that comparison — it has to be close enough while already being in the buyer's account.** The wiki has watched this shape before: the value accrues to whoever holds the distribution, not whoever shipped first.

**What is not known, and all of it matters:** pricing, latency against Jev's 200 ms, whether Luna returns a **distribution or a single label** (the entire basis of the confidence-threshold pattern below), and whether anything analogous to RLCD calibration applies. **A predefined set of options is a schema; it is not necessarily a calibrated probability**, and on this page that distinction is the product. *(Preview, per a live blog; no docs, pricing or specs fetched.)*

**A second derivative, and this one addresses the right problem (2026-09-29).** **Jevstiller** — *"distill Jev into a local model, with a **disagreement bound**"* ([[dailybrief-roundup-2026-09-29]], Show HN). **Where `firelex/jeff` copies the interface, this one attacks the thing the interface cannot give you.** A distilled local model with a stated bound on how often it disagrees with the teacher is at least *making a claim that could be checked* — and the calibration caveat above says exactly that an uncalibrated confidence number makes the threshold pattern worse than no pattern. **A disagreement bound is not a calibration guarantee** — agreeing with Jev is not the same as being right, and the bound's tightness, the distribution it holds over, and whether it covers the low-confidence region are all uncaptured. **But it is the first Jev derivative to acknowledge that the number has to mean something.** *(Show HN listing; not fetched, no evals, no adoption.)*

**An open-weights reimplementation in thirteen days (2026-09-28).** `firelex/jeff` — *"Jev-compatible 0.8B decision models, trained at home, ~30 ms"* ([[dailybrief-roundup-2026-09-28]]). **Jev launched 2026-09-15.** Three things worth noting and one worth resisting: the **interface is being cloned, not just the idea** ("Jev-compatible"), which is what happens to an API that is small enough to copy; **0.8B and home-trainable** puts the decision-layer model class within reach of an individual, unlike the frontier models it routes for; and **~30 ms** is faster than the 200 ms the vendor demo showed. What to resist: **this is a GitHub listing with no evals, no calibration evidence and no adoption.** The calibration caveat above applies far more sharply to a home-trained model than to a vendor's — RLCD is the entire product, and a reimplementation of the *interface* is not a reimplementation of the *training*. **A schema-compatible model with uncalibrated confidence is exactly the "worse than no pattern" case.**

**Independent surfaces arrive within a week (2026-09-21/22)** ([[dailybrief-roundup-2026-09-22]]): [[simon-willison|Willison]] writes *"Jev introduces a new shape of LLM"*; Latent Space runs *"Jev: System One models for Prod, not God"* with TypeSafe CEO Diogo Almeida; and Willison ships **`llm-typesafe 0.1a0`**, adding Jev to the LLM CLI.

**These validate attention, not calibration.** This page's central caveat — that calibration is the entire product and no reliability data exists — is untouched by a plugin and two write-ups. Note the manifesto's *"Build Prod, Not God"* framing has become the Latent Space headline, which is adoption of the *positioning* as much as the model.

Limited and early. [[akshay-pachaar|Pachaar's]] explainer notes the reaction was *"unusually strong for a model that cannot hold a conversation"* — and is also the source of the sharpest correction on the record, pushing back on the no-hallucination claim. No independent evaluation captured.

## Resources

- [[jev-typesafe-system-one-model-2026-09-18]] — explainer, comparison thread, launch post and manifesto
- [[dailybrief-roundup-2026-09-16]] / [[dailybrief-roundup-2026-09-17]] — first two brief mentions
- [[jev-as-a-judge-arxiv-2609-26550]] — **the CMU primary**; cite this, not the secondhand fold
- [[jev-as-judge-cmu-paper-and-plugin-evals-2026-09-27]] — the secondhand fold, partly superseded; plugin evals still live here
- [[isenberg-ryan-vogel-jev-is-here-2026-09-18]] — Ryan Vogel walkthrough; 18 cents / 1,700 emails, 200 ms, Vercel Gateway. **Listing depth; no transcript.**
- [[ai-margin-collapse]] — why a purpose-built routing model matters economically

## Verification-pending

Independent latency/cost benchmarks against the 100×–200× claim; **a reliability diagram for RLCD** (the CMU abstract is suggestive, not sufficient); the **full CMU PDF** — per-benchmark breakdowns and the comparator's identity; production deployments; pricing; whether "TypeSafe AI" warrants its own company page; **what "browser control" means** for a 200 ms schema-bound classifier.
