---
name: Block
type: company
status: active
last_updated: 2026-07-23
---

## What It Is

Block, Inc. (formerly Square) is a financial technology company founded by [[jack-dorsey]] and Jim McKelvey in 2009. Products include Square (merchant payments/POS), Cash App (consumer payments/banking), Afterpay (BNPL), TIDAL (music), and Bitcoin/crypto infrastructure. As of 2026, Block is actively restructuring its internal organization around AI "world models" — positioning itself as one of the first large companies to attempt replacing traditional hierarchy with AI-native coordination.

## Builderbot — production-scale AI-native engineering operationalization (2026-06-17)

**STRUCTURALLY MASSIVE**: Block launches **Builderbot** at production-scale ([[block-builderbot-launch-2026-06-17]]) — first wiki-captured concrete production-scale operationalization of the AI-native-organization thesis:

- **200,000 operations per day**
- **1,500 PRs merged per week**
- **15% of all production code changes across Block**
- **100% of Block engineers regularly use AI in their work**
- Built on Block's open-source [[goose|Goose]] agent framework (contributed to **AAIF Linux Foundation**)
- Slack-native: anyone can tag `@builderbot` in any thread
- Cross-service work across hundreds of millions of lines of code
- Picks up tickets from Linear + Jira; creates branch + writes code + opens PR + watches CI + iterates

**Brad Axen** (Head of AI Capabilities at Block) canonical-framing: *"the missing layer between AI coding tools and how engineering actually works at scale"* + *"backlog to live in front of millions of customers in days instead of months"*

Pairs structurally with [[satya-nadella-frontier-ecosystem-not-frontier-model-2026-06-14|Nadella firm-tier learning-loop canonical-architecture]] at firm-tier operationalization layer. First wiki-captured "shift from AI-assisted coding to AI-native engineering" canonical framing.

## AI-Native Organization Experiment

Block is replacing middle management with two AI world models:

- **Company world model**: continuously updated understanding of all internal operations, decisions, and priorities — does the information routing that managers used to do
- **Customer world model**: per-customer, per-merchant representation built from transaction data across both sides (Cash App + Square); "money is the most honest signal in the world"

An **intelligence layer** sits on top, composing atomic financial capabilities into proactive customer solutions without product managers defining roadmaps. Three roles replace the traditional management pyramid: ICs, DRIs, and player-coaches.

This is Sequoia-backed and explicitly called out as a model they believe "will reshape how companies of all kinds operate." — [[block-organizational-intelligence]]

## Relevance to AI Engineering

- One of the most concrete, at-scale attempts to deploy AI as organizational infrastructure rather than productivity tool
- The architecture (capabilities → world model → intelligence layer → interfaces) is a template for how AI-native companies might be built
- Connects to the broader [[agentic-ai]] theme: the intelligence layer is an agentic system with access to atomic capabilities

## Traction Signals

- **2026-07-22 — open-sources [[buzz|Buzz]]** ([[block-buzz-launch-2026-07-22]]): a Nostr-based, Apache-2.0, self-hosted **workspace where people *and* agents are equal, cryptographically-identified members** behind a signed event log — built to *"reduce dependency on Slack + GitHub"* and solve the *"one context"* problem ([[jack-dorsey|Jack Dorsey]]). Block's 2nd major open-source agent-infra release after [[goose|Goose]]; operationalizes *"block is rebuilding itself to be an intelligence."*
- Sequoia-endorsed experiment; essay published as thought leadership [unsourced on date]
- Remote-first, artifact-rich culture makes the "machine-readable work" prerequisite feasible [per [[block-organizational-intelligence]]]

## Cross-Reference

- [[jensen-huang]] / [[nvidia]] — different route to flat structure: Jensen uses direct broadcasting to 55 reports; Block uses AI world models; both eliminate middle-management information routing
- [[ai-native-organizations]] — concept page for this pattern

## Strategy Quote (Dorsey, April 2026)

"I think most of the industry is thinking about AI as like a co-pilot, as something that is augmented onto, rather than like how do you just rebuild our whole company with this as the core." Block has been executing on this thesis since early 2024, including building [[goose]], an internal agent coding harness. — [[post-realBigBrainAI-dorsey-ai-rebuild]]

## Resources

- [[block-organizational-intelligence]] — primary source essay on org architecture
- [[post-realBigBrainAI-dorsey-ai-rebuild]] — Dorsey on copilot vs. rebuild strategy (April 2026)
- [[jack-dorsey]] — co-founder and CEO
- [[goose]] — Block's internal agent coding harness
