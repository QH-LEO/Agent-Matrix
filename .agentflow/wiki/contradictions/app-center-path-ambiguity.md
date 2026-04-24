---
title: App Center Path Ambiguity
type: contradiction
status: active
created: 2026-04-24
updated: 2026-04-24
owners: [agentflow]
tags: [wiki, quality]
sources:
  - user-request-2026-04-24
related:
  - ../overview/home.md
  - ../open-questions/app-center-wiki-scope.md
---

# App Center Path Ambiguity

## Conflict

用户目标中同时出现 `app-center/.agentflow/wiki`、`/Users/didi/Code/*/.agentflow/wiki`，而当前执行 workspace 是 `/Users/leo/Projects/agentflow-platform`，且本仓库没有 `app-center` 子目录。

## Claim A

- Claim: 目标目录是 `app-center/.agentflow/wiki` 或 `/Users/didi/Code/*/.agentflow/wiki`。
- Source: user request on 2026-04-24.

## Claim B

- Claim: 当前可操作仓库目录是 `/Users/leo/Projects/agentflow-platform`，现有 `.agentflow/` 位于仓库根目录。
- Source: local workspace inspection on 2026-04-24.

## Current Handling

本次将 `/Users/leo/Projects/agentflow-platform/.agentflow/wiki` 作为目标 Wiki。若后续确认存在 App Center 独立仓库，应复制或重新生成同等结构。

## Resolution Needed

确认 `app-center` 是否是另一个仓库、历史名称，还是当前 AgentFlow Platform 的业务域名称。

