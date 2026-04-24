---
title: Source Catalog
type: source
status: active
created: 2026-04-24
updated: 2026-04-24
owners: [agentflow]
tags: [source, wiki]
sources: []
related:
  - ../overview/home.md
  - ../raw/designs/hermes-agent-llm-wiki-research.raw.md
---

# Source Catalog

## Durable Project Sources

| Source id | Kind | Location | Notes |
| --- | --- | --- | --- |
| `user-request-2026-04-24` | requirement | current conversation | Request to upgrade AgentFlow Wiki into a long-term LLM Wiki knowledge base. |
| `readme` | requirement | `README.md` | Project layout, principles, runnable frontend entry points. |
| `root-plan-agentflow` | design | `方案.md` | AgentFlow as Agent Organization Compiler. |
| `root-plan-discussion` | design | `方案讨论.md` | V0.2 Agent Team workflow platform design. |
| `root-change-review` | review | `变更点审查.md` | Cross-session change log and review checklist. |
| `docs-agentflow-knowledge-wiki-product` | design | `docs/agentflow-knowledge-wiki-product.md` | Knowledge Wiki product proposal. |
| `docs-hermes-agent-llm-wiki-research` | design | `docs/hermes-agent-llm-wiki-research.md` | Hermes / Karpathy LLM Wiki research. |
| `docs-frontend-page-spec` | design | `docs/frontend-page-spec.md` | Pipeline Studio information architecture and interactions. |
| `code-orchestrator-compiler` | code-note | `orchestrator/src/compiler.js` | Compiler emits AgentFlow assets and existing Knowledge Wiki seed artifacts. |
| `code-orchestrator-schema` | code-note | `orchestrator/src/schema.js` | Default knowledgeBase config and DSL normalization. |
| `code-frontend-studio-composable` | code-note | `frontend/src/composables/useAgentFlowStudio.js` | Frontend default pipelines, menus, quality gates and Knowledge Wiki state. |
| `config-agentflow-pipeline` | snapshot | `configs/agentflow.pipeline.json` | Current pipeline definition; currently has uncommitted user/workspace changes. |
