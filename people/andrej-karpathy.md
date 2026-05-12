---
name: Andrej Karpathy
type: person
affiliation: Eureka Labs (founder)
signal_sources: [twitter, blog, github, youtube]
last_updated: 2026-05-11
---

## Who They Are
AI researcher and educator. Co-founded OpenAI, led Tesla Autopilot's vision team, returned to OpenAI, then went independent. Founder of [[eureka-labs]], an AI education company. One of the most influential voices in practical AI/ML — known for making complex concepts accessible without dumbing them down. Strong following among both researchers and practitioners.

## Their Current Focus
Building AI education tools at Eureka Labs. Actively vibe-coding and agentic engineering — side projects folder is "extremely full." Personally maintains an LLM Wiki from articles and uses it as a primary knowledge-management tool. Also known for neural network tutorials (nanoGPT, micrograd, [[microgpt]]) and the "Software 2.0"/"Software 3.0" framing. Released [[microgpt]] (200-line, zero-dependency GPT in a single Python file) on 2026-02-12 — "the culmination of multiple projects... and a decade-long obsession to simplify LLMs to their bare essentials." — [[karpathy-microgpt-2026-02]]

## Notable Takes
- **LLM Wiki pattern**: Raw sources should be "compiled" into a structured wiki — "Obsidian is the IDE; the LLM is the programmer; the wiki is the codebase." — [[karpathy-llm-wiki-gist]]
- **On wiki maintenance**: "Humans abandon wikis because maintenance burden grows faster than value." — [[karpathy-llm-wiki-gist]]
- **On schema**: CLAUDE.md is co-evolved by you and the LLM over time — not defined once and frozen — [[karpathy-llm-wiki-gist]]
- **Software 2.0**: Neural networks are a new kind of software where you specify behavior through data rather than code — predates current LLM wave but predicted its direction
- **Software 3.0**: "What is the piece of text to copy paste to your agent? That's the programming paradigm." Prompting is programming; the LLM is an interpreter; the context window is your lever. — [[karpathy-vibe-coding-agentic-engineering]]
- **Vibe coding vs. agentic engineering**: "Vibe coding raises the floor for everyone. Agentic engineering is about preserving the quality bar of professional software — you're not allowed to introduce vulnerabilities." — [[karpathy-vibe-coding-agentic-engineering]]
- **>10x speedup claim**: "People who are very good at [agentic engineering] peak a lot more than 10x from my perspective right now." — [[karpathy-vibe-coding-agentic-engineering]]
- **December 2025 inflection**: The moment Karpathy stopped correcting agent output — "I can't remember the last time I corrected it" — and started trusting the system. A "very stark transition." — [[karpathy-vibe-coding-agentic-engineering]]
- **Verifiability thesis**: LLMs excel where outputs are verifiable (RL with verification rewards). Explains the jagged capability profile — peaks in math/code, gaps in common sense. — [[karpathy-vibe-coding-agentic-engineering]]
- **Jagged intelligence**: "How is it possible that state-of-the-art Opus 4.7 will simultaneously refactor a 100,000 line codebase or find zero day vulnerabilities and yet tells me to walk to this car wash?" — [[karpathy-vibe-coding-agentic-engineering]]
- **Ghosts vs. animals**: LLMs are "summoned ghosts" shaped by data and reward functions, not animal intelligences. "If you yell at them, they're not going to work better or worse." — [[karpathy-vibe-coding-agentic-engineering]]
- **You can outsource thinking but not understanding**: Cited a tweet he thinks about "every other day" — "You can outsource your thinking but you can't outsource your understanding." — [[karpathy-vibe-coding-agentic-engineering]]
- **Human skills that matter more**: Taste, aesthetics, judgment, spec ownership, and conceptual understanding (not API details). "You're in charge of the taste, the engineering, the design." — [[karpathy-vibe-coding-agentic-engineering]]
- **Agent-native infrastructure**: "Why are people still telling me what to do? I don't want to do anything. What is the thing I should copy paste to my agent?" Docs/tooling still written for humans — transition to agent-native is mostly unbuilt. — [[karpathy-vibe-coding-agentic-engineering]]
- **Code quality concern**: Agent-generated code is often "bloaty" with "copy paste and awkward abstractions that are brittle — it works but it's just really gross." Expects future model improvement; labs haven't run RL on aesthetics/simplicity. — [[karpathy-vibe-coding-agentic-engineering]]
- **1B model claim** (via Dwarkesh podcast): a 1B parameter model on clean data could match a 1.8T parameter frontier model — current large models burn most capacity on noise memorization; proposes separating a small cognitive core from external retrieval memory — [[thread-aakashgupta-1b-model]]
- **"The Bitter Lesson" alignment**: Generally agrees with Sutton's thesis that scale + compute beats hand-crafted approaches
- **LLM tutorial video**: a 2-hour Karpathy video on using LLMs is circulating; community describes it as better than "99% of AI influencers" — [[thread-phosphenq-karpathy-video]]
- **"Agentic engineering" term confirmed as working vocabulary**: an X comment thread (May 2026) on @benln's share of Karpathy's framing shows practitioners independently adopting "agentic engineering" as their category label for hiring conversations, skill stratification, and organizational planning — [[benln-x-karpathy-agentic-engineering-2026-05]]. Rahul Kumar (@hellorahulk): "karpathy calling the shift agentic engineering is the label i keep reaching for when hiring asks what changed." The term is working vocabulary, not just a Karpathy coinage.
- **microgpt as the algorithmic core**: 200-line, zero-dependency GPT in a single Python file. "Everything else is just efficiency." Companion to nanoGPT and micrograd — the explicit thesis is that the GPT *algorithm* is small; the rest of modern LLM stacks is engineering for scale. — [[karpathy-microgpt-2026-02]] / [[microgpt]]
- **2022 prediction of Software 3.0** (resurfaced May 2026): Karpathy's 2022 essay *Deep Neural Nets: 33 years ago and 33 years from now* projected that by 2055 "you will ask a 10,000,000X-sized neural net megabrain to perform some task by speaking... to it in English." This is the [[software-3-0]] thesis stated 4 years before he formally names it at AI Ascent 2026. — [[karpathy-lecun1989-33-years]]
- **Macro-level architectural constancy**: "Not much has changed in 33 years on the macro level. We're still setting up differentiable neural net architectures made of layers of neurons and optimizing them end-to-end with backpropagation." The revolution has been scale (data, model, compute), not paradigm shift. — [[karpathy-lecun1989-33-years]]
- **Independent practitioner echo of two-mode framing (Simon Willison, May 2026)**: [[simon-willison]] reports the practitioner discipline that distinguishes [[vibe-coding]] from [[agentic-engineering]] is harder to maintain in practice as agents improve — even ceiling-side practitioners find themselves not reviewing every line. Willison frames the convergence as uncomfortable, not triumphant. Independent extension of Karpathy's framing from a long-tracked high-signal voice. — [[simonwillison-vibe-coding-agentic-engineering-2026-05]]
- **January 2026 Claude code-writing complaint thread spawned an ecosystem**: a Karpathy X thread naming three Claude failure modes — silent wrong assumptions, over-complication, "orthogonal damage" to nearby code — was packaged by [[forrest-chang]] into a 4-rule CLAUDE.md template that became the fastest-growing single-file GitHub repo of 2026 (~120K stars by May). [[mnilax-claude-md-12-rules-2026-05-09]] later extended it to 12 rules with empirical mistake-rate measurements. The pattern (see [[claude-md-pattern]]) is now community-canonical practice for Claude Code project setup.
- **HTML as the new default LLM output format (May 8 2026)**: quote-tweeting [[thariq-shihipar]]'s "Unreasonable Effectiveness of HTML," Karpathy articulates a 4-step taxonomy — raw text → markdown (current default) → HTML ("early but forming new good default") → ... → interactive neural videos/simulations (the speculative endpoint, cited via [[thread-zan2434-flipbook]]). Reasoning: "audio is the human-preferred input to AIs but vision is the preferred output from them"; ~1/3 of the brain is dedicated to vision. Flags an open architectural question: how procedural Software 1.0 artifacts (deterministic interactivity) get woven together with neural artifacts (diffusion grids). First Karpathy-level voice connecting the *current* HTML-output prompting practitioner pattern ([[claude-code]] / [[willison-html-effectiveness-2026-05]]) to the *long-arc* [[model-rendered-ui]] research direction as a single trajectory. — [[karpathy-html-output-taxonomy-2026-05-08]]

## Where to Follow
- Twitter/X: @karpathy
- GitHub: github.com/karpathy
- YouTube: Andrej Karpathy (tutorials channel)
