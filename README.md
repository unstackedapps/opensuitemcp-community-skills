# OpenSuiteMCP Community Skills

Community `SKILL.md` pack for [OpenSuiteMCP](https://github.com/unstackedapps/opensuitemcp) — extra instructions agents can load on top of Oracle’s SuiteCloud Agent Skills.

This repo is the public SoT for **community** skills. OpenSuiteMCP will sync it the same way it syncs Oracle’s pack (opt-in toggles in the Skills panel). You can also install the files into any agent that understands Agent Skills.

Layout follows [mattpocock/skills](https://github.com/mattpocock/skills): one folder per skill, grouped into buckets.

```text
skills/
  <bucket>/
    <skill-name>/
      SKILL.md
```

## Install

**OpenSuiteMCP** — coming soon as a third source in the Skills panel (Oracle / You / Community). Watch [opensuitemcp.com/docs/skills](https://opensuitemcp.com/docs/skills).

**Other agents** (Cursor, Claude Code, Codex):

```bash
npx skills@latest add unstackedapps/opensuitemcp-community-skills
```

## Reference

These split on one axis — **promoted** buckets are listed here and shipped in `.claude-plugin/plugin.json`. Drafts live in `in-progress/` until they move.

### Examples

- **[contribute-a-skill](./skills/examples/contribute-a-skill/SKILL.md)** — How to add a skill to this pack (frontmatter, buckets, review bar).

### NetSuite

_None yet. PRs welcome._

### MCP

_None yet. PRs welcome — AI Connector, MCP Standard Tools, Companion SuiteApp._

### SuiteScript

_None yet. PRs welcome._

## Related

- Product: [unstackedapps/opensuitemcp](https://github.com/unstackedapps/opensuitemcp)
- Community prompts: [unstackedapps/opensuitemcp-community-prompts](https://github.com/unstackedapps/opensuitemcp-community-prompts)
- Oracle pack: [SuiteCloud Agent Skills](https://github.com/oracle/netsuite-suitecloud-sdk/tree/master/packages/agent-skills)

## License

MIT. Contributions are accepted under the same license. See [CONTRIBUTING.md](./CONTRIBUTING.md).
