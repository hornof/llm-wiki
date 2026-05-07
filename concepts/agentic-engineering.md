---
name: Agentic Engineering
type: concept
maturity: emerging
last_updated: 2026-05-06

---

## Definition
Karpathy's term for the professional engineering discipline of coordinating AI agents to ship production-quality software without sacrificing the quality bar that existed before AI coding tools.

> "Agentic engineering is about preserving the quality bar of what existed before in professional software. You're not allowed to introduce vulnerabilities due to vibe coding. You are still responsible for your software just as before, but can you go faster?" — Andrej Karpathy, AI Ascent 2026

> "You have these agents which are these like spiky entities. They're a bit fallible, a little bit stochastic, but they are extremely powerful. [Agentic engineering is] how do you coordinate them to go faster without sacrificing your quality bar." — Andrej Karpathy, AI Ascent 2026

## Why It Matters
Karpathy asserts the speedup from skilled agentic engineering is well beyond 10x — "people who are very good at this peak a lot more than 10x from my perspective right now." This is not a marginal productivity improvement; it is a capability transformation for engineers who master it.

## Core Responsibilities of the Agentic Engineer
1. **Spec and design authority**: the engineer owns the system design, not the agent. Example: insisting on a persistent unique user ID rather than letting the agent cross-correlate by email address.
2. **Taste and aesthetics**: agent-generated code is often "bloaty," with copy-paste and brittle abstractions. The engineer identifies and demands better.
3. **Oversight**: agents are "intern entities" — remarkable capability, but still require a human who understands what correct looks like.
4. **Conceptual understanding**: knowing *what* the code is supposed to do — e.g., understanding that a tensor has an underlying view and separate storage — even if you've forgotten the exact API details (dim vs. axis, reshape vs. permute).

## What the Agent Handles
- API-level details (exact library signatures, parameter names)
- Boilerplate and fill-in-the-blanks implementation
- Multi-step execution within a well-specified plan

## Agents as Interns
Karpathy uses the "intern" metaphor: agents have exceptional recall and can execute at high speed, but they make category errors on common sense (e.g., cross-correlating user identity via email across systems). The engineer must maintain the big picture.

## Hiring Implications
Traditional interview formats (puzzles, leetcode) are the old paradigm. Karpathy's proposed new interview format:
- Give a large project (e.g., "build a Twitter clone")
- Make it really good, really secure
- Simulate real traffic with agents
- Use an adversarial agent (e.g., "10 Codex 5.4x agents try to break your deployment")
- Evaluate: did the system hold?

## Relationship to Vibe Coding
See [[vibe-coding]]. Vibe coding raises the floor; agentic engineering raises the ceiling. Both are legitimate — they serve different purposes and audiences.

## Tools in This Space
- [[claude-code]] — Karpathy specifically cites "Claude Code or Codex" as the layer where agentic engineering happens
- Codex (OpenAI) — mentioned alongside Claude Code as a primary agentic engineering interface
- [[career-ops]] — flagship open-source example of an agent-leveraged production tool stack (8.2k stars, MIT)
- [[playwright-mcp]] — emerging convention for browser-side execution within agentic workflows

## Related Concepts
- [[vibe-coding]] — the floor-raising complement; entry-level
- [[software-3-0]] — the broader paradigm; agentic engineering is the professional manifestation
- [[verifiability-and-jagged-intelligence]] — explains which domains benefit most from agentic approaches
- [[agentic-ai]] — the broader topic page covering multi-agent patterns, protocols, and tools

## Solo Operator Vision (Naval's Reinforcement)

Naval Ravikant (April 2026) articulates the same capability from an investor/founder perspective: a 1-person company operating at the velocity of a 50-person team via agents. Users report bugs → agent reviews → agent writes fixes, opens PRs, runs tests → founder reviews and ships. No coordination overhead, no political compromise, no vision diluted by committee. This is the market-facing consequence of agentic engineering applied to product companies. See [[saas-disruption-thesis]] and [[naval-ravikant-saas-is-next]].

## Real-World Example: career-ops (April 2026)

[[career-ops]] (santifer, MIT, 8.2k GitHub stars at announcement) is one of the cleanest end-to-end instantiations of agentic engineering in the wild. The pipeline composes:

- **14 skill modes** as the spec layer (the engineer's design authority — what each stage produces)
- **Real Claude Code sub-agents** for `batch` mode, evaluating 10+ job offers in parallel (genuine multi-process parallelism, not prompt-time persona simulation)
- **[[playwright-mcp]]** for ATS-optimized PDF generation
- **A Go TUI on top** (Bubble Tea) for browsing pipeline state
- **Self-modifiability**: because career-ops *is* a Claude Code skill stack, the user asks Claude to rewrite the system itself ("change archetypes to backend roles," "add these 10 companies"). The [[llm-wiki-pattern]] applied recursively to a tool's own configuration.

The author's framing is a textbook agentic-engineering claim — a quality bar is *enforced* (the system refuses to recommend any role scoring below 4.0/5), human judgment is preserved at the decisive step (which offers to pursue), and execution toil (PDF generation, salary research, story banking) is fully agent-driven. **Filter, not firehose** — explicitly inverting spray-and-pray automation. — [[heygurisingh-career-ops]]

## The Missing "Why" Layer (Chamath, April 2026)

Chamath Palihapitiya identifies a team-level gap that individual agent speed gains don't solve: architectural reasoning (the "why" behind decisions) typically lives in Slack threads, Linear tickets, or individual heads. Individual engineers can go faster with AI, but team collective knowledge doesn't compound — so the team goes the same speed or slower. The implication for agentic engineering: agents need access to decision context, not just code. A good multiplayer AI dev experience must capture the reasoning layer, not only accelerate the execution layer. — [[chamath-decision-context-agents]]

## Practical Workflow (Practitioner Distillation, May 2026)

A r/AIAgentsInAction popularization of Karpathy's framing distills agentic engineering into a 4-step working loop. Useful because Karpathy himself articulates the *philosophy* but not a step-by-step procedure:

1. **Spec first** — write what the feature does, edge cases, data model, what can break, *before* prompting the agent. Use the model to help draft if you want, but the spec exists before the agent touches a file. This is the step vibe coders skip.
2. **Scope tasks tightly** — "Build a user auth system" is a vibe prompt. "Implement password reset using existing Resend integration, store the token in Redis with a 15-minute TTL, here's the spec" is a scoped task. Constrained, reviewable, the agent can't drift.
3. **Review the diff like a human PR** — "If you can't explain what a module does, it doesn't merge." Reading every diff is the gate that prevents the [[vibe-coding]] failure modes (security holes compound, context collapses).
4. **Test before shipping** — tests you wrote or reviewed, not tests the agent generated and you skimmed. If tests don't exist, write them first and have the agent pass them.

Three habits the post recommends: spec before every agent task; read every diff (200 lines changed = 200 lines read); run tests before calling anything done. — [[reddit-karpathy-moved-on-from-vibe-coding]]

## Practitioner Reactions: The X Comment Thread (May 2026)

An X comment thread on @benln's share of Karpathy's framing surfaced five distinct practitioner angles that extend the core concept. These are independent voices — not Karpathy — attesting to how the framing is landing in practice. — [[benln-x-karpathy-agentic-engineering-2026-05]]

### The Economics of Being Wrong
ByteCrafter (@bytecrafter_1): the core shift is not that agents write code — it's that **the cost of being wrong has dropped**. When an agent reruns tests in 90 seconds and self-corrects three times before you read the diff, you stop optimizing for first-try correctness. The bottleneck moves to **spec quality**. This is a different claim than Karpathy's "intern" framing — ByteCrafter is pointing to the incentive structure change, not the capability level.

### Floor vs. Ceiling (Confirmed Externally)
Facundo Franco (@facundofranco_): "Vibe coding gives everyone a floor. Agentic engineering raises the ceiling for people who actually understand what they're building." Independent practitioner confirmation of the two-tier model Karpathy articulates.

### Agent-Native Documentation Gap
Gagan (@gagansaluja08): "CLAUDE.md is the only thing we actively maintain for agent consumption. Everything else fails them." This is a strong practitioner signal that Karpathy's observation about docs-written-for-humans is real in the field, not just a theoretical concern. Gagan's "agents are interns — great recall, weak judgment" independently echoes Karpathy's framing, suggesting the intern metaphor has broad resonance.

### Term Adoption in Hiring
Rahul Kumar (@hellorahulk): "agentic engineering is the label I keep reaching for when hiring asks what changed." The term is functioning as a practical category for practitioners navigating the transition — a signal that it is working vocabulary, not just a Karpathy coinage.

### Verifiability and Auditability
Balaji Jegadeesh (@Vbj0818): "Verifiability is the unlock. Agents can generate more work now but the bottleneck moves to knowing what was built, why it changed, and whether the result can be trusted. Agentic engineering is going to need a lot more auditability." This extends [[verifiability-and-jagged-intelligence]] into an organizational requirement — not just an epistemological observation but an operational demand.

### Organizational Harness (Zohar Einy's 7-Point Framework)
Zohar Einy (@ZoharEiny, newsletter.port.io) contributes the most structurally novel take: individual engineer productivity is not enough — agents need an **organizational harness** to function at professional quality. His seven-point list:

1. **Pre-cleared integrations** — agents can only touch what's been explicitly authorized
2. **Context lake** — the memory substrate agents draw from (parallels [[company-brain]] at organizational scale)
3. **Agent registry** — known inventory of agents, their capabilities, their current state
4. **Measurement** — observability layer; you can't govern what you can't see
5. **HITL** — Human-In-The-Loop; structured approval gates at consequential steps
6. **Governance** — policy layer; rules for what agents can and can't do autonomously
7. **Orchestration** — coordination layer; how multiple agents collaborate without collision

This framework is complementary to (not competing with) the individual-engineer framing. Karpathy's agentic engineering addresses the individual practitioner. Zohar's harness addresses the organizational substrate beneath them. See also [[company-brain]] (organizational memory), [[agentic-ai]] (multi-agent patterns), and [[chamath-decision-context-agents]] (the "why" capture gap).

## Practitioner-Discipline Erosion (Simon Willison, May 2026)

[[simon-willison]] reports in a May 6 2026 blog post that the line between vibe coding and agentic engineering is harder to maintain in his own practice: "The problem is that as the coding agents get more reliable, I'm not reviewing every line of code that they write anymore, even for my production level stuff." This does not collapse the analytical distinction (Willison still wants higher-quality output, not just less-checked output), but it does flag that the *review discipline* on which agentic engineering depends has to be actively maintained — agent unreliability used to enforce it, and that enforcement is fading.

Implication for the framing: Karpathy's two-mode picture (floor-raise vs. ceiling-raise) is conceptually clean, but the practitioner gap between them is narrower in 2026 than it was at AI Ascent. The professional discipline now requires *active* review effort, not the friction of fixing buggy output. — [[simonwillison-vibe-coding-agentic-engineering-2026-05]]

## Resources
- [[karpathy-vibe-coding-agentic-engineering]] — PRIMARY SOURCE: Karpathy introduces and distinguishes this framing at AI Ascent 2026
- [[reddit-karpathy-moved-on-from-vibe-coding]] — third-party practitioner popularization (May 2026); adds 4-step workflow, three failure modes, and "cognitive debt" coinage
- [[benln-x-karpathy-agentic-engineering-2026-05]] — X comment thread (May 2026); practitioner reactions: cost-of-being-wrong economics, term adoption as hiring vocabulary, organizational harness 7-point framework
- [[simonwillison-vibe-coding-agentic-engineering-2026-05]] — Simon Willison on the practitioner-discipline-erosion convergence (May 2026)
- [[naval-ravikant-saas-is-next]] — Naval's investor framing of the solo-operator outcome; "pure software is uninvestable"
- [[chamath-decision-context-agents]] — Chamath on decision-context capture as the missing layer for team AI leverage
