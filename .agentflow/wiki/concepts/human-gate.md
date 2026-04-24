---
title: Human Gate
type: concept
status: active
created: 2026-04-24
updated: 2026-04-24
owners: [agentflow]
tags: [quality, workflow]
sources:
  - readme
  - root-plan-discussion
  - code-orchestrator-schema
related:
  - ../entities/agentflow-platform.md
  - ../entities/pipeline-studio.md
---

# Human Gate

## Summary

Human Gate 是 AgentFlow 的质量控制机制：阶段边界、写文件前、完成验收、破坏性命令和发布前等关键点需要人工确认或审查。

## Stable Facts

- README 将阶段门禁列为研发原则。
- V0.2 方案要求每个阶段都有 Human Checkpoint。
- Schema 默认质量门禁包括需求确认、方案确认、写文件前、完成验收、破坏性命令、发布前确认。

## Related

- [Pipeline Studio](../entities/pipeline-studio.md)
- [AgentFlow Platform](../entities/agentflow-platform.md)

