---
title: "Claude API versions, and Migrating to API version 2026-10-21"
type: source
medium: article
url: https://platform.claude.com/docs/en/api/migration-2026-10-21
ingested: 2026-10-25
---

## Summary

Anthropic's API docs (the [versions page](https://platform.claude.com/docs/en/api/versioning) and the migration guide, both read as raw page text on 2026-10-25). They confirm a claim the wiki had only secondhand, from [[openai-patch-the-planet-php2shell-2026-10-22|Latent Space AINews]]: **API version `2026-10-21` removes `temperature`, `top_p` and `top_k` from the Messages API.** It's the first new API version since `2023-06-01`. **Nothing breaks until you opt in.** The version is set by the `anthropic-version` header, and an SDK sends whichever version was current when its major version shipped. The break arrives when you upgrade the SDK to a new major (Python `anthropic` 2.0.0).

## Key Claims / Takeaways

- **The removal:** *"The `temperature`, `top_p`, and `top_k` request parameters are removed. A request that sends any of them returns a 400 error on every model."* It errors *"even at the parameter's default value."*
- **Who loses anything:** *"Models that already accept only the defaults, such as Claude 4.7 and later models, sample as before. On models that accept other values, such as Claude Sonnet 4.6, a request that lowered temperature for more consistent output loses that effect. No other setting replaces it."* So for current models it's a code cleanup. Only older models lose a real control.
- **The escape hatch:** *"If a request relies on a non-default value, either stop sending the parameter, or keep that request on 2023-06-01."*
- **How the break arrives:** *"If you use an SDK, your requests use the API version that was current when your SDK's major version was released."* For Python: *"Upgrade the anthropic package to version 2.0.0."* *"Earlier SDK and CLI versions sent anthropic-version: 2023-06-01 with every request."* The new SDKs drop the three parameters from their types.
- **The same version's other breaks:**
  - *"A request that places a `document` block directly in an `assistant` message returns a 400 error."*
  - A user-message `text` block with *"a non-empty `citations` array"* returns a 400.
  - Several Admin API and Enterprise Analytics field renames: `roles` → `role_ids`, `group_id` → `rbac_group_id`, `name` → `display_name`, `group_type` → `group.type`, `workspace_id` → `scope.workspace_id`, `actor.email` → `actor.email_address`, `summaries` → `data`.
- **Bedrock:** *"On Amazon Bedrock, it's available for Claude 4.7 and later models."*
- **Version policy, unchanged:** *"For any given API version, Anthropic preserves: Existing input parameters"* (the first item of a list).

## Pages Updated

- [[anthropic]]: Traction Signals
- [[openai-patch-the-planet-php2shell-2026-10-22]]: the secondhand claim marked confirmed
