---
name: mcp-stay-on-track
description: Keeps NetSuite MCP work on one path and conserves tokens. Use when calling ns_* tools, after a failed or unhelpful result, or when about to switch tools or invent a new angle. Pause, tell the user, and wait instead of looping until max iterations.
license: MIT
---

# Stay on track

While this skill is enabled, these rules are mandatory for every persona. They override default error recovery, “do not stop early,” and any playbook that would keep issuing MCP calls after a miss.

This skill does not teach which NetSuite tool to prefer. It teaches when to stop spending tokens and check in.

## Job

The harness often cannot recover from a live NetSuite miss. Two starts:

1. The MCP call fails (transport, unknown or truncated name, or a business error inside a Completed payload).
2. The call succeeds but the result does not answer the question, or it only points at a different object, report, or search.

Do not hop to another tool or theory to “get back on track.” That oscillation burns tokens and ends at the step-limit lock. Notice you are off course, stop, and tell the user.

**One path, one same-tool fix, then check in.**

## Call only real tools

- Call only names listed in this session’s connected MCP tools.
- Never invent an `ns_*` name. Never call a truncated name (`ns_`, `ns_run`).
- If the intended tool is not connected, say so. Do not guess a neighbor name.

## One path

- One intended retrieval path per user turn (discover → one execute). Not a tour of every tool class.
- At most one distinct fix on the **same** tool (missing dates, period, or subsidiary; or replace an invented ID with an exact ID from a list that already ran).
- Treat an unhelpful success as a failure: no asked-for facts, or only a tangent to chase.
- Every extra MCP call costs tokens and usually does not recover the harness. Prefer a short check-in over another tool.

## Reality check

Before a second approach, a different tool class, or a “this might help” call, stop and tell the user:

- what you tried
- what came back or failed
- why that does not answer their question
- that you are stuck, or that you want to try one specific other tool
- **one** choice: approve that tool, change a filter, or stop

Wait. Do not silently switch.

## No more MCP calls this turn

Stop calling tools when any of these is true:

- unknown, truncated, or invented tool name
- same error text or same missing field after the one fix
- permission, auth, or tool-not-available
- write tools (`ns_createRecord`, `ns_updateRecord`, deletes) — never auto-retry
- result does not answer the question (wrong grain, empty, or a tangent)
- already switched approach once this turn
- about to call a tool because the last result “might” help
- three MCP calls this turn and no answer in hand

Parse tool `content` even when the call looks Completed. A payload `error` counts as failure.

A short honest stop is success. Hitting the step-limit lock is not.
