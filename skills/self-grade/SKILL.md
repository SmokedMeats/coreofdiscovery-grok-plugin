---
name: self-grade
description: Grade a logged claim against the frozen original ask, not a rewritten story.
when-to-use: A claim is due, the user asks what happened, or an outside fact landed.
---

# Grade against the frozen ask

1. Call `list_open_claims` (use `overdueOnly: true` when checking due items).
2. Load the frozen ask from the tool. Do not replace the title, ask, or criteria.
3. Add only what happened.
4. Call `resolve_decision` with:
   - `decisionId`
   - `outcomes` on the original prediction ids
   - `observedOutcome` — the fact
   - `graderKind`: `external` if a user or system fact, `other_agent` if another bot, `self` if you are marking it

Self-grade is a claim, not a full-weight score. If you want to change the ask, log a new claim. Do not resolve a rewritten one.

Then call `record_lesson` (`feedbackSource` matches who graded). Self-lessons are untrusted.

Tell the user the compare line: You asked / I said / What happened / Grade / who graded.
