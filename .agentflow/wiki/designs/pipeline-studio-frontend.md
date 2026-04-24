---
title: Pipeline Studio Frontend
type: design
status: active
created: 2026-04-24
updated: 2026-04-24
owners: [agentflow]
tags: [frontend, product]
sources:
  - docs-frontend-page-spec
  - code-frontend-studio-composable
related:
  - ../entities/pipeline-studio.md
  - ../concepts/human-gate.md
---

# Pipeline Studio Frontend

## Summary

Pipeline Studio 前端从早期轻量 Vue 原型演进为配置 AgentFlow 流水线的工作台。它承载流程编排、策略模型、门禁管理、Agent 职责、Skill 管理和编译预览。

## Stable Facts

- 页面规格定义了 Pipeline -> Stage -> Agent -> Skill 的核心数据模型。
- 早期四个菜单是流水线管理、阶段编排、Agent 职责、Skill 管理。
- 当前 composable 的菜单已扩展到流程编排、策略模型、门禁管理、Agent 职责、Skill 管理、编译预览。
- 默认数据包含核心研发流程、默认质量门禁和默认 Knowledge Wiki 配置。

## Related

- [Pipeline Studio](../entities/pipeline-studio.md)
- [Human Gate](../concepts/human-gate.md)

