# OpenSuiteMCP Community Skills

Community `SKILL.md` pack for [OpenSuiteMCP](https://github.com/unstackedapps/opensuitemcp) — extra instructions agents can load on top of Oracle’s SuiteCloud Agent Skills.

This repo is the public SoT for **community** skills. OpenSuiteMCP will sync it the same way it syncs Oracle’s pack (opt-in toggles in the Skills panel). You can also install the files into any agent that understands Agent Skills.

Layout follows [mattpocock/skills](https://github.com/mattpocock/skills): one folder per skill, grouped into buckets.

```text
skills/
  opensuitemcp/          product chat / policy
    get-to-the-point/
  netsuite/             ERP, ns_* tools, connector, SuiteScript
    netsuite-m2m-oauth/
    ns-stay-on-track/
  in-progress/           drafts (not shipped)
```

OpenSuiteMCP syncs leaf folders (except `in-progress/`). The bucket is for humans; the slug must be unique across the pack. Naming rules are in `AGENTS.md`.

## Install

**OpenSuiteMCP** — coming soon as a third source in the Skills panel (Oracle / You / Community). Watch [opensuitemcp.com/docs/skills](https://opensuitemcp.com/docs/skills).

**Other agents** (Cursor, Claude Code, Codex):

```bash
npx skills@latest add unstackedapps/opensuitemcp-community-skills
```

## Reference

Promoted skills are listed here and shipped in `.claude-plugin/plugin.json`. Drafts live in `in-progress/` until they move.

### OpenSuiteMCP

- **[get-to-the-point](./skills/opensuitemcp/get-to-the-point/SKILL.md)** — Raw answers only; no preamble, hedging, or follow-up offers.

### NetSuite

- **[netsuite-m2m-oauth](./skills/netsuite/netsuite-m2m-oauth/SKILL.md)** — NetSuite OAuth 2.0 Client Credentials (M2M) setup and verification for REST, RESTlets, and SuiteAnalytics Connect.
- **[ns-stay-on-track](./skills/netsuite/ns-stay-on-track/SKILL.md)** — One NetSuite `ns_*` path per turn; pause, tell the user, and wait instead of looping until max iterations.

## Related

- Product: [unstackedapps/opensuitemcp](https://github.com/unstackedapps/opensuitemcp)
- Community prompts: [unstackedapps/opensuitemcp-community-prompts](https://github.com/unstackedapps/opensuitemcp-community-prompts)
- Oracle pack: [SuiteCloud Agent Skills](https://github.com/oracle/netsuite-suitecloud-sdk/tree/master/packages/agent-skills)

## License

MIT. Contributions are accepted under the same license. See [CONTRIBUTING.md](./CONTRIBUTING.md).
