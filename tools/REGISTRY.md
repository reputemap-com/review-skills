# Tool Registry

Which skill calls which ReputeMap MCP tool, and what each costs.

Hosted server: `https://api.reputemap.com/mcp` (Streamable HTTP,
`Authorization: Bearer rmk_...`). REST mirror for scripts:
`https://api.reputemap.com/api/v1/*` — same key, same credit meter
(1,000 credits/month per org; 60 requests/minute).

## Capability matrix

| Skill | list_locations | list_reviews | get_review_stats | send_review_request | get_usage |
|---|:-:|:-:|:-:|:-:|:-:|
| review-triage | ● | ● | | | |
| reply-drafting | ○ | ● | | | |
| negative-review-response | ○ | ● | | | |
| reputation-report | ○ | ● | ● | | |
| review-request-outreach | ● | | ○ | ● | |
| reputation-audit | ● | ● | ● | | |

● primary · ○ occasional. `get_usage` is free and available to every skill for
credit checks. Every other call costs 1 credit.

## Boundaries

- Data covers the org's OWN connected locations — no competitor lookups.
- No publish tool: reply drafts are published by a human from the ReputeMap
  inbox.
- `send_review_request` is the single write action; it respects opt-outs and
  is idempotent.
