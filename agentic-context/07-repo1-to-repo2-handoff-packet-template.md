# Repo 1 -> Repo 2 Handoff Packet Template

本文件是 Repo 1 向 Repo 2 移交稳定输入的控制接口模板。  
它不是某一层的附属说明，也不是实现模板；当前主消费者是 Repo 2 的 Layer 3。

## 文档定位与边界

本 handoff packet 只负责把 Repo 1 已稳定的输入整理成 Repo 2 可承接的包。

它负责：

- 打包已经稳定的 Layer 1 原则
- 打包已经稳定的 Layer 2 产品决定
- 打包 glossary 已定义的必要术语语义引用
- 打包 register 中相关治理项的状态快照
- 指定 Repo 2 的进入路径与 Return Path

它不负责：

- 生成新的产品决定
- 生成新的语义决定
- 生成新的状态决定
- schema 设计
- implementation checklist
- architecture backlog
- decision register
- glossary 副本
- issue tracker

本 packet 不拥有独立术语定义权，也不拥有独立状态定义权。  
若与 glossary 或 register 冲突，以 glossary 与 register 为准。

handoff packet 进入 Repo 2 后，具体 Layer 3 任务必须再经过 [08-layer-3-task-start-template.md](./08-layer-3-task-start-template.md) 的启动门。  
`07` 只负责稳定输入打包，不负责某次具体任务能不能启动。

## 使用原则

- 只写已经稳定的输入，不把未决事项伪装成稳定输入
- 若某项内容仍处于 open question / temporary assumption 状态，只能在 `Governance State Snapshot` 中引用，不得在其他区块偷偷升级
- 若 Repo 2 认为某项输入不足，必须走 `Return Path` 回 Repo 1，而不是在 Repo 2 内私自补定义

## Packet Identity

- `Packet Name`：
  - `<填写本次 handoff 名称>`
- `Source Repo`：
  - `Repo 1 / Project Context Repo`
- `Target Repo`：
  - `Repo 2 / System Realization Repo`
- `Target Layer`：
  - 默认填写 `Layer 3`
- `Status`：
  - `<Draft / Ready / Superseded>`
- `Scope Note`：
  - `<说明本 packet 覆盖的承接范围>`

## Canonical Source Bundle

以下文档构成 Repo 2 的进入路径，不是“推荐阅读”：

1. `<README.md>`
2. `<AGENTS.md>`
3. `<01-repo-charter.md>`
4. `<02-original-prompt-intake.md>`
5. `<05-cross-layer-glossary.md>`
6. `<06-open-questions-register.md>`
7. `<10-layer-1-concept-philosophy.md>`
8. `<20-layer-2-product-prd.md>`
9. `<30-layer-3-architecture-handoff.md>`

使用要求：

- Repo 2 的消费者默认先承认这些输入，再开始自己的 Layer 3 工作
- packet 只能引用这些上游 canonical 文档，不得重写它们的权威内容
- 若 Repo 2 发现某项输入不足或冲突，必须走 `Return Path`

## Stable Inherited Inputs

本区块只记录已经稳定的输入类别与引用，不写未决事项。

### Layer 1 Principles

- `<列出本次 handoff 必须继承的上位原则>`

### Layer 2 Product Decisions

- `<列出本次 handoff 必须继承的产品决定>`
- 默认双端点决定应在需要时写明：
  - `项目对接端点`
  - `监管升级端点`
  - 以及它们与 `owner / manager / liability` 的治理边界

### Glossary Terms

- `<列出本次 handoff 必须直接承认的 glossary 术语>`

## Governance State Snapshot

本区块只允许：

- 引用相关 OQR 项的 `ID`
- 引用其 `当前状态`
- 引用必要的当前决定摘要

本区块不允许：

- 在 packet 内重新解释 register 状态
- 在 packet 内重判某个 OQR 是否已关闭
- 在 packet 内改写某个 OQR 的状态语义

register 仍然是唯一状态权威源。

模板：

- `<OQR-ID>` / `<当前状态>` / `<必要决定摘要>`

## Responsibility Surface

本区块只记录已稳定的责任表面，不新增责任定义。

- 默认用户对接 endpoints：
  - `<引用当前已稳定的默认角色集>`
- 非端点治理角色：
  - `<引用 owner / manager / liability 与默认 endpoints 的关系边界>`
- 禁止改写项：
  - `<列出不得在 Repo 2 私自改写的责任边界>`

## Questions Repo 2 Must Answer

本区块只承载当前 handoff 后由 Repo 2 Layer 3 必须承接的架构问题。  
不得借此重开已关闭的产品决定、重定义 glossary 术语，或生成新的上游治理项；如发现这类问题，必须走 `Return Path` 回 Repo 1。

模板：

- `<Repo 2 Layer 3 必须回答的架构问题 1>`
- `<Repo 2 Layer 3 必须回答的架构问题 2>`
- `<Repo 2 Layer 3 必须回答的架构问题 3>`

## Non-Negotiables

- `<列出 Repo 2 不得削弱的上位边界>`
- `<例如：progress 不得退化成活动量>`
- `<例如：监管升级通道不得被项目对接表面吞掉>`

## Return Path

出现以下情况时，必须回 Repo 1，而不是在 Repo 2 内私自处理：

- glossary 术语不足以支持当前架构讨论
- register 中相关治理项状态不足以支持当前承接
- Layer 2 产品决定存在缺口或冲突
- 当前 handoff packet 无法支撑继续推进，而问题属于上游输入缺失，不是 Repo 2 的局部实现问题

回退目标：

- 术语问题 -> 回 `05-cross-layer-glossary.md`
- 治理状态问题 -> 回 `06-open-questions-register.md`
- 产品边界问题 -> 回 `20-layer-2-product-prd.md`
- 架构入口冲突 -> 回 `30-layer-3-architecture-handoff.md`

## L4 Placeholder

本区块只为后续 Layer 4 handoff 留输入类别占位，不代表本轮要提前定义实现要求。

这里只能保留：

- 将来实现层会消费哪些上游输入类别
- 将来实现层需要追溯哪些 Layer 1 / Layer 2 / Layer 3 输入

这里不能填写：

- 具体实现内容
- 具体 API / schema / event 设计
- 具体 UI / 页面 / 交互要求
- 任何会抢占 Layer 4 后续展开空间的实现细节
