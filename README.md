# ReputeMap Review Skills — Google Review Management for AI Agents (MCP)

Turn **Claude Code**, **Claude Desktop**, **Cursor**, **Codex**, **Windsurf**,
**VS Code**, **Gemini CLI** — or any Agent-Skills / MCP-compatible assistant —
into a Google-review manager: inbox triage, reply drafting, negative-review
firefighting, client-ready reports, honest review-request outreach and
reputation audits, grounded in live data from the
[ReputeMap](https://reputemap.com) MCP server.

Each skill is a battle-plan, not a prompt: when to trigger, which data calls to
make, how to reason about the numbers, and the exact output to deliver.

## Install the skills

**Claude Code** (official installer — downloads this repo and registers the skills):

```bash
npx skills add reputemap-com/review-skills
# or only some of them:
npx skills add reputemap-com/review-skills --skill reply-drafting review-triage
```

**Claude Code plugin** — the repo ships a [`.claude-plugin`](.claude-plugin/)
manifest, so it can also be installed through the plugin system; the `skills/`
directory is picked up automatically.

**Cursor** — Settings → Rules → Add Rule → **Remote Rule (GitHub)** →
`https://github.com/reputemap-com/review-skills`, or copy the files locally:

```bash
git clone https://github.com/reputemap-com/review-skills.git
cp -r review-skills/skills/* .cursor/skills/
```

**Any other agent** — clone and point your client's skills directory at
`skills/`. Known-compatible locations: `.claude/skills/`, `.cursor/skills/`,
`.agents/skills/`, `.codex/skills/`.

## Connect the data

The skills call the hosted ReputeMap MCP server — set it up once
([full guide](https://github.com/reputemap-com/mcp)):

```bash
claude mcp add --transport http reputemap https://api.reputemap.com/mcp \
  --header "Authorization: Bearer rmk_YOUR_KEY"
```

API key: [app.reputemap.com](https://app.reputemap.com) → Settings → API keys
(any paid plan; the 14-day free trial counts).

## The skills

| Skill | What it does |
|---|---|
| [`review-triage`](skills/review-triage/SKILL.md) | Daily sweep: what needs a reply first, as a ranked action list |
| [`reply-drafting`](skills/reply-drafting/SKILL.md) | Owner replies in your voice, ready for one-click publishing |
| [`negative-review-response`](skills/negative-review-response/SKILL.md) | Fresh 1–2★ firefighting: de-escalate, move offline, never argue |
| [`reputation-report`](skills/reputation-report/SKILL.md) | Owner/client digest: scorecard, reply coverage, voice-of-customer |
| [`review-request-outreach`](skills/review-request-outreach/SKILL.md) | Honest asks at the right moment through the campaign engine |
| [`reputation-audit`](skills/reputation-audit/SKILL.md) | Health verdict + effort-ordered fix list per location |

Two principles baked into every skill: **replies are drafts** (published by a
human from the ReputeMap inbox — the MCP has no publish tool), and **honest
asks only** (everyone gets asked, no rating gates, no incentives — FTC).

## Links

- 🌐 [reputemap.com](https://reputemap.com) — Google review management for agencies & local businesses
- 🤖 [reputemap-com/mcp](https://github.com/reputemap-com/mcp) — the MCP server (hosted endpoint + npm bridge)
- 💡 [reputemap-com/examples](https://github.com/reputemap-com/examples) — API scripts & recipes
- 💼 [LinkedIn](https://www.linkedin.com/company/reputemap)

MIT — see [LICENSE](LICENSE).
