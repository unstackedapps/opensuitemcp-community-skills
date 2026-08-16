# Contributing

Thank you. This pack is how the OpenSuiteMCP community shares `SKILL.md` files that Ava (and other agents) can load.

## What belongs here

- Repeatable NetSuite / MCP / SuiteScript guidance written for an agent
- Small, composable skills — one job per folder
- Public knowledge (no customer data, no internal IDs, no credentials)

Do **not** copy Oracle’s SuiteCloud Agent Skills into this repo. Point at them; don’t vendor them.

## Add a skill

1. Pick a bucket under `skills/` (`netsuite`, `mcp`, `suitescript`, or `examples`). Use `in-progress/` if it is still a draft.
2. Create `skills/<bucket>/<skill-name>/` where `<skill-name>` is kebab-case and matches frontmatter `name`.
3. Add `SKILL.md` with `name` and `description` frontmatter. Copy `skills/examples/contribute-a-skill/SKILL.md`.
4. Link it from `skills/<bucket>/README.md` and, if it is promoted, from the root `README.md` and `.claude-plugin/plugin.json`.
5. Open a pull request.

## Review bar

- Frontmatter `name` is unique across the repo
- Description says **what** and **when**, in one or two sentences
- Body is instructions for an agent, not a blog post
- No secrets, no account-specific numbers, no copyrighted Oracle docs pasted wholesale
