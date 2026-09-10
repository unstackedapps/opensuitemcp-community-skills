Skills are organized into bucket folders under `skills/`:

- `opensuitemcp/` — product-level chat behavior and agent policy (not NetSuite-specific)
- `netsuite/` — ERP, `ns_*` tools, connector setup, and SuiteScript until a split is warranted
- `in-progress/` — public drafts; not listed as shipped until moved

Do not add empty buckets (`mcp`, `suitescript`, `examples`, …). Create a bucket when the first skill lands.

Every skill lives at `skills/<bucket>/<skill-name>/SKILL.md` with YAML frontmatter:

```yaml
---
name: kebab-case-id
description: One or two sentences. What it does and when to use it.
license: MIT
---
```

## Naming

Folder name, frontmatter `name`, and the OpenSuiteMCP slug are the **same** string. Sync is flat (leaf folder only), so `name` must be unique across the pack.

| Kind | Pattern | Example |
| --- | --- | --- |
| Product chat / policy | `<job>` | `get-to-the-point` |
| NetSuite ERP / setup | `netsuite-<topic>` | `netsuite-m2m-oauth` |
| `ns_*` tool policy | `ns-<topic>` | `ns-stay-on-track` |

- kebab-case, lowercase, hyphens
- Do not prefix product skills with `opensuitemcp-`
- Do not use an `mcp-` prefix; NetSuite MCP tools are `ns-*` under `netsuite/`
- `description`: **what** and **when**, under ~280 characters

## Promoted vs draft

Promoted buckets (`opensuitemcp`, `netsuite`, and any later bucket that has a shipped skill) must have:

1. A `README.md` in the bucket listing every skill (name linked to `SKILL.md`, one-line description)
2. An entry in the top-level `README.md` Reference section
3. An entry in `.claude-plugin/plugin.json` `skills` array

`in-progress/` skills must **not** appear in the root README or plugin manifest.

Do not vendor Oracle’s SuiteCloud Agent Skills here. That pack is synced separately from `oracle/netsuite-suitecloud-sdk`.
