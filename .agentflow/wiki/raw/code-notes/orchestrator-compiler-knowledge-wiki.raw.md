---
source_id: code-orchestrator-compiler
kind: code-note
status: active
captured: 2026-04-24
origin: orchestrator/src/compiler.js
immutable: true
---

# Orchestrator Compiler Knowledge Wiki Code Note

## Extracted Facts

- `buildCompilePlan` normalizes a definition, lints it, and emits artifacts.
- `buildKnowledgeBaseArtifacts` currently emits seed-only `SCHEMA.md`, `index.md`, `log.md` plus `.gitkeep` directories and compiled wiki prompts/skill.
- The older generated directory set includes `raw/requirements`, `raw/designs`, `raw/reviews`, `raw/external`, `entities`, `concepts`, `decisions`, `comparisons`, `queries`.
- `renderUsingAgentFlowSkill` already instructs the leader to orient on Knowledge Wiki when enabled.

## Candidate Wiki Updates

- [Compiler Knowledge Wiki Seed](../../designs/compiler-knowledge-wiki-seed.md)

