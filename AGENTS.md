Skills are organized into bucket folders under `skills/`:

- `examples/` — templates and how-to skills for contributing
- `netsuite/` — ERP workflows (A/R, inventory, saved searches, reports)
- `mcp/` — NetSuite AI Connector, MCP Standard Tools, Companion SuiteApp
- `suitescript/` — SuiteScript, SDF, and customization guidance
- `in-progress/` — public drafts; not listed as shipped until moved

Every skill lives at `skills/<bucket>/<skill-name>/SKILL.md` with YAML frontmatter:

```yaml
---
name: kebab-case-id
description: One or two sentences. What it does and when to use it.
---
```

Promoted buckets (`examples`, `netsuite`, `mcp`, `suitescript`) must have:

1. A `README.md` in the bucket listing every skill (name linked to `SKILL.md`, one-line description)
2. An entry in the top-level `README.md` Reference section
3. An entry in `.claude-plugin/plugin.json` `skills` array

`in-progress/` skills must **not** appear in the top-level README or plugin manifest.

Do not vendor Oracle’s SuiteCloud Agent Skills here. That pack is synced separately from `oracle/netsuite-suitecloud-sdk`.
