---
title: "How to Build Your First Team of AI Agents Using Claude Opus 5.5"
type: source
medium: article
url: https://x.com/undefinedKi
published: 2026-10-07
ingested: 2026-10-08
local_source: "_raw/How to Build Your First Team of AI Agents Using Claude Opus 5.5.md"
---

## Summary

An 11-step course on building agent teams with the **Claude Agent SDK**, built around a result the author says was buried in **Anthropic's Opus 5.5 prompting guide**:

> *"When Anthropic gave a team of agents **an elapsed-time budget**, the team kept answer quality **comparable to a single agent's** while finishing **considerably sooner**."*

**It is also the second substantive surface for [[claude-opus-5-5|Opus 5.5]]**, carrying the specs the 2026-09-22 launch note lacked.

## Opus 5.5 specs, as relayed

- **66.4% on Terminal-Bench 4.0**, against **55.8% for the far larger Claude Fable 5.1**
- **~40% cheaper than Opus 5** on typical workloads
- One early tester *"completed a **680,000-line code migration** with it in less than a day"*
- **Effort as a per-role dial**, and a documented elapsed-time budget for teams

**All relayed from Anthropic's prompting guide, which was not fetched.**

## The architecture

**Three roles, and the third is the one the author says everyone skips:**

- **The orchestrator** — receives the goal, splits it, assigns, assembles. *"It plans and integrates. It does not do the deep work itself. In a well-built team, **it is the only agent you talk to.**"*
- **The specialists** — one narrow job each. *"The narrower the role, the better the output, because a focused instruction beats a vague one every time."*
- **The critic** — *"the role almost everyone skips and the one that separates professional systems from demos… **A team without a critic produces fast, confident garbage.** A team with one produces work you can ship."*

**The first rule is not to build a team at all:**

> *"A team adds coordination overhead, more API calls, more tokens, and new ways to fail. **If your task is one job with one clear way to check it, a single well-prompted agent will beat a team every time, faster and cheaper.**"*

Three conditions that justify one: the job **splits into independent pieces**, a subtask would **flood the main context with material nobody needs afterward**, or part of the work **needs different expertise or different permissions.** *"If none of those apply, close this tab and build a single agent."*

## The eight mistakes

1. **Building five agents before one works.** *"Earn every new agent. One excellent orchestrator beats five mediocre agents wired together."*
2. **Vague descriptions.** *"The orchestrator routes by description. 'Helps with research' routes nothing reliably. 'Gathers and verifies facts on one focused question' routes correctly."*
3. **Thin handoffs.** *"Subagents see only the delegation message. If the brief says 'write it up,' the writer has nothing to write from."*
4. **No critic.** *"Parallel speed without review just produces wrong answers faster."*
5. **Full permissions everywhere.** *"Every tool a role does not need is a mistake it can now make."*
6. **No spending cap.** *"**The default is unlimited.** Set `max_budget_usd` before your first run."*
7. **Trusting the advisory clock.** *"The elapsed-time budget **paces** the team. Your own timeout **stops** it."*
8. **Letting the team act irreversibly.** *"Drafting an email is delegation. Sending it is your decision. Keep anything that cannot be undone — sending, publishing, spending, deleting — behind a human approval step."*

## Judgment

**The elapsed-time-budget result is the genuinely interesting claim, and it is the one least supported here.** *Same quality, considerably sooner* is a real finding if it holds — it says coordination overhead can be paid for in tokens rather than in quality, which is the opposite of what the wiki's agent-team record suggests (Anthropic's own three-agent harness cost **20× more** for a better result). **But it reaches the wiki through a course author's reading of a prompting guide nobody fetched, with no numbers.** Flagged as the fetch item.

**"Most tasks do not need a team" is the best thing in it** and it inverts the genre. Every multi-agent artifact the wiki holds argues *for* the architecture; this one opens by arguing against it and gives three testable conditions. **It is also the only source on [[ai-native-organizations]]'s one-agent-or-ten axis that supplies a decision rule rather than a preference.**

**"The default is unlimited" belongs on the record permanently.** [[simon-willison|Willison's]] hard-caps argument and [[pachaar-llm-routing-can-cost-more-2026-09-06|Uber's vanished annual budget]] are both about this exact fact. **A spend cap that must be opted into is the same design defect as an approval prompt people click through 93% of the time** — the safe setting is not the default one.

**The mistakes list is better than the course.** *"Every tool a role does not need is a mistake it can now make"* is the least-permission principle in one line; *"the orchestrator routes by description"* is the same finding as [[pachaar-llm-routing-can-cost-more-2026-09-06|routing intent living in the description]]; and **the advisory-versus-enforcing clock distinction** is the harness essay's hard-cap advice restated with the trap named — **a budget that paces is not a budget that stops.**

**And the closing admission is the honest part:** *"A team of agents will not fix a process you do not understand… If you cannot describe how a task should be done step by step, you cannot delegate it to five agents any better than to one. The code in this course takes an afternoon. **The clear thinking about your own process is the real work.**"* That is the same conclusion as the [[forward-deployed-engineer|FDE's]] *"the real process is almost always 3× longer than the one on paper."*

**Caveats.** A commercial course, promoted on X, by the same author as the [[undefinedki-how-to-design-an-agent-harness-2026-08-15|harness essay]] — **so this is a second artifact from a source whose first one was excellent but whose studies went unlinked.** Same pattern here: the Anthropic prompting-guide result, the Terminal-Bench numbers and the 680,000-line migration all arrive **without links**. **The architecture advice stands on its own reasoning; the numbers need the primary.**

## Pages Updated

- [[claude-opus-5-5]] (new)
- [[loop-engineering]]
- [[ai-native-organizations]]
