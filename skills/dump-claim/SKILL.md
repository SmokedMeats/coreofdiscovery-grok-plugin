---
name: dump-claim
description: Log a relevant claim so it can be graded later against the original ask.
when-to-use: The user or you just made a prediction, commit, or "I think X will happen" that should be remembered.
---

# Dump a claim

Call CoreOfDiscovery MCP `dump_claim`. Do not invent a second notebook.

Required fields:

- `sourceAsk` — the user's original request, quoted. Not your later summary.
- `claim` — what you said would happen.
- `probability` — 0..1.
- `outcomeCriteria` — done-when, prefer `metric >= target by YYYY-MM-DD`.
- `resolvesAt` — when to check.
- `nominatedBy` — `user` if they asked to track it, else `bot`.
- `botId` — stable id, e.g. `grok-4`.

After the tool returns, repeat the frozen ask back to the user. That freeze is the only thing you may grade later.
