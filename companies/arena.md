---
name: Arena (Arena AI)
type: company
focus: AI leaderboard and evaluation infrastructure
status: gaining-traction
last_updated: 2026-10-21
---

## What It Is

**Arena (Arena AI)** turned the **LMSys Chatbot Arena** — a research leaderboard — into a business, reaching a **$100M valuation in under a year.**

**The wiki tracks it as the clearest instance of evaluation infrastructure becoming a venture-scale category**, alongside METR, Gray Swan, Epoch AI, Sophont Medmarks and Anthropic's Public Record. **The thesis it tests is whether neutral evaluation is defensible as a business** — and that is the question its later funding makes sharper rather than settles.

## Traction Signals

- **2026-10-08: a $200M Series B at $3.1B, and the launch of an Alignment Index** ([[dailybrief-roundup-2026-10-08]]). **A 31× valuation increase in roughly fifteen months.**
  > **The Alignment Index is the part [[frontier-ai-governance]] cares about, and the structure deserves saying plainly.** That page's recurring complaint is that voluntary frameworks carry no measurements. **An index is a measurement — produced by a venture-funded company whose valuation depends on the category it is measuring.** Not disqualifying: METR and the UK AISI both evaluate models they have relationships with. **But it is a different incentive from a non-profit's or a national institute's**, and the wiki should capture the index's methodology and funding model before citing any of its scores.
- **2026-06-29: a $100M business in under a year** ([[arena-100m-evaluation-infrastructure-2026-06-29]]) — the growth anchor, and the first validation that **neutral evaluation tooling has defensible commercial value.**
- **Three prior substantive mentions** as a recurring leaderboard reference across source pages before this page existed.
- **Evolved from LMSys**, a research tool, to a corporate entity. *(The corporate transition detail is uncaptured.)*

## How to Use It

- **The public leaderboard** — head-to-head model evaluation, free to read.
- **Enterprise and API access** *(pricing uncaptured).*
- **The Alignment Index** (announced 2026-10-08, no results captured).

**What the wiki does not know and should**: whether rankings come from **Elo over human preference votes, LLM-as-judge, or something else.** That decides how much any Arena number is worth — and it bears directly on the finding from [[anthropic-automating-eval-design-hillclimbing-2026-09-28|Anthropic's eval guidance]] that *"you pick the judge model, and it should not be the model you are testing."*

## Compared To

- **[[metr|METR]]** — a mission-driven evaluation organisation against Arena's commercial one. **METR rejected a frontier launch's results** ([[gpt-5-6|GPT-5.6]], 2026-06-26); **the open question for Arena is whether a venture-funded evaluator can do the same thing to a customer.**
- **[[gray-swan|Gray Swan]]** — red-teaming rather than leaderboard evaluation; the two together make a two-tier evaluation-business cohort.
- **Epoch AI (MirrorCode), Sophont Medmarks** — domain-specific evaluation against Arena's general-purpose leaderboard.
- **The UK AI Security Institute** — the national-institute comparison, and the one now partly funded by [[nvidia|NVIDIA]] compute ([[dailybrief-roundup-2026-10-14]]). **Every evaluator the wiki tracks now has a funding relationship worth disclosing.**

## Resources

- [[arena-100m-evaluation-infrastructure-2026-06-29]] — the $100M anchor
- [[dailybrief-roundup-2026-10-08]] — the Series B and the Alignment Index
- [[metr]] · [[gray-swan]] · [[anthropic-public-record]] · [[frontier-ai-governance]]
- [[gpt-5-6-launch-3-event-cluster-2026-06-26]] — METR's rejection, the comparison case for evaluator independence

## Verification-pending

- **Leaderboard methodology** — Elo over human votes, LLM-as-judge, or other. **The single most load-bearing unknown on this page.** *(**Resolved 2026-10-21:** a Bradley-Terry model fitted to pairwise battles, i.e. blind side-by-side human votes per third-party explainers, with style control, reweighting for models with few battles, and closed-form confidence intervals. The code is open source (Arena-Rank, Apache 2.0). See [[arena-rank-methodology-2025-12-18]]. The new **Alignment Index** has no published method yet.)*
- **The Alignment Index's methodology and funding model**, before any score from it is cited.
- TechCrunch primary for the $100M story.

> [!note] Rewritten 2026-10-15
> The 2026-06-29 version carried **24 instances of `canonical-` filler** from an automated pass, including in the `focus:` frontmatter field. Content preserved, prose rewritten, and the 2026-10-08 Series B and Alignment Index added — the page was four months stale on a company that had raised at 31× in the interim. See lint rule 7.

*(2026-10-21 backlog triage: 3 items removed. Corporate-profile facts; the methodology questions are the ones the wiki cites against.)*

