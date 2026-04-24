---
title: Compiler Knowledge Wiki Seed
type: design
status: active
created: 2026-04-24
updated: 2026-04-24
owners: [agentflow]
tags: [orchestrator, wiki]
sources:
  - code-orchestrator-compiler
  - code-orchestrator-schema
related:
  - ../entities/agentflow-orchestrator.md
  - ../designs/knowledge-wiki-architecture.md
---

# Compiler Knowledge Wiki Seed

## Summary

Orchestrator 已具备 Knowledge Wiki seed 生成能力，但旧目录和模板比本次 LLM Wiki 目标轻。本次手工结构升级应作为后续编译器模板升级的参考。

## Current Code Facts

- `buildKnowledgeBaseArtifacts` 根据 `pipeline.knowledgeBase.enabled` 生成 Wiki seed。
- 生成文件包括 seed-only `SCHEMA.md`、`index.md`、`log.md`。
- 生成目录目前包含 `raw/external` 和 `comparisons`，但不包含本次目标中的 `schema/`、`overview/`、`sources/`、`contradictions/`、`open-questions/`、`raw/code-notes` 等。
- `renderUsingAgentFlowWikiSkill` 已包含 orient、ingest、query 和写入模式说明。

## Follow-up

后续可以升级 `orchestrator/src/compiler.js` 的 Knowledge Wiki seed 模板，让新建项目直接得到本次 LLM Wiki 结构。

