---
title: Knowledge Wiki Architecture
type: design
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

# Knowledge Wiki Architecture

## Summary

本次改造将 `.agentflow/wiki` 定义为 LLM Wiki：使用 raw / wiki / schema 三层结构，并补充 source catalog、contradictions、open questions 和维护规则。

## Structure

- `raw/requirements`、`raw/designs`、`raw/reviews`、`raw/code-notes`、`raw/meetings`、`raw/cooper`、`raw/db`、`raw/snapshots` 保存来源。
- `schema/` 保存 ingest、compile、lint、maintenance 规则和页面模板。
- 稳定页面按 `overview`、`entities`、`concepts`、`designs`、`decisions`、`queries`、`reviews` 组织。
- `sources/`、`contradictions/`、`open-questions/` 支撑可追溯和冲突管理。

## Query Path

`index.md` -> stable page -> related pages -> source catalog -> raw/code only if needed.

## Related

- [Wiki Maintenance Mode](../overview/wiki-maintenance-mode.md)
- [How To Query This Wiki](../queries/how-to-query-this-wiki.md)

