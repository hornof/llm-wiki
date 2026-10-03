---
name: Model-Rendered UI
type: concept
maturity: emerging
last_updated: 2026-10-03
---

## Definition
A UI paradigm where every pixel on screen is generated live by a model — no HTML, no DOM, no layout engine. The model streams visual output directly to the user, with any region of the image potentially interactive. The opposite of structured UI frameworks.

## Why It Matters
If viable at scale, this collapses the distinction between "what the model produces" and "what the user sees." There is no rendering layer to constrain or mediate the output — the model IS the UI. This has implications for AI engineering: the bottleneck shifts from layout/component engineering to model accuracy, statefulness, and latency.

## Current State
Very early. Flipbook (flipbook.page, April 2026) is the clearest public prototype: built by Zain Shah, Eddie Jiao, and Drew O'Carr; uses a heavily optimized LTX Studio video model streamed at 1080p/24fps via WebSockets to Modal Labs GPU infra. The team acknowledges it is slow and limited to visual explanations today. Demos in the announcement thread were sped up.

Related: "Neural Computers" (arxiv.org/abs/2604.06425, April 2026) — video models that generate screen frames from instructions, pixels, and user actions in both CLI and GUI settings.

## Key Constraints
- **Latency**: streaming 1080p pixels from a model is expensive; requires serverless GPU infra
- **Statefulness**: current models are not stateful enough for complex interactive UIs
- **Accuracy**: model must reliably produce the right visual output; no fallback layout engine
- **Interactivity**: defining interactive regions requires additional machinery beyond pixel generation

## Expansion Thesis
From the Flipbook thread: "As the models get more accurate and more stateful, the set of things worth doing this way will expand. Even ones you'd assume need structured UIs like coding." — [[thread-zan2434-flipbook]]

## Karpathy's 4-Step Output-Format Taxonomy (May 2026)

[[andrej-karpathy]] (May 8 2026, [[karpathy-html-output-taxonomy-2026-05-08]]) places model-rendered UI as the **endpoint** of a multi-stage progression in how LLMs deliver output to humans:

1. **raw text** — hard/effortful to read
2. **markdown** — current default; "bold, italic, headings, tables, a bit easier on the eyes"
3. **HTML** — "still procedural with underlying code, but a lot more flexibility on the graphics, layout, even interactivity" — *"early but forming new good default"*
4. …intermediate stages (slideshows, mixed media)
5. **interactive neural videos / simulations** — generated directly by a diffusion neural net

The endpoint (5/n) is explicitly the Flipbook-style direction — Karpathy cites [[thread-zan2434-flipbook]] by URL as the place "the direction" extrapolates toward. *Model-rendered UI is not a leap; it is the asymptote of the output-format ladder practitioners are climbing right now via HTML-output prompting.*

### Reasoning behind the trajectory

Karpathy's argument for *why* output should evolve this way: **vision is the human-preferred output modality** ("vision is the 10-lane superhighway of information into brain"; ~1/3 of the brain is dedicated to it). Audio works as the human-preferred *input*, but text/markdown rendering bottlenecks the vision-bandwidth side of the mind-meld between humans and AIs. Each step in the taxonomy moves output further along the vision-bandwidth axis.

### Open architectural question

Karpathy flags an unresolved question on the path from step 3 to step n: how exact/procedural "Software 1.0" artifacts (e.g. interactive simulations with deterministic behavior) get woven together with neural artifacts (diffusion grids). The model-rendered-UI program does not yet have a clean answer for *deterministic interactivity inside a generated pixel stream*.

## Practitioner Bridge: HTML Output Prompting (May 2026)

The practitioner-pattern "ask Claude for HTML, not Markdown" ([[thariq-shihipar]] / [[willison-html-effectiveness-2026-05]] / [[karpathy-html-output-taxonomy-2026-05-08]]) is the *currently-shipped* prong of the taxonomy above (step 3). It is concretely available today inside [[claude-code]] and on Claude.ai. The model-rendered-UI research direction is the *next* prong (step n). Karpathy's May 2026 framing is the first time the wiki has a primary-voice articulation of *the practitioner pattern and the research direction as a single ladder rather than two separate developments*.

## Adobe: self-assembling websites (July 2026)

A [latent.space piece](https://www.latent.space/p/the-website-of-the-future) surfaced in the [[dailybrief-roundup-2026-07-06|2026-07-06 Daily Brief]] reports Adobe experimenting with **agentic sites that assemble a different page for every visitor**, generated per user intent rather than authored once. This is the *application-layer* cousin of model-rendered UI: still (for now) structured web output, but with the page composition itself model-generated at request time. Conceptually significant; no concrete working example in the coverage yet. Watch whether "page assembled per visitor" and "pixels streamed per visitor" (Flipbook) converge or stay distinct.

## "Stop making TUIs" + the agent interface (Aug 2026)

Two 2026-08 dev-practice signals ([[dailybrief-roundup-2026-08-22]]) push the same direction from the *tooling* side:
- **Thomas Ptacek — "Stop Making TUIs"** (via [[simon-willison]]): coding agents have made **native GUIs cheap enough that the marginal cost of a real UI is now below the cognitive tax of a TUI workflow.** The econ flipped — a tool built by an agent *"doesn't feel like a script anymore,"* so users actually use it. The practitioner-facing consequence of model-rendered UI: when generating a UI is nearly free, the default output stops being terminal text.
- **"The Evolution of the Agent Interface"** (Latent Space): the agent is **absorbing into model weights**, and the durable surface becomes the **interface that captures human attention**, not the control layer over the model. Same trajectory as this concept — the rendered interface, not the harness plumbing, is where the human sits.

## The visual layer is where it stops — practitioner consensus (2026-09-28)

A 100+ comment r/ClaudeAI thread ([[reddit-claude-beautiful-uis-vs-ai-slop-2026-09-28]]) states the gap precisely, and the precision is what makes it usable:

> *"Claude is actually pretty good at **structure, UX flow, information architecture**, and getting a functional dashboard together. But when it comes to the **visual layer**, everything starts looking like generic AI-generated SaaS: cards everywhere, random gradients / glows, huge border radiuses, Lucide icons everywhere, pills and badges for no reason… Basically AI slop."*

**This page has been about models producing interfaces; this is the first source that says which part of that works.** The split is clean and it is not the one you would guess: **the structural and architectural work holds, and the aesthetic layer collapses to a mode.** That is a claim about where the training signal is dense, and it is checkable.

**The thread's consensus — *"you're getting slop because you're not being a director"*** — resolves into four methods (reference images, a design system, `impeccable.style`, screenshot→critique→fix loops). **What unites them is that every one removes a degree of freedom rather than supplying taste**: a reference constrains the target, a design system constrains the vocabulary, a critique loop constrains by comparison. **None makes the model have taste; each makes taste unnecessary at that step** — the same move as schema-bounding output instead of asking for care.

**The loop the poster asked for does not exist.** He describes a closed cycle — render, look, notice what's missing, create the asset, place it, re-screenshot, critique, iterate — and **the answer from 100 comments is that the critic is still a person.** See [[loop-engineering]].

**Discount `impeccable.style` accordingly**: one strong recommendation with me-toos, and the most substantive reply argues against it **from its own landing page** (*"5 buttons, 10 icons, text all over the place"*) while conceding the author *"seems to have some serious skill."* A name to watch, not an endorsement.

*(Self-selected practitioner sentiment; no before/after anyone can inspect, and no definition of "beautiful.")*

## Tooling arrives for the top consensus method, three days later (2026-10-01)

**Pikspec** ([[raw-batch-roundup-2026-10-02]]) — a Chrome extension that clones any page into a working local copy: *"html, css, assets and the hover/interaction states"*, one click, zipped.

**The author's rationale is the section above, restated by someone building for it**: *"when you start a new site with cursor or claude from a blank prompt, you get the same generic ai look every time. same spacing, same fonts, same cards. **if you start from a real page you like, the ai has actual layout, type scale and spacing to work from**, and you edit your way to your own thing instead of fighting slop from scratch."*

**The wiki recorded "feed it references" as the top-ranked consensus method on 2026-09-28. Three days later there is a tool whose only job is to make that step one click.** That is the clearest confirmation available that the diagnosis was right — and it reinforces the observation that **every working method here removes a degree of freedom rather than supplying taste.**

**The technical choice is the interesting part**: *"keeps the **computed styles and states** instead of the raw source."* Resolved values, not authored CSS — which is the form a model can actually use, since a spacing scale expressed through a chain of custom properties and media queries tells it nothing.

**The copyright question is real and the author's caveat is not a defence.** *"Obviously don't ship someone else's site as your own. Use it as a reference and starting point, then make it yours"* is correct advice that does not change what the tool outputs, which is a working copy of a third party's design. **Recorded as a capability and an open legal question, not a recommendation.**

*(Single self-promoting Reddit post; no adoption figures, not installed, not tested.)*

## Related Concepts
- [[world-models]] — related idea: models that predict and generate environment state rather than tokens
- [[agentic-ai]] — agent interfaces may evolve toward model-rendered rather than structured UI
- [[software-3-0]] — same trajectory framed from the programming-paradigm side (natural language as the programming layer; this concept is its output-rendering layer)

## Resources
- [[thread-zan2434-flipbook]] — Flipbook announcement thread (April 2026)
- [[karpathy-html-output-taxonomy-2026-05-08]] — Karpathy's 4-step output-format taxonomy connecting current HTML practitioner pattern to Flipbook-style endpoint (May 8 2026)
- [[willison-html-effectiveness-2026-05]] — Simon Willison amplification of Thariq Shihipar's "Unreasonable Effectiveness of HTML"; step 3 of the taxonomy
- [[svpino-bruin-dac-markdown-doomed-2026-05-15]] — Santiago Valdarrama (svpino) restates the HTML-over-Markdown thesis with the pragmatic *"nobody wants to type HTML"* pivot: HTML as output substrate, YAML/TSX as input. **First wiki-captured counter-take** also appears in the comment thread (Andrii Artemenko: *"Markdown wins on agent readability, human readability, and token efficiency"*) — the thesis is no longer one-sided (May 15 2026)
- [[tools/dac]] — practitioner-instantiated version of the YAML/TSX-to-HTML compile layer; first wiki tool that ships SKILL.md for both Claude Code and Codex
