---
title: Project First, Automation Later
type: decision
status: active
created: 2026-04-24
updated: 2026-04-24
owners: [agentflow]
tags: [wiki, workflow]
sources:
  - docs-agentflow-knowledge-wiki-product
related:
  - ../designs/knowledge-wiki-architecture.md
  - ../designs/compiler-knowledge-wiki-seed.md
---

# Project First, Automation Later

## Decision

本次改造优先完成目录结构、规则文档、页面模板和维护约定，不要求接入完整自动化工具链。

## Rationale

- 现有目标是让 Agent 能够快速理解、查询和增量维护 App Center / AgentFlow 知识。
- 规则和结构先稳定，后续自动化才有清晰契约。
- Orchestrator 已有基础 seed 能力，可在后续迭代升级。

## Consequences

- 当前 lint 和 compile 主要依赖人工或 Agent 按规则执行。
- 后续需要把本结构同步进编译器模板，避免新项目生成旧版轻量 Wiki。

