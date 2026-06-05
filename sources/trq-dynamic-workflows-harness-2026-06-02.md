---
title: "Thariq Shihipar — A harness for every task: dynamic workflows in Claude Code (2026-06-02)"
type: source
medium: blog-post
url: https://claude.com/blog/a-harness-for-every-task-dynamic-workflows-in-claude-code
ingested: 2026-06-05
---

## Summary

[[thariq-shihipar|Thariq Shihipar]] (Anthropic Claude Code team; @trq212) publishes (2026-06-02 via X, [also on Claude Blog](https://claude.com/blog/a-harness-for-every-task-dynamic-workflows-in-claude-code)) **practitioner-narrative companion to the [[anthropic-dynamic-workflows-official-docs-2026-06|canonical Dynamic Workflows docs]]**. **First wiki-captured 3-failure-mode framework** (agentic laziness / self-preferential bias / goal drift) **+ first wiki-captured 6-pattern composable workflow-library** (classify-and-act / fan-out-and-synthesize / adversarial verification / generate-and-filter / tournament / loop-until-done) **+ 8 use-case categories**. **3rd wiki Thariq Shihipar surface** (1st: [[willison-html-effectiveness-2026-05|HTML output framing]]; 2nd: [[trq-suzanne-learn-quiz-2026-06-01|Suzanne's Learn Quiz]]; 3rd: this Dynamic Workflows harness articulation) — **establishes Thariq as the Anthropic-internal practitioner-content voice for the Claude Code agent-architecture surface**.

## Key Claims / Takeaways

### Thesis: workflows are *harnesses written on the fly*

> *"Claude can now write its own harness on the fly, custom-built for the task at hand. While the default Claude Code harness is built for coding, it is also useful for many other types of tasks because, as it turns out, many tasks resemble coding tasks. But there are certain classes of tasks where we have had to build custom harnesses on top of Claude Code to achieve peak performance such as Research, security analysis, agent teams, or Code Review. Workflows allow you to dynamically create harnesses that enable Claude to solve all of those problems and more natively inside of Claude Code."*

**Pattern**: Dynamic Workflows are *the meta-primitive* — they let Claude *write its own Claude Code harness* per task instead of relying on the default coding-tuned harness or hand-built custom harnesses (Research / security analysis / agent teams / Code Review). **First wiki-captured Anthropic-internal articulation of *harness-as-product-tier-primitive***.

### The 3 failure modes Dynamic Workflows solve

Thariq's framework for *why* workflows exist — three failure modes the default single-context-window Claude Code harness exhibits on long-running / massively-parallel / structured-adversarial tasks:

| Failure mode | Definition |
|---|---|
| **Agentic laziness** | *"Claude stops before finishing a particularly complex, multi-part task and declares the job done after partial progress, for example addressing 20 of the 50 items in a security review."* |
| **Self-preferential bias** | *"Claude's tendency to prefer its own results or findings, especially when asked to verify or judge them against a rubric."* |
| **Goal drift** | *"The gradual loss of fidelity to the original objective across many turns, especially after compaction. Each summarization step is lossy, and details like edge-case requirements or 'don't do X' constraints can get lost."* |

**First wiki-captured 3-failure-mode framework for context-window-bounded agent attention** at the frontier-vendor articulation tier. Pairs structurally with:
- [[nateherk-opus-4-8-aios-2026-05-29|Nate Herk's 150,000-inbox concrete-incident lesson]] on instructions-vs-capabilities — Nate Herk's lesson is the operator-side instantiation of *agentic laziness* (asking Claude not to do something doesn't reliably work; constrain by capabilities instead)
- [[trq-suzanne-learn-quiz-2026-06-01|Suzanne's Learn Quiz]] — operator-side answer to *goal drift* (verify operator-side comprehension before context-clears)
- [[claude-md-pattern|CLAUDE.md pattern]] — operator-side answer to *self-preferential bias* (explicit rules that don't depend on the model self-judging)

**First wiki-captured 3-vector mapping** from failure-mode → practitioner-side discipline-pattern.

### The 6 composable workflow-patterns — first wiki-captured Anthropic-canonical catalog

| Pattern | Shape |
|---|---|
| **Classify-and-act** | Classifier agent decides task type, routes to different agents/behavior; or classifier at end determines output |
| **Fan-out-and-synthesize** | Split task into many smaller steps, run agent on each, then synthesize results. Synthesize step is a barrier — waits for all fan-out agents, merges structured outputs into one result |
| **Adversarial verification** | For each spawned agent, run a separate spawned agent to adversarially verify its output against rubric/criteria |
| **Generate-and-filter** | Generate N ideas on topic, filter by rubric or verification, dedupe, return highest-quality tested ideas |
| **Tournament** | Instead of dividing work, agents compete. Spawn N agents attempting same task different approaches; pairwise judging agent picks winner |
| **Loop-until-done** | For tasks with unknown work amount, loop spawning agents until stop condition met (no new findings, no more errors) instead of fixed number of passes |

**First wiki-captured Anthropic-canonical composable workflow-pattern library**. Pairs structurally with [[rody-5-subagent-templates-2026-05-31|@0x_rody's 5 standalone subagent templates]] — *Rody's templates are individual-worker primitives; Thariq's patterns are orchestration-level primitives*. **First wiki-captured complete 2-tier composability stack**: individual-worker templates ([[zodchii-4-agent-pipeline-2026-05-30|zodchii's 4-agent pipeline]] + Rody's 5 standalone) + orchestration-level patterns (Thariq's 6 composable).

### 8+ use cases — practitioner pedagogy

The post enumerates use cases by category. Each maps to one or more of the 6 patterns:

1. **Migrations and refactors** — Thariq explicitly cites *"[[bun|Bun]] was rewritten from Zig to Rust using workflows"* (references [Jarred Sumner's thread](https://x.com/jarredsumner/status/2060050578026189172)). Pattern: per-callsite worktree fan-out + adversarial review + merge. **First wiki-captured Bun Zig→Rust attribution to Dynamic Workflows specifically** — extends prior wiki coverage in [[anthropic-dynamic-workflows-primary-2026-05-28]] with practitioner-side validation.
2. **Deep research** — `/deep-research` skill uses Dynamic Workflows (fan-out web searches + fetch sources + adversarially verify claims + synthesize cited report). Generalizes to Slack-context research or codebase exploration.
3. **Deep verification** — fact-check every claim in a report by spinning off subagents to verify each one in-detail; verification agent checks the source subagent for quality.
4. **Sorting** — qualitative-judgment sorting (e.g., support tickets by bug severity) on 1000+ rows; tournament / pairwise-comparison pipeline ("comparative judgment is more reliable than absolute scoring") with deterministic loop holding the bracket.
5. **Memory and rule adherence** — workflow with verifier-per-rule for CLAUDE.md rules Claude struggles with; skeptic persona reduces false positives. **Reverse direction**: *"mine your recent sessions and code review comments for corrections you keep making, cluster them with parallel agents, adversarially verify each candidate (would this rule have prevented a real mistake?), and then distill the survivors back into a CLAUDE.md."* **First wiki-captured Anthropic-side CLAUDE.md-mining workflow primitive** — pairs with [[claude-md-pattern|CLAUDE.md pattern]] as the operator-side answer to *how do you maintain the CLAUDE.md as the project evolves?*
6. **Root-cause investigation** — generate hypotheses from disjoint evidence (logs / files / data), face panel of verifiers and refuters. **Structurally prevents self-preferential bias.**
7. **Triaging at scale** — classify each item, dedupe against tracked, take action (attempt fix or escalate to human). **Quarantine pattern**: *"bar agents that read untrusted public content from taking high-privilege actions, which are instead done by the agents in charge of acting on the information."* **First wiki-captured Anthropic-canonical quarantine-pattern for untrusted-input workflows** — operationalization of the [[chatgpt-sheets-exfiltration-promptarmor-2026-06-01|ChatGPT-Sheets exfil]] / [[willison-meta-ai-instagram-exfiltration-2026-06-01|Meta AI exfil]] cross-vendor pattern at the workflow-orchestration layer.
8. **Exploration and taste** — taste-based exploration (design / naming) with review-agent rubric.
9. **Evals** — lightweight evals via worktree spinoff + comparison-agent rubric grading.
10. **Model and intelligence routing** — classifier agent decides which model to use based on task complexity research. **First wiki-captured Anthropic-canonical model-routing-via-classifier-agent pattern** — pairs with [[zodchii-opus-4-8-setup-guide-2026-05-29|zodchii's routing matrix]] (operator-side static routing) at the workflow-internal-decision layer.

### Practitioner tips

- **"Use a workflow" or "run a workflow"** in natural language works as opt-in (in addition to `ultracode` keyword)
- **"Quick workflow"** prompt for small adversarial reviews of an assumption — *workflows are not just for large tasks*
- **Pair with `/loop`** for repeatable workflows (triage, research, verification)
- **Pair with `/goal`** for hard completion requirements
- **Explicit token budgets**: *"use 10k tokens"* prompt sets the cap
- **Save via `s` in `/workflows` menu** to `~/.claude/workflows/` or distribute via skill
- **Workflows as templates inside skills**: *"To share them via a skill, put your JavaScript workflow files in the skill and folder and reference them in the SKILL.MD. To allow for more flexibility, you may want to prompt Claude to think of the workflows in the skill as a template instead of a script that needs to be run verbatim."* **First wiki-captured Anthropic-canonical workflows-as-templates-inside-skills distribution primitive**.

### When NOT to use Dynamic Workflows

> *"It's best to use workflows creatively to push Claude Code in ways that you haven't previously. For regular coding tasks, try and ask yourself does it really need more compute? For example, most traditional coding tasks do not need a panel of 5 reviewers."*

**First wiki-captured Anthropic-canonical anti-pattern guidance for Dynamic Workflows** — pairs with the docs' cost-management framing as the *use-judiciously* counter-balance to the marketing-side *workflows-are-the-new-tier* positioning.

### Cross-cutting framings

- **3rd Thariq Shihipar wiki surface establishes him as Anthropic-internal practitioner-content voice for the Claude Code agent-architecture surface**: 1st (HTML output framing) was an output-format-side surface; 2nd (Suzanne's Learn Quiz) was a session-management-side surface; 3rd (this) is an orchestration-side surface. **Pattern**: Thariq's surfacing role is *bringing Anthropic-internal Claude Code practice into the public discourse* — the wiki should treat his X / blog posts as Anthropic-canonical practitioner-content reference even when not formally an Anthropic publication.
- **Pairs with [[anthropic-institute-when-ai-builds-itself-2026-06-04|the Anthropic Institute's RSI publication]]**: the Institute publication shows the *aggregate-productivity outcome* of agent-orchestration at Anthropic (8× per-engineer code productivity); Thariq's harness post shows the *concrete-mechanism* (workflows orchestrating subagents, applying the 6 patterns to mitigate the 3 failure modes). **First wiki-captured Anthropic-canonical aggregate-outcome + concrete-mechanism pair publication sequence**.
- **Pairs with [[andrewng-ai-fde-vs-ai-engineer-2026-06-01|Ng's 5 future-specialist-role predictions]]**: Thariq's 6 patterns + 8 use cases are *the building blocks Harness Engineers and Evals Engineers would specialize in*. **First wiki-captured concrete-skill-set inventory for the predicted Harness Engineer + Evals Engineer specialist roles**.
- **Pairs with [[ai-vulnerability-discovery|the cross-vendor agent-exfiltration pattern]]**: the **quarantine pattern** in the triaging-at-scale use case is the operationalization of *"bar untrusted-content-reading agents from taking high-privilege actions"* — first wiki-captured Anthropic-canonical security primitive for the same pattern that's been demonstrated as failure at Microsoft Copilot Cowork + ChatGPT-Sheets + Meta AI.

### Notably-absent

- **No concrete cost / token numbers** for the Bun Zig→Rust migration or the W2S researcher-style end-to-end research workflow.
- **No specific runtime-engine internals** (how Claude generates the JavaScript, what guardrails on the generated code, what the runtime can/can't do at the Node-level).
- **No specific Anthropic-internal Dynamic Workflows usage data** — the post is practitioner-tips, not first-party productivity data (the Anthropic Institute publication carries that).
- **No mention of `/loop` or `/goal` documentation page** in the linked content — pattern-watch for those primitives surfacing as canonical docs.

## Pages Updated

- [[thariq-shihipar]] — 3rd wiki surface added; Dynamic Workflows harness articulation; surfacing-role-as-Anthropic-internal-practitioner-content-voice now established
- [[claude-code]] — 3-failure-mode framework + 6-pattern catalog + quarantine pattern + model-routing-via-classifier-agent pattern added
- [[anthropic-dynamic-workflows-official-docs-2026-06]] — companion canonical-docs surface; cross-referenced
- [[bun]] — Zig→Rust migration via Dynamic Workflows confirmed at practitioner-side; Jarred Sumner thread cited
- [[claude-md-pattern]] — CLAUDE.md-mining workflow primitive added as the operator-side answer to maintenance question
- [[agentic-engineering]] — 3-failure-mode framework + 6-pattern catalog references added

## Adjacent sources

- [[anthropic-dynamic-workflows-official-docs-2026-06]] — canonical docs companion
- [[anthropic-dynamic-workflows-primary-2026-05-28]] — May 28 preview-ship announcement
- [[claude-opus-4-8-dynamic-workflows-2026-05-28]] — Opus 4.8 launch context
- [[nateherk-dynamic-workflows-2026-05-30]] — Nate Herk 41-Haiku case study
- [[trq-suzanne-learn-quiz-2026-06-01]] — 2nd Thariq surface (Suzanne's Learn Quiz)
- [[willison-html-effectiveness-2026-05]] — 1st Thariq surface (HTML output framing)
- [[anthropic-institute-when-ai-builds-itself-2026-06-04]] — aggregate-productivity-outcome companion publication
- [[andrewng-ai-fde-vs-ai-engineer-2026-06-01]] — Ng's 5 specialist-role predictions context
- [[zodchii-opus-4-8-setup-guide-2026-05-29]] — practitioner-side routing matrix context
- [[rody-5-subagent-templates-2026-05-31]] — individual-worker template library context

## Verification-pending

- Specific failure-mode incidence-rate data (how often does agentic laziness vs self-preferential bias vs goal drift dominate?)
- Whether the 6 patterns are exhaustive or a curated subset
- Bun Zig→Rust migration concrete workflow-script structure
- Specific *"quick workflow"* token-cost framing vs full workflow
- How the *args* primitive integrates with token budgets
- Whether the `xhigh`-effort-only `ultracode` constraint is permanent or model-tier-dependent
- Specific Claude.com/blog vs X publication date difference (post is on X 2026-06-02; Claude Blog date verification-pending)
