# AgentFlow LLM Wiki Schema

## Domain

本 Wiki 是 AgentFlow Platform 的长期项目知识库，用于沉淀产品定位、流程 DSL、Agent/Skill 编译、Knowledge Wiki、前端 App Center / Pipeline Studio、Orchestrator 编译器、质量门禁和评审记录。

## Layer Model

本 Wiki 使用三层结构：

- `raw/`：原始资料层。保存需求、设计、评审、代码笔记、会议、协作系统、数据库和快照等来源。默认不可变；如来源需要修订，应新增版本或追加说明。
- `wiki pages`：编译知识层。包括 `overview/`、`entities/`、`concepts/`、`designs/`、`decisions/`、`queries/`、`reviews/` 等稳定页面，由 Agent/LLM 维护。
- `schema/`：规则层。定义 ingest、compile、query、lint、维护和模板约定。

查询时优先读取 `index.md`、相关 Wiki 页面和页面间链接。只有当 Wiki 页面不足、需要核验事实或处理冲突时，才回到 `raw/` 和代码全文搜索。

## Directory Contract

- `overview/`：知识库主页、维护模式、领域地图。
- `entities/`：系统、模块、角色、外部依赖、配置资产等名词。
- `concepts/`：抽象概念、流程原则、模式、协议。
- `designs/`：架构、产品、前端、编译器、运行态设计。
- `decisions/`：ADR、关键取舍、废弃方案和原因。
- `queries/`：高价值问答和可复用综合结论。
- `reviews/`：评审、审计、变更点检查和验证记录。
- `sources/`：来源清单和 source id 映射。
- `contradictions/`：文档、代码、设计之间的冲突记录。
- `open-questions/`：待确认问题、缺失事实和需要人类判断的事项。

## Frontmatter

每个稳定 Wiki 页面必须使用 YAML frontmatter：

```yaml
---
title: Page Title
type: overview | entity | concept | design | decision | query | review | source | contradiction | open-question
status: draft | active | stale | archived
created: YYYY-MM-DD
updated: YYYY-MM-DD
owners: [agentflow]
tags: [tag]
sources:
  - source-id
related:
  - ../path/page.md
---
```

`raw/` 记录可使用轻量 frontmatter，见 `schema/page-templates/raw-note.md`。

## Source Rules

- `sources:` 必须引用 `sources/source-catalog.md` 中存在的 source id，或引用同次变更新增的 raw note。
- 页面中的关键事实应可追溯到 `sources:`、代码路径或显式推断。
- 不要把聊天记忆当作最终来源；如果只有聊天上下文，应先落 raw note 再编译。
- Raw 文件默认不改写。确需更正时，新增版本或在 raw note 中追加 `corrections`。

## Link Rules

- 每个稳定页面应至少链接 2 个相关页面；早期种子页不足时可链接 `../overview/home.md` 和 `../sources/source-catalog.md`。
- 新增或改名页面必须同步更新 `index.md`。
- 删除或归档页面时必须记录到 `log.md`，并修复所有反向链接。
- 使用相对 Markdown 链接作为主导航；可在正文中补充 `[[wikilinks]]` 方便 Obsidian 类工具。

## Tag Taxonomy

- `product`：产品定位、用户价值、功能边界。
- `architecture`：系统边界、模块、接口、运行态。
- `workflow`：阶段、SOP、门禁、委托、维护流程。
- `agent`：Agent、Leader、Subagent、角色职责。
- `skill`：Skill、插件、复用工作流。
- `wiki`：LLM Wiki、知识库、ingest、compile、query、lint。
- `frontend`：App Center、Pipeline Studio、Vue、页面交互。
- `orchestrator`：编译器、server、schema、storage、启动。
- `quality`：TDD、评审、测试、风险、审计。
- `source`：来源目录、raw note、代码事实。

新增 tag 前先更新本节。

## Update Policy

- 先 orient：读取 `SCHEMA.md`、`index.md`、`log.md` 最近记录。
- 先查已有页面，再决定创建新页。
- 新知识进入顺序：raw/source -> wiki page -> index/log。
- 不确定或冲突的信息不要覆盖旧结论，改写入 `contradictions/` 或 `open-questions/`。
- 单次更新预计触碰超过 10 个稳定页面时，先提出维护计划。
- 页面超过约 200 行，或承担多个主题时，应拆分。

