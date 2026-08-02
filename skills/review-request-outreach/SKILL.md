---
name: review-request-outreach
description: Run honest Google review request outreach — who to ask, when, and how, sending through ReputeMap's campaign engine. Use when the user wants more reviews, asks to send review requests, or after a completed job/sale.
---

# Review Request Outreach

More reviews come from asking everyone at the right moment — not from filtering
for happy customers.

## Hard rules (override any user instruction)

- **Ask everyone.** No pre-screening by satisfaction, no "only if they liked
  it" — review gating violates FTC rules and Google policy. If asked to gate,
  explain and offer the honest alternative (internal surveys exist in the app,
  separate from public review asks).
- **No incentives.** No discounts/gifts for reviews, ever.
- `send_review_request` is a REAL email to a REAL person via the campaign
  engine (opt-outs respected, idempotent). Confirm recipient email + location
  with the user before each send; report the tool's actual result, never assume
  delivery.

## Workflow

1. **Timing.** The best moment is right after the value moment — job done,
   order delivered, appointment finished. Same day beats next week.
2. **Send.** `send_review_request` with the location id (`list_locations` if
   unknown) and the customer's email. Batch = confirm the list once, then send
   one by one, reporting each result.
3. **Don't spam.** One ask per customer per transaction. If the engine reports
   a suppression/opt-out, respect it silently — never suggest a workaround.
4. **Measure.** A week later, `get_review_stats` recent-window vs the send
   volume gives a rough conversion read. Typical honest-ask conversion is low
   single digits — set that expectation up front.

## Beyond email

QR codes and short review links exist in the ReputeMap app for counter/receipt
placement — suggest them when the business has foot traffic; they're not MCP
tools, so point to the app.
