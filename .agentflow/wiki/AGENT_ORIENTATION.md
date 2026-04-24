# AgentFlow Wiki Agent Orientation

This is the single source of truth for how Agents discover and use the AgentFlow LLM Wiki.

## Required Startup Sequence

Before answering project questions, changing code, updating docs, reviewing designs, or maintaining the wiki:

1. Read `.agentflow/wiki/SCHEMA.md`.
2. Read `.agentflow/wiki/index.md`.
3. Read recent entries in `.agentflow/wiki/log.md`.
4. Follow `index.md` to relevant stable wiki pages.

Use raw files and code search only when stable wiki pages are missing detail, need verification, or record a contradiction.

## Why This File Exists

Different Agent runtimes discover instructions from different bootstrap files:

- Codex and general repo Agents may read `AGENTS.md`.
- Claude Code may read `CLAUDE.md`.
- AgentFlow runtime may read `.claude/skills/using-agentflow/SKILL.md`.
- Compiled leaders may read `.agentflow/compiled/leader.md`.

Those files must not duplicate the policy. They should point here.

## Knowledge Update Flow

When durable new knowledge appears:

1. Capture or reference the source through `.agentflow/wiki/raw/` and `.agentflow/wiki/sources/source-catalog.md`.
2. Compile stable knowledge into the right page under `overview/`, `entities/`, `concepts/`, `designs/`, `decisions/`, `queries/`, or `reviews/`.
3. Record uncertainty in `open-questions/`.
4. Record conflicting facts in `contradictions/`.
5. Update `.agentflow/wiki/index.md`.
6. Append `.agentflow/wiki/log.md`.

Default write mode is proposal-first for broad wiki changes: propose touched files and rationale before changing many pages.

## Guardrails

- Preserve raw sources; do not casually rewrite files under `.agentflow/wiki/raw/`.
- Keep source-backed claims traceable through `sources:` frontmatter or explicit code paths.
- Do not flatten contradictions into a single unsupported conclusion.
- Record significant project changes in `变更点审查.md`.

