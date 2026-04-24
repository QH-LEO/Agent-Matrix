---
source_id: docs-hermes-agent-llm-wiki-research
kind: design
status: active
captured: 2026-04-24
origin: docs/hermes-agent-llm-wiki-research.md
immutable: true
---

# Hermes Agent LLM Wiki Research Raw Note

## Extracted Facts

- LLM Wiki 把原始资料持续编译成互链 Markdown 知识库。
- 核心结构是 raw sources、wiki pages、schema 三层。
- 操作模式包括 ingest、query、lint。
- 每次会话应先读取 schema、index、log。
- 内容冲突不能静默覆盖，应保留不同说法、日期和来源。

## Candidate Wiki Updates

- [LLM Wiki Pattern](../../concepts/llm-wiki-pattern.md)
- [Wiki Maintenance Mode](../../overview/wiki-maintenance-mode.md)

