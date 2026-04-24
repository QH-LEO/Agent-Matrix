---
title: Knowledge Wiki
type: entity
status: active
created: 2026-04-24
updated: 2026-04-24
owners: [agentflow]
tags: [wiki, workflow]
sources:
  - docs-agentflow-knowledge-wiki-product
  - docs-hermes-agent-llm-wiki-research
related:
  - ../concepts/llm-wiki-pattern.md
  - ../designs/knowledge-wiki-architecture.md
---

# Knowledge Wiki

## Summary

Knowledge Wiki 是每条 AgentFlow 流水线的长期上下文层。它沉淀可复用的需求、方案、决策、评审、代码事实和查询结果，让 Agent 不必每次从原始资料重新理解项目。

## Stable Facts

- 默认路径是 `.agentflow/wiki`。
- 默认写入模式是 `proposal_first`。
- Agent 启动时应先读取 `SCHEMA.md`、`index.md` 和 `log.md`。
- Raw source 默认不可变；稳定 Wiki 页面由 Agent/LLM 编译和维护。

## Related

- [LLM Wiki Pattern](../concepts/llm-wiki-pattern.md)
- [Knowledge Wiki Architecture](../designs/knowledge-wiki-architecture.md)

