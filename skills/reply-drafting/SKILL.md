---
name: reply-drafting
description: Draft owner replies to Google reviews in the business's voice — ready for one-click publishing from the ReputeMap inbox. Use when the user asks to reply to a review, answer reviews in bulk, or wants reply templates in their tone.
---

# Reply Drafting

A reply is written for the NEXT customer reading it, not for the reviewer.

## Ground rules

- **Drafts only.** The MCP has no publish tool. Deliver text; the user publishes
  from the ReputeMap inbox (or the app's AI-draft flow). Never say "posted".
- Match the business's voice: if prior replies exist (`list_reviews` includes
  published reply text), mirror their register; otherwise ask one question —
  "warm, short, or formal?" — and default to warm.
- Never: argue, blame the customer, deny their experience, disclose personal or
  order details, offer discounts-for-changing-the-review (that's an incentive —
  prohibited), or paste boilerplate identical across reviews.

## Structure by rating

- **5★ with text** — 2–3 sentences: thank by name, reflect ONE specific detail
  they praised (proof a human read it), a light welcome-back. Vary openings
  across a batch; no two drafts should start identically.
- **5★ no text** — one warm sentence. Done.
- **3–4★** — thank, acknowledge the specific friction, state one concrete thing
  being done about it, invite them back. No defensiveness.
- **1–2★** — use `skills/negative-review-response`; its structure overrides
  this one.

## Workflow

1. Pull the target reviews (`list_reviews`, usually `unanswered: true`).
2. Draft per review; naturally mention the service/city ONLY where it fits —
   one keyword-bearing phrase max, never stuffed.
3. Present as a numbered list: review gist → draft. Ask which to adjust; offer
   tone variants (shorter / warmer / more formal) on request.
