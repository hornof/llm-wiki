---
name: Vibe Coding
type: concept
maturity: emerging
last_updated: 2026-04-29
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

## Related Concepts
- [[agentic-engineering]] — the professional counterpart
- [[software-3-0]] — the broader paradigm; vibe coding is one manifestation
- [[verifiability-and-jagged-intelligence]] — explains why vibe coding works better in some domains than others

## Resources
- [[karpathy-vibe-coding-agentic-engineering]] — Karpathy's own description at AI Ascent 2026; coined the term, now contextualizes it relative to agentic engineering
