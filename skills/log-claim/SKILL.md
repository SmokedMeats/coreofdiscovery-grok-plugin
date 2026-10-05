---
name: log-claim
description: Log a CoreOfDiscovery claim before you state a date, probability, or recommendation you cannot look up now. Triggers: ship Friday, ETA, ~70%, this should work, I think, forecast, /log-claim.
when-to-use: You are about to assert something a later fact could grade true or false, and you cannot verify it from current context.
---

# Log a claim

A **claim** is a judgement a later observer can mark true or false without rewriting the ask.

## Test

Log when both are true:

1. A later fact could grade this true or false.
2. You cannot verify it from current context.

Lookups, tastes, and already-frozen asks stay spoken only.

## Steps

1. Run the test. Done when you know log vs speak-only.
2. Follow `learn-from-outcomes` (`recall_lessons` on this `sourceAsk`). Done when recall returns.
3. Call `log_claim` with:
   - `sourceAsk` — the user's original request, quoted
   - `claim` — what you are about to say will happen
   - `probability` — 0..1
   - `outcomeCriteria` — done-when, prefer `metric >= target by YYYY-MM-DD`
   - `resolvesAt` — when to check
   - `nominatedBy` — `user` if they asked to track it, else `bot`
   - `botId` — stable id, e.g. `grok-4`
   Done when the freeze returns.
4. Read the freeze back, then speak the claim. Books are CoreOfDiscovery MCP at `https://coreofdiscovery.vercel.app/api/mcp`. If the call is unauthorized, follow `connect`.
