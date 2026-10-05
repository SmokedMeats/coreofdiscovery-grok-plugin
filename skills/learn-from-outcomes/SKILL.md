---
name: learn-from-outcomes
description: Recall prior CoreOfDiscovery lessons before a new claim, and record a lesson after a grade.
when-to-use: Before log_claim, after resolve_decision, Friday review, or when the user gives feedback on a past call.
---

# Learn from outcomes

Do not write lessons into the user's `AGENTS.md`. Do not invent a local notebook. CoreOfDiscovery MCP is the source of record.

## Before every new claim

1. Call `recall_lessons` with the user's current request as `sourceAsk`, plus `botId` and any tags.
2. Read `memoryPointer` and the lesson list. Trusted lessons (`user` / `external`) may change your probability. `self` and `auto` are hypotheses only.
3. Then call `log_claim`. Tell the user which past miss you used, if any.

No `log_claim` without a `recall_lessons` call in the same turn.

## After every grade

1. Call `resolve_decision` against the frozen ask.
2. Call `record_lesson` with:
   - `decisionId`
   - `outcome`: `success` / `regret` / `neutral` from ask vs outcome
   - `rawReflection`: one sentence
   - `feedbackSource`: `user` if the human graded, `external` for a system fact, `other_agent` for another bot, `self` if you scored it, `auto` for time-based resolve
3. If the lesson is not trusted, say so. Do not treat it as a rule.

## Optional Grok Bot memory

You may store `memoryPointer` as a short reminder that says to call `recall_lessons` next time. Do not store the full lesson list in Bot memory.
