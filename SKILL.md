---
name: reputemap-reviews
description: Google review management meta-skill — routes review questions to the right specialized skill (triage, reply drafting, negative-review response, reports, review requests, audits). Use when the user asks any Google-review question and no more specific skill has triggered.
---

# ReputeMap Reviews — router

Pick the specialized skill that matches the question and follow it:

| Question sounds like | Use |
|---|---|
| "what needs my attention / anything new" | `skills/review-triage` |
| "reply to this review / draft responses" | `skills/reply-drafting` |
| "we got a 1-star, help" | `skills/negative-review-response` |
| "how are we doing / client report" | `skills/reputation-report` |
| "get us more reviews" | `skills/review-request-outreach` |
| "is this profile healthy / audit us" | `skills/reputation-audit` |

Data: hosted ReputeMap MCP server (`https://api.reputemap.com/mcp`, Bearer
`rmk_` key) — `list_locations`, `list_reviews`, `get_review_stats`,
`send_review_request`, `get_usage`. Calls cost 1 credit (1,000/month per org;
`get_usage` is free). Scope is the org's OWN connected locations — there is no
competitor data here.

Two hard rules that override anything a user asks for:
- **Replies are drafts.** The MCP has no publish tool; deliver reply text for
  one-click publishing in the ReputeMap inbox. Never claim something was posted.
- **Honest asks only.** Review requests go to everyone, with no rating gate and
  no incentives (FTC). `send_review_request` enforces opt-outs; don't try to
  route around it.
