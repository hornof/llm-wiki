---
title: "How to Design an Agent Harness: six decisions that turn a model into a worker you can leave alone"
type: source
medium: twitter-thread
url: https://x.com/undefinedKi/status/2088611136027361368
published: 2026-08-15
ingested: 2026-10-04
---

## Summary

**The most systematic treatment of the harness layer the wiki holds**, and a **backfill** — published **2026-08-15**, seven weeks before it reached `_raw`, during which [[loop-engineering]] accumulated most of the same conclusions one source at a time.

It decomposes the harness into six decisions, three of which the vendor owns and three of which you do, and attaches a number to most of them. The framing:

> *"A better model fixes none of it. All of that lives in the software wrapped around the model: what it gets told, what it keeps, what it's allowed to touch, and who checks the result. **That wrapper is the harness. You already have one. The only question is whether anyone designed it.**"*

And the naming history, which matters for the wiki's own vocabulary: *"People started calling this layer 'the harness' in early 2026. Before that it had no agreed name, **which is most of why it went unmanaged for so long**."*

## Three shapes, with receipts

| Org | Shape | Numbers |
|---|---|---|
| **DoorDash** | **Platform** — each agent in a throwaway VM pre-booted with repos, tools and credentials; work written as **YAML playbooks mixing agent steps with scripted steps**; everything reaching an internal system goes through **one gateway** that hands out only the tools a playbook declared and logs every call | **130,000 automated tasks in one month**, including **25,000+ code reviews a week** |
| **OpenAI** | **Repository** — no platform. The repo *is* the harness: instructions file kept to **~100 lines** as a table of contents into a real docs folder; **architectural rules enforced by custom linters instead of prose the model can skip** | **Three engineers merged ~1,500 PRs in five months** |
| **Anthropic** | **Role split** — three agents: one turns a sentence into a spec, one implements, one **drives the finished app in a browser and grades it**. They communicate **only by writing files to each other** | **6 hours and $200**, against **20 minutes and $9** unharnessed |

> *"Over twenty times the price for a much better result, **which is the trade nobody advertises.**"*

## The six decisions

### 1. The loop, and where it stops

- **Write the stopping rule in one sentence, before you start.** *"Done means the test suite passes and the app boots."* Not *"done means the agent says it's done, which is what you have right now by default."*
- **Decide what happens on a bad ending** — restart with a note, or freeze and wait. *"Having no answer means the agent silently invents its own."*
- **Hard cap on turns or wall-clock.** *"An agent that has taken forty passes at the same file is not going to fix it on the forty-first."*
- **Log every turn** if unattended.

> **Someone audited fifty published agent loops by hand: only 74% even stated what counted as finished, and only 32% kept any memory between runs.** *"This is the cheapest fix on the list and the one most often skipped."*

### 2. The tools it can see

- **Stop loading every tool up front.** Connected MCP servers stuff every tool description into context every turn. Fix: tools on disk as files, agent opens only what it needs. **Anthropic's worked version: 150,000 tokens down to 2,000.**
- **Rewrite what errors say.** *"Invalid request"* tells the model nothing, so it guesses. Return structure: which field, what a valid value looks like, what to try next. **Siemens measured a 37–40 point jump in task completion at roughly half the tokens per success.**
- **Cut the menu.** Remove anything unused in a month. *"Two tools with confusingly similar names cost you more than a missing tool does."*
- Naming and grouping *"measurably changes behaviour. Prefixes and suffixes are not cosmetic."*

### 3. What stays in memory

- **Don't fill it.** On a million-token model, *"work up to 300,000 or 400,000 and then stop. Past that the failures stop looking like confusion and start looking like carelessness, the kind where it deletes a config file it should have left alone."*
- **Trim on purpose**, in stages — research → doc → plan → implementation, each stage starting clean with only the previous stage's document. *"Slower, and much more reliable."*
- **Pin the rules.** *"Facts can be summarised away. Rules cannot."* Re-read after every reset **and** repeat in the system prompt — *"belt and braces, deliberately."*
- **Restart when it starts agreeing with you.** *"If the model has accepted five suggestions in a row without pushback, the session is done. Something wrong got in early and everything after treats it as established fact."*

> **Policy-rule violations: 0% with the rule in full view → 30% after compaction → 59% on the worst model. Where the rule survived summarising, violations stayed at zero.** The essay flags its own source: *"a single author and unreviewed, so treat the number as a strong hint rather than a fact. The fix costs an afternoon either way."*

### 4. What survives a crash

**Four files, kept current by the agent:**

| File | Rule |
|---|---|
| **SPEC.md** | What you're building. **You write it, the agent never edits it.** Stops the target drifting. |
| **PLAN.md** | Steps with plain acceptance criteria. Not *"improve error handling"* but *"requests to /orders with a missing id return 400 with a message, and the test asserting this passes."* |
| **PROGRESS.md** | Finished, next, tried-and-failed. *"The file a fresh agent reads first."* |
| **DECISIONS.md** | **Append-only.** *"Without it a later session re-litigates a decision you already made two hours ago."* |

Plus: **commit after every change that works.** *"Rollback becomes `git revert`, review becomes reading diffs, and you get a full history for free instead of building a checkpoint system."*

> *"If it isn't in a file, it doesn't exist."*

### 5. What it's allowed to touch

> *"An agent running on your laptop has your SSH keys, your VPN session, and every CLI you're logged into. It doesn't need to be malicious for that to end badly. **It needs one poisoned web page in its context.**"*

- **Two boundaries, at the OS level** — writable directories, and network through a proxy with an allowlist. **At the OS level so anything it spawns is covered**: *"an agent that shells out to a script that shells out to curl has escaped an in-app restriction and has not escaped this one."*
- **Stop trusting approval prompts. People approve 93% of them.** *"A prompt you always click through is not a security control, it's a delay you built for yourself."*
- **One gateway** in front of shared systems, handing out only declared tools and logging every call. *"That log is what makes an incident investigable instead of mysterious."*
- **Never put long-lived credentials in the sandbox.** *"If the agent can read a key, assume the key is in a context window somewhere."*

> **Anthropic reported sandboxing cut permission prompts by 84% internally.** *"That's the real argument: it isn't only safer, it's much less annoying, which is why it actually sticks."*

### 6. Who says it's done

> *"The agent that wrote the code is the worst available judge of whether the code works. It graded itself, and it grades generously."*

- **Review in a separate session.** *"The same model is fine. What matters is that it isn't carrying the reasoning that produced the bug."*
- **Make it actually run the thing.** *"Reading a diff and pronouncing it correct is not verification, it's a second opinion on the same guess."*
- **Build an eval set out of failures you've already had.** Twenty to fifty real tasks from your own repo.
- **Run every task three times and judge the worst run.** *"A 75% success rate per attempt means all three attempts pass only 42% of the time. A single green run tells you almost nothing."*
- **Watch for the confident wrong answer.** *"The characteristic agent failure is not a crash. It's hitting an error and writing a fluent paragraph about why it doesn't matter."* **In one production study, around 70% of these were caught by a human noticing, not by any test.** Suggested detection: *"grep your logs for explanation-shaped text near error handling."*

**And an honest gap:** *"There is no published data on retry policy… Everyone has an opinion, nobody has numbers. If you find yourself tuning this for days, know that you're in genuinely unmapped territory."*

## The weekend version

1. **One instructions file, under a hundred lines** — a table of contents, not an encyclopedia. *"Long instruction files get skimmed exactly like long emails."*
2. **Anything broken twice becomes a linter.** *"Not a paragraph of prose asking nicely. A rule that fails the build. Add one when you've seen a real failure; delete it when a better model has made it pointless."*
3. **The four files**, plus a commit after every working change.
4. **Pin the rules** that must never be summarised away.
5. **Twenty tasks, three runs each, judged on the worst one.**

## Judgment

**This is the document [[loop-engineering]] has been assembling one source at a time, and it predates most of that page's entries.** It was published 2026-08-15 and reached the wiki 2026-10-03 — **seven weeks during which the wiki independently arrived at the same conclusions from Isenberg, Anthropic's eval post, croovies, Rauch and others.** That convergence is evidence the conclusions are right; the gap is a sourcing failure worth noting.

**Three things here are genuinely new to the wiki.**

**"Restart when it starts agreeing with you"** is the sharpest heuristic in the piece and the wiki has nothing like it. Five accepted suggestions in a row as a signal that *something wrong got in early* names a failure mode — context poisoning that looks like cooperation — which is otherwise invisible precisely because it feels like progress.

**"Anything broken twice becomes a linter"** is the hardest form of the accretion rule the wiki holds in softer versions. [[gregisenberg-ai-roll-ups-5t-guide-2026-09-26|Isenberg's]] corrections-become-test-cases is the same instinct; **OpenAI enforcing architectural rules by linter rather than prose is the same instinct with the escape hatch removed.** A rule that fails the build cannot be skimmed.

**"Run three times, judge the worst"** supplies arithmetic the wiki has been missing. **75% per attempt means 42% across three** — which quietly invalidates most single-run demos the wiki has catalogued, including several it recorded without comment.

**The cost disclosure is the most valuable paragraph and the least quoted.** *"A harness earns its keep on work you couldn't hand off at all, and never on work where you were trying to save twenty minutes."* **Anthropic's own harnessed run cost >20× the unharnessed one** — and the wiki holds a great many harness claims with no price attached at all. This is the first source that states the trade as a trade.

**Caveats.** An X long-form post by a pseudonymous author, citing studies that are mostly **not linked or named** — the fifty-loop audit, the Siemens measurement, the production study on confident-wrong-answers and the 93% approval figure all arrive without references. **The essay flags one of its own sources as single-author and unreviewed, which is more rigour than it shows for the others.** Treat the numbers as directional. The three org receipts (DoorDash, OpenAI, Anthropic) are also secondhand and uncited here.

## Pages Updated

- [[loop-engineering]]
- [[domain-specific-harness]]
- [[ai-vulnerability-discovery]]
- [[claude-md-pattern]]
