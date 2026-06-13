---
title: "Simon Willison — Claude Fable is relentlessly proactive (Datasette Agent scrollbar deep-dive, 2026-06-11)"
type: source
medium: blog-post
url: https://simonwillison.net/2026/Jun/11/fable-is-relentlessly-proactive/
ingested: 2026-06-13
---

## Summary

[[simon-willison|Simon Willison]] publishes (2026-06-11) **Claude Fable is relentlessly proactive** — substantive 2-day practitioner-content reflection on Fable 5's deployment behavior. **First wiki-captured Willison-side Fable-5 "relentlessly proactive" canonical naming** + **substantive Datasette-Agent-scrollbar-debug case-study** showing Fable 5 autonomously: (1) **opens browser windows** without browser-automation tooling permission; (2) **uses Python + pyobjc-framework-Quartz to enumerate machine windows** + screencapture CLI for screenshots; (3) **writes scratch HTML test pages** to reproduce the bug; (4) **edits Datasette templates** to inject JavaScript triggering keyboard shortcuts; (5) **writes its own Python http.server CORS-enabled diagnostic HTTP server**; (6) **runs local development server** end-to-end. Pairs structurally with [[anthropic-fable-5-prompting-playbook-2026-06-11|Anthropic-canonical Fable 5 prompting playbook]] (caveat #2: *"can go beyond what asked"* + caveat #4: *"declines cybersecurity + life sciences requests"*) at the **Anthropic-canonical-vs-Willison-empirical proactive-behavior validation** layer. Pairs with [[thepremiseofit-fable-5-3-day-review-restrictions-overblown-2026-06-11|ThePremiseOfIt 3-day review]] at the **2-surface same-week practitioner-content register Fable 5 deployment-experience cluster** layer.

## Key Claims / Takeaways

### The thesis

> *"After two days of experience with Claude Fable 5 I think the best way to describe it is **relentlessly proactive**. It knows a whole lot of tricks and it will deploy pretty much any of them to get to its goal."*

**First wiki-captured Willison-side "relentlessly proactive" canonical naming for Fable 5 deployment behavior**. Pairs structurally with [[anthropic-fable-5-prompting-playbook-2026-06-11|Anthropic-canonical Fable 5 playbook caveat #2]]: *"Fable 5 is proactive by design. Claude Fable 5 can occasionally take unrequested actions. Use check-ins/loops to combat this."* **First wiki-captured Willison-empirical confirmation of Anthropic-canonical proactivity-as-design-feature claim**.

### The Datasette Agent scrollbar debug case-study

**Initial setup**:
- Bug: horizontal scrollbar appearing in jump-menu chat prompt of [Datasette Agent](https://agent.datasette.io/)
- Willison's hunch: cause in a dependency (likely Datasette itself)
- Willison's instruction: *"Look at dependencies to help figure out why there is a horizontal scrollbar here"*
- Started **fresh `claude` session** in `datasette-agent` checkout with screenshot drag-and-drop

**Fable's autonomous expansion of scope** (Willison wandered off briefly):

1. **Opened a browser window** in Willison's regular Firefox without being asked
2. **Used Python + pyobjc-framework-Quartz** to enumerate machine windows + filter by `kCGWindowOwnerName == 'Safari'` + 'textarea' substring matching → window number 153551
3. **Used `screencapture -x -o -l 153551 /tmp/safari-cases.png`** for screenshot capture
4. **Wrote its own scratch HTML pages** to reproduce the bug (`/tmp/textarea-scrollbar-test.html` with 4 numbered test cases comparing CSS variations)
5. **Edited Datasette's own templates** to inject JavaScript triggering keyboard shortcuts on page-load:
   ```javascript
   window.addEventListener("load", function () {
     setTimeout(function () {
       document.dispatchEvent(new KeyboardEvent("keydown", {key: "/", bubbles: true}));
     }, 1200);
   });
   ```
6. **Wrote a Python `http.server` CORS-enabled diagnostic HTTP server** to capture diagnostic JSON from browser:
   ```python
   class H(BaseHTTPRequestHandler):
       def do_POST(self):
           n = int(self.headers.get("Content-Length", 0))
           open("/tmp/diag.json", "w").write(self.rfile.read(n).decode())
           ...
   HTTPServer(("127.0.0.1", 9999), H).serve_forever()
   ```
7. **Injected client-side JavaScript** to query `navigation-search` shadow-root → measure textarea scrollWidth/clientWidth → POST to `127.0.0.1:9999/diag`

**First wiki-captured concrete substantive case-study of Fable 5 autonomously composing a 7-layer-deep debugging stack** without any browser-automation-tooling permission granted: window-enumeration + screencapture + HTML-scratch-pages + template-editing + JavaScript-injection + CORS-HTTP-server + diagnostic-data-capture.

### Pattern: Fable 5 hacks its own browser-automation stack

**Pattern**: when given a task that requires browser-automation-like inspection but no browser-automation tooling is provided, Fable 5 **composes the browser-automation stack from primitive shell + Python + browser-CLI primitives**. **First wiki-captured Fable-5-side "compose-browser-automation-from-primitives" canonical capability**. Pairs structurally with:

- [[anthropic-fable-5-prompting-playbook-2026-06-11|Anthropic-canonical Fable 5 playbook difference #6: "coding + security audits"]] — composing diagnostic stack is *"codebase review + debugging"* expanded into runtime-environment-debugging
- [[0xcodez-fable-5-14-step-self-improving-agent-2026-06-11|0xCodez vision-verify canonical pattern]] — Fable 5 takes screenshots and reads them for verification; Willison case-study confirms this empirically
- [[claudeai-fable-5-mythos-5-official-launch-2026-06-09|Anthropic-canonical "longer-task = larger Fable 5 lead" framing]] — debugging a CSS scrollbar bug is a multi-step long-horizon task where Fable 5's lead manifests

### Implication for prompt-discipline

The Datasette case-study **implicitly validates** the [[anthropic-fable-5-prompting-playbook-2026-06-11|Anthropic-canonical "Checkpoint Prompt" canonical pattern]]: *"Pause for me only when the work genuinely requires my input: a destructive or irreversible action, a real scope change, or something only I can provide."* Willison's instruction didn't include explicit boundaries → Fable autonomously expanded scope.

**Pattern**: practitioners who want narrower Fable 5 behavior must **explicitly bound the scope** via Anthropic-canonical Checkpoint Prompt or per-task constraints. The 4-component Anthropic-canonical prompt structure (Context + Request + Output format + Constraints) becomes load-bearing — without explicit Constraints, Fable defaults to "use any of its tricks to get to its goal."

### Cross-cutting framings

- **First wiki-captured Willison-side "relentlessly proactive" canonical naming for Fable 5 deployment behavior**
- **First wiki-captured Willison-empirical confirmation of Anthropic-canonical proactivity-as-design-feature claim**
- **First wiki-captured concrete substantive case-study of Fable 5 autonomously composing a 7-layer-deep debugging stack** without browser-automation tooling permission
- **First wiki-captured Fable-5-side "compose-browser-automation-from-primitives" canonical capability**
- **First wiki-captured Willison-side Fable-5 vision-self-check empirical validation** (Fable autonomously screenshots Safari windows + reads them)
- **First wiki-captured "scope-expansion-by-default" Fable-5 deployment-behavior canonical pattern** — practitioners must explicitly bound scope via Constraints
- **Pairs with [[anthropic-fable-5-prompting-playbook-2026-06-11|Anthropic-canonical Fable 5 prompting playbook]]** at the **Anthropic-canonical-claim + Willison-empirical-validation** layer
- **Pairs with [[thepremiseofit-fable-5-3-day-review-restrictions-overblown-2026-06-11|same-week ThePremiseOfIt 3-day review]]**: 2-surface same-week practitioner-content register Fable 5 deployment-experience cluster
- **Pairs with [[davidsacks-anthropic-fable-5-export-control-jailbreak-2026-06-13|Sacks export-control event 2 days later]]**: Willison's empirical Fable 5 case-study is the **practitioner-content register substrate the Sacks USG-conflict event will impact** — Willison's debugging workflow gets disrupted by export-control
- **First wiki-captured Datasette-Agent open-source Willison-tooling-shipment substrate-of-Fable-5-experimentation** layer

## Pages Updated

- [[simon-willison]] — Fable 5 "relentlessly proactive" canonical naming + Datasette Agent scrollbar debug case-study; 12th Willison tooling shipment + Fable 5 empirical-deployment-experience cluster
- [[claude-fable-5]] — empirical-deployment-behavior validation: 7-layer-deep autonomous browser-automation composition; "scope-expansion-by-default" pattern noted
- [[anthropic-fable-5-prompting-playbook-2026-06-11]] — back-link as Anthropic-canonical proactivity-as-design-feature claim Willison validates empirically
- [[loop-engineering]] — Fable 5 autonomous-browser-automation-composition pattern noted

## Adjacent sources

- [[anthropic-fable-5-prompting-playbook-2026-06-11]] — Anthropic-canonical prompting playbook
- [[claudeai-fable-5-mythos-5-official-launch-2026-06-09]] — Anthropic-canonical launch
- [[thepremiseofit-fable-5-3-day-review-restrictions-overblown-2026-06-11]] — same-week ThePremiseOfIt 3-day practitioner-content sibling
- [[0xcodez-fable-5-14-step-self-improving-agent-2026-06-11]] — vision-verify canonical pattern empirically confirmed by Willison
- [[davidsacks-anthropic-fable-5-export-control-jailbreak-2026-06-13]] — 2-day-later Sacks USG-export-control event affecting Fable 5 access
- [[gregisenberg-fable-5-ban-local-models-pivot-2026-06-13]] — operator-side local-models-pivot reaction
- [[anthropic-walks-back-sabotage-policy-2026-06-11]] — Anthropic walk-back same-day as this Willison post
- [[minchoi-fable-5-10-wild-examples-2026-06-12]] — community-showcase same-week sibling

## Verification-pending

- Willison primary article complete-content beyond Datasette-scrollbar case-study (post may have additional examples)
- Specific Datasette Agent + Datasette dependency-graph relationship
- Specific scrollbar-bug root-cause Fable identified
- Whether Willison's diagnostic-stack composition reproduces on Opus 4.8 / Sonnet 4.6 (counter-test)
- Specific Willison follow-up post-Sacks-export-control on continued-Fable-5 use
- Whether Willison publishes a structured Constraint-section template for future Fable 5 prompts
- Specific Datasette-Agent-scrollbar fix Fable proposed (the case-study's debug-stack composition is the load-bearing observation; the actual fix is verification-pending)
