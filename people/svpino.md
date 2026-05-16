---
name: Santiago Valdarrama (svpino)
type: person
affiliation: independent (AI/ML educator, content creator)
signal_sources: [twitter, github]
last_updated: 2026-05-16
---

## Who They Are

Santiago Valdarrama (@svpino on X) is an independent AI/ML educator with sustained-reach practitioner content on X. First wiki capture via his 2026-05-15 X post on **HTML-over-Markdown for agents + introduction of [[tools/dac|bruin-data/dac]]**. Bio details beyond X presence not captured in this ingest batch; verify before external citation.

## Their Current Focus

- **HTML-over-Markdown thesis for agents** — pragmatic version: HTML wins on rendering substrate, but is too verbose for humans; let agents *generate* HTML from a denser YAML/TSX input.
- **Tooling for agent-friendly data infrastructure** — surfacing [[tools/dac|bruin-data/dac]] as an existence proof of the HTML-as-output / YAML-as-input pattern.

## Notable Takes

- **"Markdown was doomed from the start"** (May 15 2026): *"It's just a format with low information density. HTML is better for humans, and agents can now consume and produce it without issues."* Continues the [[willison-html-effectiveness-2026-05|HTML-over-Markdown thread]] from Thariq Shihipar / Karpathy / Willison May 8. — [[svpino-bruin-dac-markdown-doomed-2026-05-15]]
- **"Nobody wants to type HTML, so here is an alternative"** (May 15 2026): the pragmatic move — keep HTML as the output substrate; use YAML/TSX as the denser intermediate that humans (or agents) author. Structurally the practitioner-instantiated version of [[karpathy-html-output-taxonomy-2026-05-08|Karpathy's 4-step taxonomy]] step 3.
- **"Subagent-pilled with Claude Code"** (May 15 2026): *"Everything that can be a subagent should be a subagent."* Three named advantages — separate context windows, per-subagent model selection (Haiku/Sonnet/Opus by task), per-subagent tool configuration. svpino himself walks the framing back in the same thread (*"I'm overindexing on using them now, but I'm sure I'll find the proper balance"*), confirming the microservices-analogy arc. The comment-thread payload — coordination tax past the four-agent threshold, shared-mutable-state boundary, audit-trail collapse — surfaces the natural ceiling on subagent-everything decomposition. — [[svpino-subagent-pilled-2026-05-15]]

## Where to Follow

- X: [@svpino](https://x.com/svpino)
- Other surfaces (LinkedIn, blog, podcast) not captured in current ingest batch

## Cross-references

- [[svpino-bruin-dac-markdown-doomed-2026-05-15]] — first wiki capture.
- [[svpino-subagent-pilled-2026-05-15]] — subagent-pilled posture and same-thread walk-back.
- [[dac]] — the tool svpino surfaced.
- [[willison-html-effectiveness-2026-05]] / [[karpathy-html-output-taxonomy-2026-05-08]] — prior HTML-over-Markdown thread.
