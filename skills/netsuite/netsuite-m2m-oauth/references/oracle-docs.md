# Oracle docs and version notes

NetSuite authentication behavior evolves. When web access is available, verify version-sensitive limits, supported algorithms, UI labels, certificate rotation behavior, and authentication changes against current Oracle NetSuite documentation before asserting them as current facts.

As of NetSuite 2026.1, Oracle documents a maximum of five active M2M certificates per Integration Record and provides a certificate-rotation endpoint. Treat those as lifecycle concerns after initial setup rather than expanding the main skill into a rotation workflow.

## Authoritative references

- Agent Skills specification: https://agentskills.io/specification
- Oracle SuiteCloud Agent Skills: https://github.com/oracle/netsuite-suitecloud-sdk/tree/master/packages/agent-skills
- NetSuite OAuth 2.0 overview: https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/chapter_157769826287.html
- Enable OAuth 2.0: https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/section_157771482304.html
- OAuth 2.0 roles: https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/section_157771510070.html
- Integration Record OAuth settings: https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/section_157771733782.html
- M2M mapping setup: https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/section_162686838198.html
- Certificate conditions: https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/subsect_162755332391.html
- Client assertion structure: https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/section_162790605110.html
- Token exchange: https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/section_162755359851.html
- Account-specific domains: https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/section_1498251763.html
