# AgentFlow LLM Wiki Index

> 入口文件。查询时先读这里，再沿页面关系进入相关知识页；不要默认回到 raw 或代码全文搜索。

## Orientation

- [Agent Orientation](AGENT_ORIENTATION.md)：Agent 发现和使用本 Wiki 的统一入口。
- [Wiki Home](overview/home.md)：知识库地图和当前项目结论。
- [Wiki Maintenance Mode](overview/wiki-maintenance-mode.md)：Agent 维护本知识库的工作方式。
- [Source Catalog](sources/source-catalog.md)：来源 id、原始资料和代码事实索引。
- [Open Questions](open-questions/app-center-wiki-scope.md)：当前范围和待确认问题。

## Core Entities

- [AgentFlow Platform](entities/agentflow-platform.md)：项目整体定位和仓库空间。
- [Pipeline Studio](entities/pipeline-studio.md)：前端配置台 / App Center 领域入口。
- [AgentFlow Orchestrator](entities/agentflow-orchestrator.md)：编译器、schema、server、storage 所在模块。
- [Knowledge Wiki](entities/knowledge-wiki.md)：项目长期上下文层。

## Concepts

- [LLM Wiki Pattern](concepts/llm-wiki-pattern.md)：raw / wiki / schema 三层模式。
- [Agent Organization Compiler](concepts/agent-organization-compiler.md)：AgentFlow 的核心产品定位。
- [Human Gate](concepts/human-gate.md)：质量门禁与人工确认原则。

## Designs

- [Knowledge Wiki Architecture](designs/knowledge-wiki-architecture.md)：本次 LLM Wiki 改造方案。
- [Pipeline Studio Frontend](designs/pipeline-studio-frontend.md)：前端页面、数据模型和交互。
- [Compiler Knowledge Wiki Seed](designs/compiler-knowledge-wiki-seed.md)：编译器当前 Knowledge Wiki 生成能力。

## Decisions

- [Use LLM Wiki As Durable Context](decisions/use-llm-wiki-as-durable-context.md)：将 Wiki 作为长期上下文层。
- [Project First, Automation Later](decisions/project-first-automation-later.md)：本次先落目录、规则、模板和维护约定。

## Queries

- [How To Query This Wiki](queries/how-to-query-this-wiki.md)：面向 Agent 的查询流程。

## Reviews

- [Wiki Bootstrap Review](reviews/wiki-bootstrap-review.md)：本次结构化升级的审查记录。

## Contradictions

- [App Center Path Ambiguity](contradictions/app-center-path-ambiguity.md)：用户目标路径与当前仓库路径不完全一致。

## Raw Sources

- [Product Wiki Proposal Raw Note](raw/designs/agentflow-knowledge-wiki-product.raw.md)
- [Hermes LLM Wiki Research Raw Note](raw/designs/hermes-agent-llm-wiki-research.raw.md)
- [Frontend Page Spec Raw Note](raw/designs/frontend-page-spec.raw.md)
- [Project README Raw Note](raw/requirements/project-readme.raw.md)
- [Compiler Code Notes](raw/code-notes/orchestrator-compiler-knowledge-wiki.raw.md)

## Maintenance Status

- Last updated: 2026-04-24
- Total stable pages listed: 15
- Write mode: proposal-first unless the user explicitly asks to write.
