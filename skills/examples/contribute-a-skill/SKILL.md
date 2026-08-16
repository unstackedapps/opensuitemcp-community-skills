---
name: contribute-a-skill
description: Add a community skill to the OpenSuiteMCP pack. Use when the user wants to write, structure, or submit a SKILL.md.
---

# Contribute a community skill

This pack is `unstackedapps/opensuitemcp-community-skills`. One skill = one folder = one `SKILL.md`.

## Folder

```text
skills/<bucket>/<skill-name>/SKILL.md
```

`<skill-name>` is kebab-case and **must** match frontmatter `name`.

Buckets:

- `netsuite` — ERP workflows
- `mcp` — AI Connector, MCP Standard Tools, Companion
- `suitescript` — SuiteScript / SDF
- `examples` — templates
- `in-progress` — drafts (do not list in the root README or plugin.json)

## Frontmatter

```yaml
---
name: kebab-case-id
description: What it does, and when to reach for it. One or two sentences.
---
```

Keep `description` under ~280 characters. OpenSuiteMCP reads `name` and `description` the same way it reads Oracle skills.

## Body

Write instructions for an agent:

- When to use the skill
- Which MCP tools or reports to prefer
- What not to do (SuiteQL vs standard reports, account-specific data, secrets)

Do not paste Oracle documentation wholesale. Link out. Do not include customer data.

## After the file exists

1. Link it from `skills/<bucket>/README.md`
2. If promoted, link it from the root `README.md` Reference section and add the folder path to `.claude-plugin/plugin.json` `skills`
3. Open a pull request
