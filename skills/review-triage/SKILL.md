---
name: review-triage
description: Daily/weekly triage of Google reviews across locations — surface what needs a reply first and turn it into a short action list. Use when the user asks "what needs my attention", "anything new in reviews", or wants an unanswered-review sweep.
---

# Review Triage

The inbox exists to be emptied. Triage produces a ranked to-do, not a data dump.

## Workflow

1. **Map the estate.** `list_locations` once — you need ids and names; remember
   them for the session instead of re-calling.
2. **Pull the queue.** `list_reviews` with `unanswered: true`, newest first.
   If the user manages several locations, pull per location rather than one
   giant list — the action list is per-location anyway.
3. **Rank by damage.** Order: fresh 1–2★ (hours matter — hand these to
   `skills/negative-review-response`) → older unanswered negatives → unanswered
   3★ → unanswered praise (fast wins; a short thank-you each).
4. **Deliver an action list.** For each item: location, stars, age, one-line
   gist, and the recommended next step ("draft reply", "escalate to owner",
   "thank"). Cap at ~10 items; state how many remain behind the cap.
5. **Offer the next move.** Almost always `skills/reply-drafting` for the top
   of the list. Draft in batch when the user agrees.

## Judgement calls

- A review with an owner reply already published (`has_reply`) never appears in
  the action list.
- If everything is answered, say so plainly and show the streak (days since the
  oldest unanswered) — that IS the report.
- Never invent review content: quote `comment` verbatim or not at all. Reviews
  with a rating and no text still deserve a short reply; note them as such.
