---
name: Vibe Coding
type: concept
maturity: emerging
last_updated: 2026-05-06
---

## Definition
Term coined by Andrej Karpathy (early 2025) for the practice of building software by directing an AI coding agent through natural language — accepting its output without closely reviewing the generated code, iterating on vibes and observed behavior rather than explicit code review.

> "Vibe coding is about raising the floor for everyone in terms of what they can do in software." — Andrej Karpathy, AI Ascent 2026

## Why It Matters
Vibe coding democratizes software creation. Anyone can build working applications without deep programming knowledge by directing an agent and iterating on results. This represents a floor raise — more people can ship more things.

## Relationship to Agentic Engineering
Karpathy explicitly distinguishes vibe coding from [[agentic-engineering]]:

| | Vibe Coding | Agentic Engineering |
|---|---|---|
| **Goal** | Raise the floor for everyone | Preserve the quality bar of professional software |
| **Audience** | Hobbyists, non-engineers, fast prototyping | Professional engineers |
| **Code review** | Minimal / none | Engineer remains accountable |
| **Responsibility** | Low stakes | Full professional responsibility |
| **Speedup** | High | Very high (>10x) |

The two are not in conflict — vibe coding is the entry point; agentic engineering is the professional discipline built on top.

## December 2025 Inflection Point
Karpathy notes that December 2025 was when vibe coding became reliably effective for him — models stopped needing correction on chunks of code, and he started trusting the system end-to-end. Many practitioners report the same shift around this period. — [[karpathy-vibe-coding-agentic-engineering]]

## Limitations
- Vibe-coded software is not held to professional security or reliability standards.
- Agents still make architectural mistakes without human oversight (e.g., using email addresses as cross-system user IDs instead of a persistent user ID).
- Generated code can be "bloaty" with copy-paste and brittle abstractions — aesthetics and simplicity require human judgment.

## Why It Breaks at Scale (Three Failure Modes)
A May 2026 r/AIAgentsInAction popularization names the failure modes that kill vibe coding in production work — useful sharper articulation of the limits above:

1. **Security holes compound.** An agent writing 1,000 PRs/week at a 1% vulnerability rate ships ~10 new vulnerabilities per week. Vibe coding has no gate for this because the human isn't reading what gets merged.
2. **Architecture rots.** Skipping design means months later nobody can explain why the codebase is shaped the way it is — no reasoning to follow because no reasoning happened.
3. **Context collapses.** Long sessions degrade; the agent loses track of earlier decisions, code contradicts itself, the developer never catches it.

The accumulated cost of all three is **cognitive debt** — the price of poor agent management, lost context, and unreliable behavior. — [[reddit-karpathy-moved-on-from-vibe-coding]]

## Propagation Signal (May 2026)
Karpathy's vibe-coding/agentic-engineering distinction is propagating into practitioner subreddits within ~5 weeks of the AI Ascent talk. But comments on the r/AIAgentsInAction popularization show a sharp split: the *concepts* are spreading, but AI-formatted summaries are getting rejected as "slop" — practitioner antibodies against LLM-written advice posts even when the framing they carry is sound. The signal is two-sided: distinction is catching on; second-hand explainers are not. — [[reddit-karpathy-moved-on-from-vibe-coding]]

## Convergence Pressure (Simon Willison, May 2026)
[[simon-willison]] (long-tracked, high-signal practitioner voice — creator of Datasette, co-creator of Django) reports in a May 6 2026 blog post that the line distinguishing vibe coding from [[agentic-engineering]] is collapsing in his own practice as agents become more reliable: "The problem is that as the coding agents get more reliable, I'm not reviewing every line of code that they write anymore, even for my production level stuff." He frames this as uncomfortable, not triumphant — he wants higher quality, not less review.

This is not a claim that the two modes are equivalent. It is a report that the *practitioner discipline* keeping ceiling-side work out of vibe-coding territory is harder to maintain. The two-mode framing remains analytically useful; the practitioner needs to *actively* preserve the review discipline rather than rely on the agent's unreliability to enforce it. — [[simonwillison-vibe-coding-agentic-engineering-2026-05]]

## Related Concepts
- [[agentic-engineering]] — the professional counterpart
- [[vibe-physics]] — the same coined-by-analogy pattern extended into theoretical physics by [[alex-lupsasca]]; demonstrates "vibe X" propagating into adjacent disciplines
- [[software-3-0]] — the broader paradigm; vibe coding is one manifestation
- [[verifiability-and-jagged-intelligence]] — explains why vibe coding works better in some domains than others

## Resources
- [[karpathy-vibe-coding-agentic-engineering]] — Karpathy's own description at AI Ascent 2026; coined the term, now contextualizes it relative to agentic engineering
- [[reddit-karpathy-moved-on-from-vibe-coding]] — third-party Reddit popularization (May 2026); adds the cognitive-debt coinage and three-failure-mode framing
- [[simonwillison-vibe-coding-agentic-engineering-2026-05]] — Simon Willison reports practitioner-discipline-erosion (May 2026)
