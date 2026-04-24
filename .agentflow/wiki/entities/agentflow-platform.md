---
title: AgentFlow Platform
type: entity
status: active
created: 2026-04-24
updated: 2026-04-24
owners: [agentflow]
tags: [product, architecture, workflow]
sources:
  - readme
  - root-plan-agentflow
  - root-plan-discussion
related:
  - ../concepts/agent-organization-compiler.md
  - ../entities/agentflow-orchestrator.md
---

# AgentFlow Platform

## Summary

AgentFlow Platform 是面向研发团队的 Agent 组织编译器和流程平台。它把流水线、阶段、角色、职责、Skill、质量门禁和委托策略编译成 Claude Code / 本地 Agent 工作流可执行的资产。

## Stable Facts

- 项目空间包括前端、编排器、配置、脚本、文档、测试和技能目录。
- 产品覆盖需求分析、技术方案、开发、测试流程。
- 项目原则强调 TDD、阶段门禁和可追溯。
- 当前方向不是重新实现完整 Agent runtime，而是编译 Claude Code 原生资产。

## Related

- [Agent Organization Compiler](../concepts/agent-organization-compiler.md)
- [AgentFlow Orchestrator](agentflow-orchestrator.md)
- [Pipeline Studio](pipeline-studio.md)

