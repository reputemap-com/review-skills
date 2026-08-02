---
name: reputation-audit
description: Assess how healthy a Google Business Profile's review presence is and produce a prioritized fix list. Use when the user asks "audit our reviews", "why is our rating stuck", or evaluates a new client/location onboarding.
---

# Reputation Audit

An audit is a verdict with evidence, not a tour of the dashboard.

## Signals and thresholds

Pull `get_review_stats` + a `list_reviews` sample per location, then score:

| Signal | Healthy | Warning |
|---|---|---|
| Average rating | ≥ 4.5 | < 4.3 — visibly costs clicks vs neighbors |
| Reply coverage | ~100% of negatives, most positives | any unanswered negative older than a week |
| Recency | new reviews within ~30 days | silence for 90+ days reads as closed/inactive |
| Volume | double digits and growing | < 10 total — every single review swings the average |
| Distribution | 1★ share small vs 5★ | a fat 1–2★ tail with no owner replies |

## Workflow

1. Score each location against the table; quote the 1–2 worst unanswered
   negatives as evidence (verbatim, dated).
2. **Verdict per location**: healthy / needs attention / looks unmanaged — with
   the two signals that drove it.
3. **Fix list, effort-ordered:** (a) answer the negative backlog
   (`skills/reply-drafting` — same week); (b) restart the ask habit
   (`skills/review-request-outreach`); (c) standing rhythm — triage weekly
   (`skills/review-triage`), report monthly (`skills/reputation-report`).
4. **Scope honestly.** The tools see the org's connected locations only. For a
   prospect not yet in ReputeMap, say the audit needs the profile connected
   first (2 minutes in the app) — don't estimate from memory or the open web.
