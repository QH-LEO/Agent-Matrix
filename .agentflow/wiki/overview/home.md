---
title: Wiki Home
type: overview
status: active
created: 2026-04-24
updated: 2026-04-24
owners: [agentflow]
tags: [wiki, product, architecture]
sources:
  - docs-agentflow-knowledge-wiki-product
  - docs-hermes-agent-llm-wiki-research
  - readme
related:
  - ../entities/agentflow-platform.md
  - ../concepts/llm-wiki-pattern.md
  - ../designs/knowledge-wiki-architecture.md
---

# Wiki Home

## Summary

AgentFlow 的知识库从轻量项目 Wiki 升级为 LLM Wiki：原始资料先进 `raw/`，再被编译为稳定、可追溯、可导航、可增量维护的 Markdown 页面。查询时优先走 `index.md` 和页面关系，而不是每轮重新全文搜索所有原始资料。

## Current Map

- 产品定位见 [AgentFlow Platform](../entities/agentflow-platform.md) 和 [Agent Organization Compiler](../concepts/agent-organization-compiler.md)。
- Wiki 机制见 [LLM Wiki Pattern](../concepts/llm-wiki-pattern.md) 和 [Knowledge Wiki Architecture](../designs/knowledge-wiki-architecture.md)。
- 前端/App Center 领域见 [Pipeline Studio](../entities/pipeline-studio.md) 和 [Pipeline Studio Frontend](../designs/pipeline-studio-frontend.md)。
- 维护方式见 [Wiki Maintenance Mode](wiki-maintenance-mode.md)。

## Operating Assumption

当前 workspace 是 `/Users/leo/Projects/agentflow-platform`。用户请求中提到的 `app-center/.agentflow/wiki` 和 `/Users/didi/Code/*/.agentflow/wiki` 与当前路径不完全一致，已记录到 [App Center Path Ambiguity](../contradictions/app-center-path-ambiguity.md)。

