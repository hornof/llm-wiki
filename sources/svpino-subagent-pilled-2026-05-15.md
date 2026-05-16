---
title: "svpino: 'Everything that can be a subagent should be a subagent'"
type: source
medium: twitter-thread
url: https://x.com/svpino/status/2055264566934978959
ingested: 2026-05-16
---

## Summary

Santiago Valdarrama (@svpino) X post May 15 2026 declaring himself **"subagent-pilled with Claude Code"**: *"This is the biggest update I've made in the way I work over the last 2 weeks: 'Everything that can be a subagent should be a subagent.'"* Three named advantages — separate context windows, per-subagent model selection, per-subagent tool configuration — followed by a substantive comment thread where multiple practitioners push back on the "everything-as-subagent" framing and name the coordination tax it introduces. svpino himself replies *"Yeah, a little bit. I think I'm overindexing on using them now, but I'm sure I'll find the proper balance with time and experience."*

## Key Claims / Takeaways

### svpino's three named advantages

1. **Separate context windows** — subagents run in their own context, so parallel execution doesn't pollute the parent session.
2. **Per-subagent model selection** — Haiku for fast/cheap, Sonnet for default, Opus for hard. (Cross-references the Zephyr [[zephyr-7-claude-setups-2026-05-15|7-setups]] "model routing default" framing from the same week.)
3. **Per-subagent tool configuration** — restrict each subagent to the tools it actually needs; reduces accidental scope.

### The comment-thread payload (where the substance is)

Multiple convergent counter-takes name the **coordination tax** as the binding constraint on aggressive subagent-everything decomposition:

- **Jason Haugh (@jason_haugh)**: *"Past three or four agents the cost shifts to coordination. Who hands off to whom, where state lives, what wakes what. Different tools per agent helps but eventually you want a queue or a chief-of-staff layer between them. Subagent-pilled doesn't cover that yet."* — Names the four-agent threshold where coordination cost overtakes per-agent gains; calls for a chief-of-staff orchestration layer.
- **Prompt Assay (@PromptAssay)**: *"I've found subagent decomposition works cleanly until the tasks need shared mutable state. Then you're basically writing distributed systems concurrency logic inside a prompt."* — Names the **shared-mutable-state boundary** as the natural ceiling on subagent-everything decomposition.
- **Yann Kronberg (@zazmic_inc)**: *"Separate context windows, different models per task, clean tool isolation: the microservices parallel is right IMO. And like microservices, the orchestration complexity is the part that catches up with you."* — Microservices analogy: the same operational-cost arc.
- **Agentic Glacius (@temhandev)**: *"The frame for me: subagent when its output stands alone as evidence. Inline when the reasoning IS the evidence. Subagent-everything works until your audit trail is just 'subagent #4 said so.'"* — Names the **audit-trail collapse** failure mode: if every reasoning step is delegated to a subagent, the parent loses the *evidence* of how a conclusion was reached.
- **Gergely Kovács (@zfyl)**: *"the problem is evaluation! nobody evaluates the sub-agents. and nobody will evaluate the work of the sub-sub-agents ever. might be 100% self fulfilling slop to fix slop"* — Names the **evaluation gap** — subagents are not eval'd; sub-subagents will never be.
- **clifcode (@clifcode)**: *"'everything that can be a subagent should be a subagent' feels like the ai version of microservices"* — svpino replies "Yeah, a little bit." — confirming the analogy and the same "overindexing now, will find balance later" arc microservices went through ~2015–2018.

## Why It Matters

- **First wiki capture of the "subagent-pilled" framing** as a discrete agentic-engineering posture. svpino's "everything that can be a subagent should be a subagent" is the maximal-decomposition end of the multi-agent design space; the comment thread names the failure modes (coordination tax, shared-state boundary, audit-trail collapse, evaluation gap).
- **Microservices analogy is load-bearing** — three independent commenters land on it. The "subagent-everything works until orchestration overhead catches up" arc parallels the microservices-renaissance-and-correction of the 2015–2020 era. Worth tracking as a structural pattern: practitioners will overindex on decomposition, hit the coordination wall, and pull back to a small number of well-scoped subagents with explicit hand-off contracts. The same shape as the Khairallah / sairahul1 "specialist team" pattern landing where it lands.
- **The audit-trail-collapse framing (@temhandev) is novel and worth elevating**: *"subagent when its output stands alone as evidence; inline when the reasoning IS the evidence."* This is a useful design rule, not just a critique. Pairs with [[verifiability-and-jagged-intelligence]] — subagent decomposition shifts what's verifiable.

## Caveats

- **svpino is overindexing and says so**. The headline framing ("everything that can be a subagent should be a subagent") is explicitly walked back in svpino's own reply to the microservices analogy. Capture as a practitioner's *current posture*, not a settled position.
- **No quantitative benchmark** for when subagent decomposition stops paying off. The four-agent threshold (Jason Haugh) is a practitioner-anecdote, not a measurement.

## Cross-references

- [[svpino]] — entity page; "subagent-pilled" framing added under Notable Takes.
- [[claude-code]] — subagents are Claude Code primitives; advantages are Claude-Code-specific.
- [[agentic-ai]] — multi-agent-orchestration design space; svpino's posture is the maximal-decomposition end; the comment thread surfaces the natural ceiling.
- [[sairahul1-solo-founder-13-agent-playbook-2026-05-15]] / [[eng-khairallah-multi-agent-team-course-2026-05-15]] / [[av1dlive-cursor-1m-agent-orchestrator-2026-05-15]] — same-week multi-agent practitioner cluster.
- [[verifiability-and-jagged-intelligence]] — the audit-trail-collapse framing is a new verifiability anchor.

## Pages Updated

- [[svpino]] (updated — subagent-pilled take + "everything that can be a subagent should be a subagent" + same-week walk-back added under Notable Takes; date bumped to 2026-05-16)
- [[agentic-ai]] (updated — "Subagent-Pilled Posture and Its Natural Ceiling (svpino + thread, May 2026)" section added with the four-agent coordination-tax threshold, shared-mutable-state boundary, and audit-trail-collapse framing; date bumped to 2026-05-16)
