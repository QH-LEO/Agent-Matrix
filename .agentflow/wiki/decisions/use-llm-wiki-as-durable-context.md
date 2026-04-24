---
title: Use LLM Wiki As Durable Context
type: decision
status: active
created: 2026-04-24
updated: 2026-04-24
owners: [agentflow]
tags: [wiki, architecture]
sources:
  - docs-agentflow-knowledge-wiki-product
  - docs-hermes-agent-llm-wiki-research
related:
  - ../entities/knowledge-wiki.md
  - ../concepts/llm-wiki-pattern.md
---

# Use LLM Wiki As Durable Context

## Decision

AgentFlow 使用 LLM Wiki 作为项目长期上下文层，而不是只依赖聊天摘要、运行日志或每次重新搜索原始资料。

## Rationale

- 项目研发知识需要跨会话复用。
- 稳定页面比 raw chunk 更适合 Agent 快速导航。
- `index.md`、`log.md` 和 schema 让知识可以增量维护。
- 矛盾记录比覆盖式总结更可靠。

## Consequences

- 每次维护需要 source、index、log 的额外纪律。
- Wiki 页面需要 lint，避免变成无链接总结堆。
- Raw/source 与稳定页面之间必须保持可追溯。

