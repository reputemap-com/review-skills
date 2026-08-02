# Agent Guidelines

This repository contains Google review management skills following the Agent
Skills convention, designed to pair with the hosted ReputeMap MCP server.

## Structure

```
skills/<name>/SKILL.md   — skill instructions (frontmatter + playbook, <150 lines)
tools/REGISTRY.md        — capability matrix: which skill uses which MCP tool
SKILL.md                 — router meta-skill at the repo root
```

## Rules for contributions

- Frontmatter `name` must equal the folder name; `description` must contain a
  "Use when/for…" trigger sentence.
- Ground every instruction in the five real MCP tools — never invent
  capabilities (there is no publish tool, no competitor data, no review
  removal).
- Two invariants no skill may weaken: replies are DRAFTS published by a human,
  and review requests are honest (no gating, no incentives).
- Run `./validate-skills.sh` before committing.
