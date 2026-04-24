---
source_id: docs-agentflow-knowledge-wiki-product
kind: design
status: active
captured: 2026-04-24
origin: docs/agentflow-knowledge-wiki-product.md
immutable: true
---

# AgentFlow Knowledge Wiki Product Raw Note

## Extracted Facts

- Knowledge Wiki 是每条流水线的项目知识层，解决“下次别从零开始”。
- MVP 配置包含 `enabled`、`path`、`domain`、`autoOrient`、`writeMode`、`rawImmutable`。
- 默认写入模式是 `proposal_first`。
- 启动规程应读取 `SCHEMA.md`、`index.md`、`log.md`。
- 阶段结束时默认输出 Wiki 更新建议，而不是自动写。

## Candidate Wiki Updates

- [Knowledge Wiki](../../entities/knowledge-wiki.md)
- [Knowledge Wiki Architecture](../../designs/knowledge-wiki-architecture.md)

