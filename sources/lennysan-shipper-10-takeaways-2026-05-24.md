---
title: "Lenny Rachitsky × Dan Shipper: 10 takeaways on the future of work"
type: source
medium: twitter-thread
url: https://x.com/lennysan/status/2058914803360600238
ingested: 2026-05-25
---

## Summary

Two-layer Lenny Rachitsky X surfacing 2026-05-24 of his Every / Dan Shipper podcast: (1) a teaser thread with three contrarian one-liners — *"Automation is a lie. CLIs are over. The SaaSpocalypse is dumb."* — and six bulleted predictions to be scored in exactly a year; (2) a full **10-takeaways post** synthesizing the full episode, surfaced 2026-05-24/25. First wiki capture of Dan Shipper (Every) as a tracked voice; first wiki capture of Lenny Rachitsky's podcast as a wiki-surface. Comment thread has multiple substantive practitioner reactions worth tracking. **Two of the takeaways directly contradict wiki-canonical framings** (SaaS-NOT-dead vs Chamath two-tier; super-agent-in-Slack vs every-employee-personal-agent) — worth holding as practitioner-disagreement signals.

## Key Claims / Takeaways

### The three teaser one-liners (the headline framing)

- *"Automation is a lie."*
- *"CLIs are over."*
- *"The SaaSpocalypse is dumb."*

All three are intentionally contrarian; each maps to a takeaway below.

### The 10 takeaways (verbatim structure)

1. **Future of work happens inside Codex or Claude Code.** Shipper spends all his time in Codex — writing docs, managing email, doing research — using Google Docs / PostHog / etc *inside the agent's in-app browser*. *"The agent can see what he's doing, and has all of his context."* The reverse of putting AI into your SaaS tool: you use SaaS tools inside your AI agent.
2. **Automation is a lie — every automation needs a human.** Every "doubled in size this year despite being incredibly AI-forward." *"Benchmarks are misleading — they measure AI on problems we've already framed and can score, but there's always a higher frame."*
3. **PMs will win the AI era.** Marcus (former PM at Axios's writing product) joined Every, got AI-pilled, now runs their product Spiral. *"Any PM who gets really AI-native will be incredibly dangerous because the building is done for you — what matters is figuring out what to build and if it's great."*
4. **Full-stack designers are becoming superheroes.** Designers no longer need to hand off to engineers; AI handles execution. *"AI is the perfect tool for them because it lets them bring their vision to life without the traditional bottlenecks."*
5. **SaaS is NOT dead — Shipper is bullish on SaaS stocks.** *"When users bring their own AI (via Codex or Claude Code) to use SaaS products, the user — not the SaaS company — pays for tokens. This saves SaaS company's margins."* Plus: agents need their own SaaS seats → **massive new SaaS demand**.
6. **Every company will have one "super-agent" inside their Slack.** Shipper **flipped his prior view** that every employee would have a personal work agent — *"agents need humans who care about them; when someone gets tired of maintaining their personal agent, it becomes useless."* Winning model: one forward-deployed engineer maintains a company-wide agent (cites [[shopify]]'s **River** and **Viktor** as instances), then specialized team agents trickle down as models mature.
7. **AI job apocalypse is not happening, but you need to evolve.** *"Models make yesterday's human competence cheap. But because everyone uses the same models, it all looks the same if you use it the default way; it becomes commoditized slop. Humans then take that frozen competence and use it to make something new and interesting for their specific situation. The key: 'ride the models.'"*
8. **We will read way more AI-generated writing and we will like it.** *"For internal docs, planning, and email, AI-generated is often better because most people are bad at writing strategy documents."*
9. **Build software for humans and agents to use together.** Current model is *"a CLI that an agent uses independently"*. Shipper's framing: *"you and your agent should be using the app together"* — agents make a billion requests in three seconds, so you need **approval flows, inboxes that summarize what happened, logs, and easy rollback**.
10. **Forward-deployed engineers are the new most essential role.** *"The big model companies have teams of people managing their internal agents, and those teams aren't going away. It's different from traditional software building, and certain engineers love it."*

### Author exchange in comments (worth quoting)

- **Dan Shipper** (@danshipper, 2026-05-25): *"Thanks Lenny!! Great summary. More about the future of work with Codex, Claude Code and Cowork here: [every.to After Automation](https://every.to/...)"* — Shipper himself names **Cowork** (Anthropic) alongside Codex and Claude Code as the agent surfaces.
- **Maksim** (@MaksimXBT) asks why Cowork isn't mentioned in the original Lenny post. **Lenny** replies: *"I think he treats CC and Cowork as the same, imho they'll likely merge over time"* — first wiki-captured framing of Claude Code + Cowork likely-to-merge as a single surface.

### Substantive comment-thread practitioner reactions

- **Crepe Supreme** (@crepesupreme): *"The 'Codex or Claude Code' framing fits one job family. Microsoft 365 Copilot has 20M paid enterprise seats at $7.2 billion ARR. ChatGPT Enterprise plus Business is over 5M paying users. Most knowledge workers run their AI inside Office and Workspace."* — **first wiki-captured M365 Copilot 20M-paid-seats / $7.2B ARR data point**; sharp counter-frame to the Codex-or-Claude-Code-as-operating-system claim. Worth tracking — Crepe's numbers should be verified.
- **Erica Ding** (@DingErica): *"9 is the underrated one. SaaS was designed for human-paced interaction: deliberate, one action at a time. Agents don't work that way. Approval flows and rollback are band-aids. The actual design challenge is figuring out who's in control at any given moment."* — cleanest single-sentence framing of the human/agent shared-software design challenge.
- **Skaltek** (@SKalTekk): *"The SaaS-inside-agent framing feels right, but the hard product layer is permissions and provenance. If agents operate across SaaS UIs, users need to see which data was read, which actions were taken, and what can be rolled back."* — provenance + permissions framing pairs with [[jeff-clarke-dell-ai-native-imperatives-2026-05-19|Clarke's "every action needs a receipt" audit-trail framing]].
- **Manav Garkel + Tech With Matteo**: both flag point 5 (SaaS-NOT-dead) as the underrated bullish take. Manav: *"the usage floor goes up, not down."*

## Why It Matters

- **Direct contradiction of [[chamath-openai-consulting-fox-in-henhouse-2026-05-17|Chamath two-tier SaaS-disruption thesis]]**: Shipper argues **SaaS demand goes UP, not down**, because agents need their own seats and users pay tokens (not SaaS companies). This is the **first wiki-captured high-signal voice arguing against the SaaS-disruption thesis from the same starting facts**. Worth holding as a structural practitioner-disagreement signal. Shipper's claim is falsifiable on a 12-month horizon — Lenny says explicitly *"we'll score these in exactly a year."*
- **Super-agent-in-Slack pattern** is the inverse of the [[sairahul1-solo-founder-13-agent-playbook-2026-05-15|sairahul1 13-agent-per-solo-founder]] and [[svpino-subagent-pilled-2026-05-15|svpino subagent-pilled]] decomposition framings. Shipper's framing centralizes maintenance (one forward-deployed engineer running a company-wide agent) rather than decentralizes it. **Names Shopify's River and Viktor** as production examples — wiki has [[river|River]] (tool page) but not Viktor. Worth adding Viktor as a candidate-tracked-entity.
- **First wiki capture of Dan Shipper + Every** as a tracked voice. Shipper runs Every; their product **Spiral** is now also wiki-relevant. Worth tracking as the AI-native-publishing-and-software-house entity.
- **First wiki capture of Lenny Rachitsky's podcast** as a wiki-surface. Lenny is a high-signal product/AI commentator; the podcast format means substantive multi-takeaway content per episode. Worth tracking.
- **First wiki-captured Microsoft 365 Copilot ARR data point** (via Crepe Supreme comment): **20M paid enterprise seats at $7.2B ARR**; ChatGPT Enterprise + Business over 5M paying users. These numbers would be substantial if verified — Microsoft's enterprise AI distribution has been wiki-undertracked relative to Anthropic / OpenAI / Google. **First-tier verification-pending claim** worth tracking; if verified, materially changes the AI-deployment competitive landscape captured in [[forbes-ai-50-2026]].
- **"Ride the models" framing** as the labor-market guidance is structurally adjacent to the [[shilpamitra-claude-code-30-commands-2026-05-22|`/effort` discipline]] and pairs with [[deedydas-sf-ai-wealth-divide-2026-05-15|the SF AI-wealth-divide vibecoding-as-escape-hatch framing]] — same practitioner discipline framed from a different angle.
- **Forward-deployed-engineer role** is the third wiki-captured surface naming FDE as central, after [[anthropic-finance-agents-2026-05-05|Anthropic's vertical-build map]] and [[chamath-openai-consulting-fox-in-henhouse-2026-05-17|Chamath's OpenAI Deployment Company framing]]. **Three independent surfaces converging on FDE as the load-bearing 2026 AI role.**
- **Codex + Claude Code + Cowork merge framing** (Lenny's own comment) is the first wiki capture of the **likely-convergence** of these three Anthropic/OpenAI agent-surfaces. Pairs with [[google-io-2026-flash-omni-spark-antigravity|Google's Gemini Spark / Antigravity 2.0]] consolidation.

## Caveats

- **Podcast itself not deeply fetched.** All 10 takeaways are Lenny's summary; Shipper's actual phrasing may differ. Worth a deep-fetch on the every.to "After Automation" essay Shipper links in the comments.
- **Crepe Supreme M365 Copilot numbers (20M paid / $7.2B ARR)** are unsourced and uncorroborated — captured as **verification-pending high-impact signal**. If true, materially undercut by the Codex-or-Claude-Code-as-operating-system framing.
- **Shipper has commercial incentives** — he runs Every; Every is bullish on the "AI is the new operating system" framing because it's their bet. SaaS-bullish framing may be motivated by his investment thesis as much as by structural analysis.
- **Single-source 12-month-scoreable predictions** are useful as a tracked-bet but should not be treated as wiki-canonical until they verify. Lenny commits to scoring in a year — worth a `meta/` checkpoint in May 2027.
- **"CLIs are over"** framing in the teaser is overstated relative to the actual takeaways — takeaway 1 is about agent-in-app-browser displacing per-tool AI; CLIs (Codex, Claude Code) are *more* central, not less. Treat the teaser as rhetorical.
- **The Shopify River + Viktor naming**: Lenny names both. The wiki tracks [[river|River]]; Viktor is new. Whether Viktor is a second agent or a person remains unclear from the brief synopsis.

## Cross-references

- [[chamath-openai-consulting-fox-in-henhouse-2026-05-17]] — Chamath two-tier SaaS-disruption thesis; Shipper's takeaway 5 directly contradicts on the same starting facts.
- [[saas-disruption-thesis]] — Shipper's bullish-on-SaaS counter-take added as the first wiki-captured high-signal-voice opposition.
- [[ai-native-organizations]] — super-agent-in-Slack centralized-maintenance framing is alternative to decomposed-per-employee agents; worth contrasting with [[sairahul1-solo-founder-13-agent-playbook-2026-05-15]] and [[svpino-subagent-pilled-2026-05-15]].
- [[shopify]] — River + Viktor named as production super-agent examples.
- [[river]] — Shopify's super-agent surface; cross-confirmed by Shipper.
- [[claude-code]] / [[openai|Codex]] / [[claude-cowork]] — three surfaces framed as future-of-work substrate; Lenny's own framing that they will likely merge.
- [[jeff-clarke-dell-ai-native-imperatives-2026-05-19]] — "every action needs a receipt" provenance framing cross-confirmed by Skaltek comment.
- [[ai-labor-market-impacts]] — "AI job apocalypse not happening / ride the models" framing.
- [[deedydas-sf-ai-wealth-divide-2026-05-15]] — adjacent "ride the wave" framing from a different cultural angle.
- [[stahlberg-team-os-aakash-2026-05]] — PMs-win-the-AI-era practitioner instantiation.
- [[forbes-ai-50-2026]] / [[techcrunch-anthropic-ramp-business-customers-2026-05-13]] — M365 Copilot 20M paid / $7.2B ARR claim warrants comparison if verified.

## Pages Updated

- [[saas-disruption-thesis]] (updated — Shipper's bullish-on-SaaS counter-take added as "Counter-Thesis (Shipper, May 2026)" subsection: tokens-paid-by-user not SaaS company + agents-need-seats → demand-floor-goes-up framing; falsifiable on 12-month horizon; date bumped to 2026-05-25)
- [[ai-native-organizations]] (updated — Super-Agent-in-Slack centralized-maintenance pattern added; one-forward-deployed-engineer maintains company-wide agent (Shopify River + Viktor); Shipper-flipped-from-personal-agent-view; contrasts with decomposition framings; date bumped to 2026-05-25)
- [[claude-code]] (updated — Codex + Claude Code + Cowork "likely to merge over time" framing added under Community Sentiment with Lenny Rachitsky attribution; agent-in-app-browser-as-future-of-work framing added; date bumped to 2026-05-25)
