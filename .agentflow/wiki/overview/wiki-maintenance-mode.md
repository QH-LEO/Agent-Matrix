---
title: Wiki Maintenance Mode
type: overview
status: active
created: 2026-04-24
updated: 2026-04-24
owners: [agentflow]
tags: [wiki, workflow]
sources:
  - docs-agentflow-knowledge-wiki-product
  - docs-hermes-agent-llm-wiki-research
related:
  - ../queries/how-to-query-this-wiki.md
  - ../schema/wiki-maintenance-rules.md
---

# Wiki Maintenance Mode

## Summary

维护本 Wiki 的 Agent 需要先 orient，再按 ingest / compile / query / lint 四种模式工作。默认写入策略是 proposal-first：重大或跨页面改动先提出更新建议。

## Modes

- Ingest：把来源放入 `raw/`，登记 `sources/source-catalog.md`。
- Compile：把 raw/source 事实合并到稳定页面。
- Query：从 `index.md` 和稳定页面回答问题。
- Lint：检查 frontmatter、链接、source、index、冲突和过长页面。

## Rule Pages

- [Ingest Rules](../schema/ingest-rules.md)
- [Compile Rules](../schema/compile-rules.md)
- [Lint Rules](../schema/lint-rules.md)
- [Maintenance Rules](../schema/wiki-maintenance-rules.md)

