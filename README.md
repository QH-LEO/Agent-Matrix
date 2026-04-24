# AgentMatrix

AgentMatrix 是一个面向 Agent 协作的配置平台。

它不重新实现 Agent runtime，也不替代 Claude Code / Codex 这类本地 Agent 工具。它解决的是另一件事：把团队的研发流程、角色分工、质量门禁、委托策略、知识库规则和 Skill 使用方式，配置成 Agent 能理解、能执行、能持续复用的项目上下文。

换句话说，AgentMatrix 让 Agent 不只是“拿到一个任务”，而是拿到一套被组织过的工作方式。

## 它解决什么问题

在真实研发协作里，Agent 经常缺少这些上下文：

- 不知道当前项目应该按什么阶段推进。
- 不知道什么时候该自己做，什么时候该拆给子 Agent 或 Team。
- 不知道哪些输出必须经过人工确认。
- 不知道不同角色分别负责什么产物。
- 不知道应该调用哪些 Skill，或 Skill 应用于哪个阶段。
- 不知道项目长期知识、历史决策、冲突和待确认问题在哪里。
- 不知道写入前应该检查哪些路径、Agent、Skill 和配置。

AgentMatrix 的目标是把这些“团队规则”从口头约定变成可配置、可预览、可编译的 Agent 运行资产。

## 配置能力如何赋能 Agent

### 1. 流程编排

通过 Pipeline -> Stage -> Action 的配置，Agent 可以获得明确的研发流程：

- 每个阶段要消费什么输入。
- 每个阶段要产出什么结果。
- 每个动作由哪个 Agent 负责。
- 阶段之间如何交接。
- 哪些动作需要门禁确认。

这让 Agent 能按项目流程推进，而不是把任务当成一次性的孤立请求。

### 2. Agent 角色配置

平台可以为阶段绑定 Agent，并配置：

- Agent 名称与本机 agentName。
- 角色职责。
- 关注的输入产物。
- 应产出的交付物。
- 可用工具。
- 共享 Agent 或项目托管 Agent。

这些配置会被编译成 Agent 指令，让产品、架构、开发、测试等角色不再只是自然语言描述，而是可执行的职责边界。

### 3. Skill 装配

平台支持给流水线或具体 Agent 配置 Skill：

- Skill 名称。
- Skill 版本。
- 本地路径。
- 适用 Agent。

如果 Skill 有本地 `SKILL.md`，Agent 在执行相关角色工作前可以读取它；如果只有名称和版本，也可以作为能力契约进入运行上下文。

### 4. 委托策略

平台可以配置 Agent 的工作分派方式：

- 默认由当前 Agent 自己完成，还是建议启动 Team。
- 是否允许 Sub Agent。
- 是否允许 Agent Team。
- 是否允许受控递归委托。
- 最大递归深度。
- 最大并行 Agent 数。
- self / subagent / team / recursive 的升级规则。

这让 Agent 在遇到复杂任务时有明确的拆解边界，而不是临场猜测是否该并行、是否该组队、是否该继续上抛。

### 5. 质量门禁

平台可以配置阻断型或审查型门禁，例如：

- 需求确认。
- 方案确认。
- 写文件前确认。
- 完成验收。
- 破坏性命令确认。
- 发布前确认。

每个门禁都能声明触发时机、执行人、强制级别、需要提交的证据、通过标准和失败动作。Agent 因此可以知道哪些节点不能自动越过，哪些内容必须交给人确认。

### 6. Knowledge Wiki

平台支持为项目配置 `.agentflow/wiki`：

- Agent 启动时先 orient 项目知识。
- 稳定知识沉淀到 Wiki 页面。
- 原始资料保存在 raw 层。
- 冲突事实记录到 contradictions。
- 待确认问题记录到 open-questions。
- 重要变更进入审查记录。

这让 Agent 能带着项目长期上下文工作，而不是每次都从代码和聊天记录里重新摸索。

### 7. 编译预览与启动预检

平台在真正写入或运行前提供：

- DSL lint。
- 编译产物预览。
- 当前内容与下一版内容对比。
- 项目路径检查。
- Claude agents 目录检查。
- 共享 Agent 检查。
- Skill 路径检查。
- Knowledge Wiki 路径检查。

这让配置变更和 Agent 启动都变得可审查、可追踪。

### 8. 启动 Prompt 生成

平台可以根据当前 Pipeline 和用户需求生成启动 Prompt，并支持不同启动模式：

- `single-leader`：单 Leader 执行。
- `suggest-team`：建议按 Team 方式拆解。
- `force-team`：强制按 Team 生命周期运行。

Agent 启动时会拿到流程、角色、门禁、委托策略、Knowledge Wiki 和用户需求，而不是只拿到一段孤立描述。

## 当前实现

当前仓库包含两个主要可运行模块：

- `frontend/`：Vue 3 + Vite 的 Pipeline Studio，用于配置流程、策略、门禁、Agent、Skill，并预览编译产物。
- `orchestrator/`：Node.js + Express 的配置编译服务，负责读取 DSL、校验配置、生成 `.agentflow/` / `.claude/` 资产，并生成运行启动 Prompt。

核心配置源是：

```text
configs/agentflow.pipeline.json
```

它是当前可编辑 DSL，优先级高于已经编译出的 `.agentflow/compiled/*` 文件。

## 目录结构

```text
.
├── .agentflow/                 # 当前项目已编译的 AgentMatrix 资产与 Wiki
├── .claude/                    # 本项目生成的 Claude skill bootstrap
├── backend/                    # 后端预留目录，当前主要服务在 orchestrator/
├── configs/
│   ├── agentflow.pipeline.json # 当前可编辑 DSL，优先级最高
│   └── agentflow.definition-sync.json
├── docs/                       # 产品、前端和 Wiki 设计资料
├── frontend/                   # Pipeline Studio Vue 应用
├── orchestrator/               # 编译器、schema、storage 和 HTTP API
├── scripts/                    # 本地启动脚本
├── tests/                      # 测试预留目录
├── tools/                      # 附加工具与 Skill
└── 变更点审查.md                # 重要变更审查记录
```

## 快速启动

要求：Node.js 18+，npm。

先启动配置编译服务：

```bash
./scripts/run-orchestrator.sh
```

服务默认监听：

```text
http://localhost:8787
```

另开一个终端启动前端：

```bash
./scripts/run-frontend.sh
```

前端默认监听：

```text
http://localhost:5173
```

打开 `http://localhost:5173` 进入 Pipeline Studio。

## 工作台使用流程

1. 在「流程编排」中维护 Pipeline、阶段、动作、输入输出和阶段顺序。
2. 在「策略模型」中配置项目路径、Claude 目录、共享 Agent 目录、委托策略和 Knowledge Wiki。
3. 在「门禁管理」中维护质量门禁及其证据、通过标准和失败动作。
4. 在「Agent 职责」中为阶段绑定共享 Agent 或托管 Agent。
5. 在「Skill 管理」中为流水线或 Agent 绑定 Skill。
6. 在「编译预览」中执行 lint、预览产物、确认写入或从系统快照同步 DSL。
7. 点击「启动」进入运行控制台，填写需求，选择启动模式，并生成或打开本地执行入口。

## 编译产物

执行编译后，orchestrator 会按当前 Pipeline 生成或更新这些资产：

- `configs/agentflow.pipeline.json`：规范化后的 DSL。
- `.agentflow/manifest.json`：运行 manifest。
- `.agentflow/compiled/definition.snapshot.json`：当前 definition 快照。
- `.agentflow/compiled/leader.md`：Team Leader 指令。
- `.agentflow/compiled/sop.md`：阶段与动作 SOP。
- `.agentflow/compiled/delegation-policy.md`：委托策略。
- `.agentflow/compiled/gates.md` 和 `.agentflow/compiled/gates.json`：门禁计划。
- `.agentflow/compiled/launch-prompt.md`：默认启动 Prompt。
- `.agentflow/wiki/`：Knowledge Wiki seed 或已维护的 Wiki 结构。
- `.claude/skills/using-agentflow/SKILL.md`：AgentMatrix 运行协议 Skill。
- `~/.claude/agents/*.md`：Leader 和托管 Agent 文件。

如果 `configs/agentflow.pipeline.json` 与 `.agentflow/compiled/*` 不一致，应以配置文件表达的最新意图为准，并记录配置与编译产物之间的漂移。

## Orchestrator API

主要接口：

- `GET /api/health`：服务与 tmux 可用性检查。
- `GET /api/agents`：读取本机共享 Claude agents。
- `GET /api/definition`：读取当前 DSL。
- `POST /api/lint`：校验当前 definition。
- `POST /api/preflight`：运行启动前检查。
- `POST /api/compile/preview`：预览编译计划和文件 diff 信息。
- `POST /api/compile/apply`：写入编译产物。
- `POST /api/definition/sync-preview`：预览从系统快照同步 DSL。
- `POST /api/definition/sync`：执行 DSL 同步。
- `POST /api/launch-prompt/preview`：生成启动 Prompt。
- `POST /api/runs`：创建一次运行记录。
- `POST /api/runs/:runId/open-iterm`：写入启动脚本并通过 iTerm2 打开。
- `POST /api/runs/:runId/stop`：停止运行记录。

## 开发命令

```bash
cd orchestrator
npm install
npm run dev
```

```bash
cd frontend
npm install
npm run dev
npm run build
```

当前根目录没有统一的 `package.json`，也没有统一的 `npm test`。

## 开发约定

- TDD 优先：高风险或共享行为变更应先补测试或可验证用例。
- 人工门禁：阻断型门禁需要明确证据与确认。
- 可追溯：重要变更应更新 `变更点审查.md`。
- Knowledge Wiki raw 资料默认不可变，稳定结论应编译到 Wiki 页面。
- 写入前先预览，确认产物边界后再执行编译写入。
