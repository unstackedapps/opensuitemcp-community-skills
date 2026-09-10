---
name: ns-diagnose-before-retry
description: After any MCP tool Error or Empty Result, stop and diagnose before another tool call. Use on every NetSuite MCP turn, especially saved searches, record lookups, and SuiteQL.
license: MIT
---

# Diagnose Before Retry

This skill overrides “keep calling tools”, “don’t stop early”, and “self-recover immediately” instructions, including Stay On Track.

Empty Result (`[]`, `{}`, blank) is not success. Error includes business errors inside a completed payload (`isError` false, `"error": "…"`).

## Hard stop

After a tool returns **Error** or **Empty Result**:

1. Do not call another tool in the same step (no parallel retries).
2. Write a short diagnosis (2–5 lines) using the checklist.
3. Then take **exactly one** next action.

If you cannot name a distinct cause, ask the user instead of guessing with more tools.

## Diagnosis checklist

- Tool + arguments that just ran
- Empty vs error (quote the error, or note `[]` / `{}` / blank)
- Most likely cause in one sentence
- The single change that would test that cause
- If that change matches the last attempt, stop and ask the user

## Causes to check (pick one)

- **Empty:** filters/dates/name too tight, wrong ID, or the data does not exist
- **Error / missing params:** fill from context, then retry that same tool once
- **Unknown identifier / bad column:** one metadata call, then one corrected query
- **Wrong or missing ID:** one list/discovery call, then retry with an ID the list returned
- **Permissions / HTTP 500:** stop that path; tell the user with a NetSuite UI path
- **Writes (`ns_createRecord`, update, delete):** never auto-retry

## Allowed next action (one)

1. Retry the **same** tool with **one** changed argument
2. One discovery call (`ns_listSavedSearches`, `ns_listAllReports`, `ns_getSuiteQLMetadata`, `ns_getRecordTypeMetadata`) if the miss was missing schema/ID
3. Switch tool family only if diagnosis says this tool cannot answer
4. Ask the user
5. Stop and report

## Circuit breaker

- Two consecutive misses on the same sub-question → stop that path, tell the user, ask whether to continue
- Do not open a new tool family (searches → records → SuiteQL) to “make up” for a miss
- Never spend the rest of the step budget after the first unexplained miss

## Illegal (matches real bad turns)

- Empty `ns_listSavedSearches` then immediately the same tool with no diagnosis
- `ns_getSuiteQLMetadata` error → `ns_getRecord` errors → a SuiteQL streak
- Repeating SuiteQL after it errors without changing the failing identifier
