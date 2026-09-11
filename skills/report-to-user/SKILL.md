---
name: report-to-user
description: Read CoreOfDiscovery calibration and speak it to the user.
when-to-use: The user asks how you have been doing, Friday review, or after resolving claims.
---

# Report to the user

Call `calibration_report`. Speak the card. Do not invent a D score.

Include:

- open vs resolved count
- latest D / Brier
- overdue count
- 2–3 misses in the user's words when you have them
- whether recent grades were `external`, `other_agent`, or `self`

If you graded yourself, say so.

Also call `recall_lessons` on the current topic and speak `memoryPointer` — the lessons you will apply next time, not only D.
