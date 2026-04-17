# Layer 3 Task Start Template

本文件是 Repo 2 Layer 3 具体任务的准入控制模板。  
它不是架构设计稿，不是 backlog，不是 decision register，也不是实现计划。

## 文档定位与边界

本模板的目标不是帮助 agent 顺势往下做架构，而是在 Layer 3 前加一道不能绕过的启动门，防止上游未决、语义缺口和非架构问题被带进 Repo 2。

它的核心职责只有五项：

- 准入检查
- 输入校验
- 上游未决拦截
- 问题类型校验
- 强制回退触发

它只负责判定：

- `Pass`
- `Fail`
- `Return Required`

它不负责：

- 产出架构答案
- 生成新的产品决定
- 生成新的术语定义
- 生成新的治理状态判断
- 代替 `07` 打包输入
- 代替 `30` 定义问题空间

## 07 / 30 / 08 的分工

- `07-repo1-to-repo2-handoff-packet-template.md`
  - 负责稳定输入打包
  - 不负责某次具体任务能不能启动
  - 不负责定义 Layer 3 的问题空间
- `30-layer-3-architecture-handoff.md`
  - 负责定义 Layer 3 的问题空间和承接边界
  - 不负责某次具体任务的准入判定
  - 不负责稳定输入打包
- `08-layer-3-task-start-template.md`
  - 负责某次具体 Layer 3 任务能不能启动
  - 不重新定义输入包
  - 不重新定义问题空间

三者不能互相替代，也不能互相长歪。

## 使用原则

- 没有通过 `Start Gate`，任务就不能进入 Repo 2 的 Layer 3 承接
- 缺输入不是“待补材料”，而是“不能开工”
- 发现上游未决、语义缺口或非架构问题，不得在 Repo 2 内私自吸收，只能失败或回退
- 本模板中的 source bundle 必须来自 `07` 的 `Canonical Source Bundle` 与当前任务直接依赖项，不得自由重组

## Task Identity

- `Task Name`：
  - `<填写本次 Layer 3 任务名称>`
- `Target Repo`：
  - `Repo 2 / System Realization Repo`
- `Target Layer`：
  - `Layer 3`
- `Task Owner / Role`：
  - `<填写当前承接角色，不写模糊描述>`
- `Bound Handoff Packet`：
  - `<填写当前任务绑定的具体 handoff packet 路径或标识>`
- `Current Status`：
  - `<Pending Gate / Pass / Fail / Return Required>`

## Required Input Package

以下输入在启动前必须齐备。  
缺任何一项，都不能开工。

- `Concrete Handoff Packet`
  - 必须存在一个基于 `07` 形成的具体 handoff packet
  - handoff packet 是前提，不是附件
- `Canonical Sources`
  - 必须附带 `07` 的 `Canonical Source Bundle`
  - 必须明确当前任务直接依赖其中哪些 canonical 文档
- `Glossary Terms`
  - 必须显式列出当前任务直接依赖的 glossary 术语清单
- `OQR Snapshot`
  - 必须显式列出当前任务直接相关的 OQR ID、当前状态与必要摘要
- `Layer 2 Accepted Decisions`
  - 必须显式列出当前任务依赖的 Layer 2 已决定项

## Canonical Source Acknowledgement

本区块表达的不是“我看过了”，而是“我接受这些上游文档作为本任务的约束来源”。

模板：

- `Accepted Canonical Sources`
  - `<列出当前任务承认的 canonical 文档>`
- `Acknowledgement Statement`
  - `<明确声明：当前任务接受这些文档作为约束来源，而不是普通参考材料>`

纪律：

- 不得在这里重新拼装一套新的 source bundle
- 不得跳过 `07` 已要求的进入路径
- 若 source bundle 不足以支撑当前任务，应转入 `Return Path`

## Questions Repo 2 Must Answer

这里只能放当前任务必须承接的架构问题。

这些问题必须同时满足：

- 来自 `30-layer-3-architecture-handoff.md` 已定义的问题空间
- 已被当前 handoff packet 收缩到本任务范围
- 属于 Repo 2 Layer 3 可以承接的架构问题

以下内容不得出现在这里：

- 产品问题
- 术语定义问题
- 治理状态判断问题
- 新的上游定义问题
- 试图重开已关闭 Layer 2 决定的问题

一旦发现混入，不能保留在这里，必须转入 `Return Path`。

模板：

- `<本任务必须回答的架构问题 1>`
- `<本任务必须回答的架构问题 2>`
- `<本任务必须回答的架构问题 3>`

## Non-Absorbable Upstream Unknowns

本区块是禁止吸收清单，不是提醒区。  
只要当前任务触到以下任一事项，Repo 2 不能自己拍板，只能停下或回退。

必须显式列出：

- 相关但未 `已正式决定` 的 OQR
- glossary 还没定义但当前任务需要的术语
- Layer 2 尚未关闭的产品边界
- 会改写默认双端点、progress、token、监管语义的事项

模板：

- `<禁止吸收的上游未决项 1>`
- `<禁止吸收的上游未决项 2>`
- `<禁止吸收的上游未决项 3>`

## Return Path

本区块是强制回退机制，不是“有问题可以回去问”的建议区。

出现以下情况时，必须回 Repo 1：

- glossary 术语不足以支持当前架构讨论
- register 中相关治理项状态不足以支持当前承接
- Layer 2 产品决定存在缺口、冲突或未正式关闭
- 输入包本身不足或冲突
- 当前任务试图重开已关闭的 Layer 2 决定
- 当前任务混入产品决策、术语决策或其他上游治理问题

回退映射：

- 术语问题 -> 回 `05-cross-layer-glossary.md`
- 决策状态问题 -> 回 `06-open-questions-register.md`
- 产品边界问题 -> 回 `20-layer-2-product-prd.md`
- 输入包本身不足或冲突 -> 回 `07-repo1-to-repo2-handoff-packet-template.md` 或其上游来源
- 架构问题空间定义不足 -> 回 `30-layer-3-architecture-handoff.md`

模板：

- `<触发条件>` / `<为什么必须回退>` / `<回到哪个上游文档>`

## Expected Layer 3 Outputs

这里只能写允许产出的结果类别，不能写结果内容、方案大意、半成品结论或候选结构偏好。

模板：

- `<允许产出的结果类别 1>`
- `<允许产出的结果类别 2>`
- `<允许产出的结果类别 3>`

## Start Gate

这是硬门槛。  
只要关键前提缺一个，就不能启动。

判定输出只能是：

- `Pass`
- `Fail`
- `Return Required`

以下任一情况出现时，`Start Gate = Fail` 或 `Return Required`：

- 没有具体 handoff packet
- 没有承认上游 canonical 输入
- 相关 OQR 状态还不够支撑当前任务
- 任务依赖 glossary 里还没有的术语
- 问题里混进了产品决策、术语决策或其他上游治理问题
- 任务在试图重开已经关掉的 Layer 2 决定

判定模板：

- `Concrete Handoff Packet`：`Pass / Fail`
- `Canonical Source Acknowledgement`：`Pass / Fail`
- `OQR Support Sufficiency`：`Pass / Return Required`
- `Glossary Sufficiency`：`Pass / Return Required`
- `Question Type Purity`：`Pass / Return Required`
- `Closed Layer 2 Decisions Reopen Check`：`Pass / Fail`
- `Final Gate Result`：`Pass / Fail / Return Required`

只有当以上检查全部通过时，任务才允许进入 Repo 2 的 Layer 3 承接。
