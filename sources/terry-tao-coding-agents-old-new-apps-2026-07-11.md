---
title: "Terry Tao — \"Old and new apps, via modern coding agents\" (Fields Medalist ports ~24 legacy Java applets to JS; language choice now 'far less relevant')"
type: source
medium: article
url: https://terrytao.wordpress.com/2026/07/11/old-and-new-apps-via-modern-coding-agents/
ingested: 2026-07-12
---

## Summary

Mathematician **Terry Tao** (Fields Medalist, UCLA) publishes a first-person account (2026-07-11) of using modern coding agents to **modernize legacy apps and build new ones** — porting ~24 old Java 1.0 math applets to JavaScript and building new visualization apps in "a couple hours of vibe coding" each. His headline claim: with sufficient context, translation friction between languages is near-zero, so *"the precise language or spec that software is written in has become far less relevant."* A high-signal, vendor-neutral, independent-expert datapoint on agentic-coding effectiveness — surfaced in the [[dailybrief-roundup-2026-07-12|2026-07-12 Daily Brief]].

## Key Claims / Takeaways

- **Legacy modernization is painless**: porting Java 1.0 applets (Besicovitch set, honeycomb, etc.) to JavaScript "proved painless," and the agent even **found two unknown bugs in the original code** — netting out to *"a net wash as far as code quality"* after one minor drag-event bug it introduced.
- **Language choice is now secondary**: *"the precise language or spec that software is written in has become far less relevant"* when enough context exists for the agent to translate.
- **Rapid new-app prototyping**: new apps (special-relativity spacetime diagram reviving an abandoned 1999 project; Gilbreath-conjecture visualizer) took ~a couple hours each; staged development (math engine first, then GUI) helped, though the agent largely managed staging itself. *"I was finally able to generate an applet that matched the vision I had back in 1999."*
- **Verifier-discipline still required**: agents produce *"blatant or subtle bugs"*; Tao frames these as acceptable **only because the apps are non-critical supplements** (*"the downside risk of such bugs is relatively low"*), and stresses human review + testing. Well-structured / well-documented source is what makes translation reliable.
- **Vendor-neutral**: Tao names no specific model or agent — refers generically to "an AI agent" / "LLM-based coding agents."

## Why it matters

- **Independent, non-commercial corroboration** of the wiki's agentic-coding thesis from an author with no vendor or VC incentive — a rare signal quality relative to the practitioner-influencer sources that dominate the [[loop-engineering]] cluster.
- **Reinforces verifier-discipline**: Tao's "net wash on code quality → acceptable only for low-criticality work" is a real-world instance of *a loop that goes green is not a loop that is correct* ([[samueljmcd-loop-engineering-verifier-bottleneck-2026-06-15|McDonald]]) — capability is gated by the criticality-appropriate verifier, which here is human review.
- **"Language becomes secondary" thesis** echoes [[rahulgs-english-code-interpreters-10-point-thesis-2026-06-17|Rahul GS's "english → code interpreters"]] framing from the practitioner side, now confirmed on real legacy-porting work by a domain outsider.

## Pages Updated
- [[loop-engineering]]

## Verification-pending
- `people/terry-tao` deferred (single wiki mention today); create-candidate if Tao becomes a recurring agentic-coding voice.
