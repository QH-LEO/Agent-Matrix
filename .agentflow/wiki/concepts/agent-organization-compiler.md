---
title: Agent Organization Compiler
type: concept
status: active
created: 2026-04-24
updated: 2026-04-24
owners: [agentflow]
tags: [product, architecture, agent]
sources:
  - root-plan-agentflow
related:
  - ../entities/agentflow-platform.md
  - ../entities/agentflow-orchestrator.md
---

# Agent Organization Compiler

## Summary

Agent Organization Compiler 是 AgentFlow 的核心定位：页面负责建模，Orchestrator 负责编译，Claude Code / 本地 Agent runtime 负责执行。

## Stable Facts

- AgentFlow 的差异化不是单纯可视化流程，而是把流程图、角色职责、Skill 和门禁编译成真实 Agent 资产。
- 目标资产包括 Leader agent markdown、subagent 定义、Skill、hooks、plugin package、启动 prompt 和行为测试 fixture。
- 该定位降低了自研 runtime 复杂度，并贴近本地 Agent 生态。

## Related

- [AgentFlow Platform](../entities/agentflow-platform.md)
- [Compiler Knowledge Wiki Seed](../designs/compiler-knowledge-wiki-seed.md)

