---
title: AgentFlow Orchestrator
type: entity
status: active
created: 2026-04-24
updated: 2026-04-24
owners: [agentflow]
tags: [orchestrator, architecture]
sources:
  - code-orchestrator-compiler
  - code-orchestrator-schema
related:
  - ../designs/compiler-knowledge-wiki-seed.md
  - ../concepts/agent-organization-compiler.md
---

# AgentFlow Orchestrator

## Summary

AgentFlow Orchestrator 负责把 DSL 定义编译为项目级 `.agentflow/`、`.claude/` 和启动 prompt 等资产。它是 Agent Organization Compiler 的实现核心之一。

## Stable Facts

- `orchestrator/src/schema.js` 定义默认委托策略、质量门禁和 Knowledge Wiki 配置。
- `orchestrator/src/compiler.js` 负责 lint definition、生成 manifest、compiled SOP、delegation policy、gates、launch prompt、using-agentflow skill 和 Knowledge Wiki seed artifacts。
- Knowledge Wiki 相关编译产物当前已经存在，但目录结构仍需升级以匹配本次 LLM Wiki 目标。

## Related

- [Compiler Knowledge Wiki Seed](../designs/compiler-knowledge-wiki-seed.md)
- [Knowledge Wiki](knowledge-wiki.md)

