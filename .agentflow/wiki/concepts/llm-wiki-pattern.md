---
title: LLM Wiki Pattern
type: concept
status: active
created: 2026-04-24
updated: 2026-04-24
owners: [agentflow]
tags: [wiki, workflow]
sources:
  - docs-hermes-agent-llm-wiki-research
related:
  - ../entities/knowledge-wiki.md
  - ../overview/wiki-maintenance-mode.md
---

# LLM Wiki Pattern

## Summary

LLM Wiki 模式把知识处理从“查询时临时检索 raw chunk”前移到“摄取时编译成稳定页面”。它保留 raw/source，可读页面和 schema 规则，并通过 index/log 支持增量维护。

## Core Pattern

- Raw sources：原始资料，不作为随意编辑的总结页。
- Wiki pages：Entity、Concept、Design、Decision、Review、Query 等稳定页面。
- Schema：命名、frontmatter、tag、链接、冲突和维护规则。

## Implication For Agents

Agent 应先沿 [AgentFlow LLM Wiki Index](../index.md) 导航，只有在稳定页面不足或需要核验时才回到 raw/source。

