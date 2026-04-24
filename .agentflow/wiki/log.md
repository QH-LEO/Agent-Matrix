# AgentFlow LLM Wiki Log

> Append-only maintenance record. New entries go at the top under this heading.

## 2026-04-24 update | Unify Agent Wiki orientation entrypoint

- Added `.agentflow/wiki/AGENT_ORIENTATION.md` as the single source of truth for Agent Wiki startup behavior.
- Changed `AGENTS.md`, `CLAUDE.md`, `.claude/skills/using-agentflow/SKILL.md`, and `.agentflow/compiled/leader.md` to point to the canonical orientation file instead of duplicating rules.

## 2026-04-24 init | Upgrade lightweight AgentFlow Wiki to LLM Wiki

- Created LLM Wiki directory contract: `raw/`, `schema/`, `overview/`, `entities/`, `concepts/`, `designs/`, `decisions/`, `queries/`, `reviews/`, `sources/`, `contradictions/`, `open-questions/`.
- Added schema, ingest/compile/lint/maintenance rules and page templates.
- Seeded first stable pages from existing project docs and code facts.
- Recorded path ambiguity: user mentioned `app-center/.agentflow/wiki` and `/Users/didi/Code/*/.agentflow/wiki`, while current workspace is `/Users/leo/Projects/agentflow-platform`.
