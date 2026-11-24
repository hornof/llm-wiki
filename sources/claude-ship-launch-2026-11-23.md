---
title: "Introducing Claude Ship (plus the /ship and Claude Approvals docs)"
type: source
medium: article
url: https://claude.com/resources/articles/introducing-claude-ship
ingested: 2026-11-23
local_source: "_raw/claude-ship-launch-2026-11-23.txt"
---

## Summary

Anthropic's launch post for Claude Ship (2026-11-23), read with the Claude Code docs for `/ship` and Claude Approvals and Digg's summary. Claude Ship bundles three agents that take a GitHub pull request from review to an approval decision: Code Review (generally available since [[claudedevs-code-review-ga-2026-10-15|2026-10-15]]), and two new beta agents, PR Steward (fixes) and Claude Approvals (approves under a team-written policy). Individuals get it through a new `/ship` command in Claude Code. It's for Team and Enterprise plans on GitHub, billed on tokens.

## Key Claims / Takeaways

- **Three parts** (Anthropic): *"Claude Ship is made up of Code Review, which is already generally available, and two new agents in beta: PR Steward and Claude Approvals."*
- **PR Steward fixes, never approves** (Anthropic): it *"is designed not to approve or merge pull requests"*. It works on failing CI, merge conflicts and review comments, and after each push comments with what it changed and how to undo it. `@claude stop` makes it step back.
- **Claude Approvals is a policy file** (docs): rules live in `.claude/approvals.yml`; each rule sets `paths`, `seats` (how many people must approve) and whether Claude may approve. Anthropic calls it *"a smarter CODEOWNERS file"*. Conditions can read PR facts and classifier answers but *"can’t read CI results"*, so CI stays a separate required check.
- **Ways it can let an unreviewed change merge** (docs): the check blocks only if GitHub requires it; *"the author can fill a seat"*; GitHub counts Claude's approving review as an approval; and *"a rule with claude: approves starts no Code Review by itself"*. Adding a policy file can also turn off automatic Code Review unless a rule names `claude/code_review`.
- **`/ship` acts without a confirmation prompt** (docs): *"/ship proceeds with no confirmation prompt"*. It can commit all uncommitted changes, new files included, push, and open the PR as you, with a few seconds to press Esc. Secret detection is by file name only (*"such as .env"*). Needs Claude Code v2.1.330 or later; cloud sessions don't have it. `/steward` does the fixing without a review on an already-open PR.
- **The watch runs your code** (docs): *"Run a watch only where you trust everyone who can merge to the base branch or push to your branch. Any of them can run programs on your computer with your credentials."*
- **Internal numbers** (Anthropic, vendor claim): on the Claude Code team *"merged PRs more than doubled from June to September while the share reverted fell by more than 40%"*. Enterprise organizations can claim *"at least $10,000 in Claude Ship credits"* by January 15, 2027.
- **Exclusions and cost** (Anthropic): not available with Zero Data Retention, the HIPAA configuration or customer-managed keys. Usage is billed on tokens, and a policy that uses Claude's review *"triggers a billed Code Review, even in observe mode."*
- **Cherny** (X, via Digg): *"A year ago we launched Opus 4.5, the first model to write 100% of my code. Shipping PRs hasn’t caught up"*.

## Pages Updated

- [[claude-code]]
- [[anthropic]]
- [[boris-cherny]]
