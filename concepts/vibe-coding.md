---
name: Vibe Coding
type: concept
maturity: emerging
last_updated: 2026-10-29
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

## Five months on: all three failure modes acquired evidence (2026-05 → 2026-10)

**The three failure modes above were a May 2026 prediction. Each one has since been measured, named, or given a countermeasure** — which makes this the rare case where a page's own framework can be scored rather than restated.

### 1. "Security holes compound" — confirmed, with the cost landing on the defender

The May estimate was *"an agent writing 1,000 PRs/week at a 1% vulnerability rate ships ~10 new vulnerabilities per week."* **The order of magnitude turned out right and the economics turned out worse.**

- **DoorDash runs 25,000+ agent code reviews a week** ([[undefinedki-how-to-design-an-agent-harness-2026-08-15]]) — so the thousand-PR scenario is now an understatement of real volume at one company.
- **[[claude-mythos|Mythos]] findings sent Bank of America to 1,000 contractors** ([[dailybrief-roundup-2026-10-15]]). **The discovery is cheap and the remediation is not.**
- **36% of OpenAI's own security discoveries were duplicates** ([[willison-openai-devday-2026-live-blog-2026-09-29]]) — so a meaningful share of that queue is triage rather than fixing.

**The countermeasure also exists now, and it is not "read the diffs."** `codex-security patch` opens PRs at a **1% rollback rate**, credited to a `verify-fix` step that **replays the original attack**. **That works because the finding arrives with a reproduction** — which is precisely what vibe-coded work does *not* produce for its own defects. See [[ai-vulnerability-discovery]].

### 2. "Architecture rots" — now has a name, a diagnosis and a tool

**The failure mode is called *architectural drift*, and the diagnosis is observability rather than capability** ([[raw-batch-roundup-2026-10-14]]):

> *"With agents doing most of the coding, we need a way to judge the architectural trade-offs they are introducing with each change — however **models are not great at surfacing what architectural changes they have made, especially at scale.**"*

**That is sharper than "nobody can explain why the codebase is shaped the way it is."** The reason nobody can explain it is that **each individual change passes review while the aggregate effect is invisible** — no gate on [[loop-engineering]] catches locally-correct code that degrades structure. The response is determinism: **architecture diagrams built from the actual control-flow graph, so the artifact can be diffed** where a model's summary cannot.

**And the best answer in that thread is the one this page should carry**: *"AI tends to generate much better output when the AI can **ingest an architecture decision record**. A good ADR explains the **goal and reasoning**."* **An append-only decision log is `DECISIONS.md` from the [[undefinedki-how-to-design-an-agent-harness-2026-08-15|four files]], arrived at independently by the architecture community** — and it is the direct antidote to *"no reasoning to follow because no reasoning happened."*

### 3. "Context collapses" — measured, and worse than described

**This is the failure mode that has gained the most, and the numbers are specific:**

| Finding | Figure |
|---|---|
| **Policy-rule violations after context compaction** | **0% with the rule in view → 30% after compaction → 59% on the worst model** |
| Where the rule survived summarising | **violations stayed at 0%** |
| Usable context before quality degrades, on a 1M-token model | **~300–400K**, past which *"failures stop looking like confusion and start looking like carelessness"* |

> **The compaction finding is the mechanism behind "the agent loses track of earlier decisions."** It is not drift — **the rules are deleted and replaced by a summary of the rules, and nothing announces it.** A session that has compacted once is operating under a paraphrase. **Pinning fixed it completely**, which makes this the one failure mode on this page with a clean fix: separate facts from rules, and re-read the rules after every reset.

**And one behavioural signal this page lacked entirely**: *"**Restart when it starts agreeing with you.** If the model has accepted five suggestions in a row without pushback, the session is done. Something wrong got in early and everything after treats it as established fact."* **Context collapse that presents as cooperation is invisible precisely because it feels like progress.**

### What this does to the two-mode framing

**It survives, and the boundary is now describable in one sentence.** The failure modes are not about code quality — **all three are about the absence of a durable artifact**: no reproduction for the defect, no decision record for the architecture, no pinned rule surviving compaction. **[[agentic-engineering]] is vibe coding plus artifacts that outlive the session**, and every countermeasure above is a file: a replayable test, an ADR, a pinned rule file. **The [[undefinedki-how-to-design-an-agent-harness-2026-08-15|harness essay's]] rule is the compressed form — *"if it isn't in a file, it doesn't exist."***

## Games cross the line Willison drew for code (2026-10-28)

[[willison-vibe-game-development-2026-10-28]]: [[simon-willison]] calls October 2026 an inflection point for vibe-coding games, matching their November 2025 call for coding agents. They built four browser games with Claude Opus 5.5 without reading the code, one of them in a single prompt. **Their criterion is whether the game is fun to play, not whether it runs.** Fun is a quality bar that tests can't check, so this is a domain where vibe coding works because the human checks the result by playing it. That fits the two-mode framing above, where the durable artifact here is the playable game. Their note on where effort goes now: *"The new challenge is coming up with concepts"*.

**The next day, a whole studio run this way** ([[willison-spawn-autonomous-game-dev-2026-10-29]]). Spawn's agents change live code and ship hourly, and about 60% of their work starts from production errors and bug reports. Willison's caveat holds for this too: it works for a game, where a broken change costs little and rolls back in 30 seconds.

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
