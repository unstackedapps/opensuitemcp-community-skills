# Contributing

Thank you. This pack is how the OpenSuiteMCP community shares `SKILL.md` files that Ava (and other agents) can load.

## What belongs here

- Repeatable guidance written for an agent (product chat behavior or NetSuite work)
- Small, composable skills — one job per folder
- Public knowledge (no customer data, no internal IDs, no credentials)

Do **not** copy Oracle’s SuiteCloud Agent Skills into this repo. Point at them; don’t vendor them.

Contributor how-to lives in this file and `AGENTS.md`. It is not a shipped skill.

## Add a skill

1. Pick a bucket: `opensuitemcp` (product chat / policy) or `netsuite` (ERP, `ns_*` tools, connector, SuiteScript). Use `in-progress/` if it is still a draft. Add a **new** bucket only when the first skill for that domain lands — do not create empty folders.
2. Create `skills/<bucket>/<skill-name>/` where `<skill-name>` is kebab-case, **unique across the pack**, and matches frontmatter `name`. See naming in `AGENTS.md`.
3. Add `SKILL.md`:

```yaml
---
name: kebab-case-id
description: What it does, and when to reach for it. One or two sentences.
license: MIT
---
```

Keep `description` under ~280 characters.

4. Link it from `skills/<bucket>/README.md` and, if it is promoted, from the root `README.md` and `.claude-plugin/plugin.json`.
5. Open a pull request.

## Review bar

- Frontmatter `name` matches the folder and is unique across the repo
- Description says **what** and **when**, in one or two sentences
- Body is instructions for an agent, not a blog post
- No secrets, no account-specific numbers, no copyrighted Oracle docs pasted wholesale
