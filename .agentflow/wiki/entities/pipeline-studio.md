---
title: Pipeline Studio
type: entity
status: active
created: 2026-04-24
updated: 2026-04-24
owners: [agentflow]
tags: [frontend, product, workflow]
sources:
  - docs-frontend-page-spec
  - code-frontend-studio-composable
related:
  - ../designs/pipeline-studio-frontend.md
  - ../entities/agentflow-platform.md
---

# Pipeline Studio

## Summary

Pipeline Studio 是 App Center / AgentFlow 前端配置台，帮助用户配置流水线、阶段、Agent 职责、Skill、策略模型、门禁和编译预览。

## Stable Facts

- 早期页面规格将核心层级定义为 Pipeline -> Stage -> Agent -> Skill。
- 当前 Vue composable 中菜单已包含 `pipeline`、`policy`、`gates`、`agent`、`skill`、`compile`。
- 前端内置默认“核心研发流程”，并启用 Knowledge Wiki 默认配置。

## Related

- [Pipeline Studio Frontend](../designs/pipeline-studio-frontend.md)
- [Human Gate](../concepts/human-gate.md)

