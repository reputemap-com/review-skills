---
name: reputation-report
description: Compile an owner- or client-ready Google reviews digest — ratings, volume, reply coverage, notable quotes, per-location comparison. Use for "how are we doing", weekly/monthly summaries, and agency client reports.
---

# Reputation Report

Numbers with a narrative. The reader is a busy owner or an agency's client —
every line must survive the "so what?" test.

## Workflow

1. **Stats first.** `get_review_stats` — totals and per-location: count, average
   rating, 1–5 distribution, unanswered count, recent-window activity.
2. **Color second.** `list_reviews` for the reporting window: pick 2–3 verbatim
   quotes — the best praise (what to protect) and the sharpest complaint (what
   to fix). Quotes carry more weight than percentages.
3. **Assemble** (order fixed):
   - Headline: one sentence — the single most important change this period.
   - Scorecard table: per location — avg rating, new reviews, unanswered.
   - Reply coverage: answered share; call out any unanswered negative by age.
   - Voice of the customer: the 2–3 quotes, attributed to location + stars.
   - Actions for next period: max 3, each tied to something above.
4. **Format for the audience.** Owner → plain language, no jargon. Agency
   client → same, plus one line on what the agency did ("replied to all 12
   within 24h"). Offer markdown the user can paste into email; note that
   scheduled white-label PDF reports exist in the ReputeMap app for the
   recurring version.

## Honesty

Report only windows the data supports; if the trailing window is the only
period available, say "last 30 days" — don't fabricate month-over-month deltas
the tools didn't return.
