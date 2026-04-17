# Repo 1 -> Repo 2 Handoff Packet: Core Truth Model

本文件是基于 [07-repo1-to-repo2-handoff-packet-template.md](./07-repo1-to-repo2-handoff-packet-template.md) 形成的第一份具体 handoff packet 实例。  
它是当前 `核心真相模型` 主题的首个可绑定实例，不是总包，也不是启动门。

## 文档定位与边界

本 packet 只覆盖 `项目`、`当前有效目标`、`目标版本`、`任务单元`、`progress`、`token 分类`、`监管事件` 这条核心真相模型主轴，及其与 `验证`、`验收`、`归因`、`目标变更`、`纠偏动作`、`冻结`、`返工` 的追溯关系约束。

它负责：

- 为 `核心真相模型` 主题提供第一份可被 `08` 绑定的具体输入包
- 把当前主题所必需的稳定原则、产品决定、术语语义与治理状态快照打包给 Repo 2 Layer 3
- 明确当前主题下 Repo 2 必须承接的架构问题与失配回退出口

它不负责：

- 充当 Repo 1 全量稳定输入总包
- 充当 Repo 2 Layer 3 的启动许可
- 产出架构答案或半架构稿
- 打包默认双端点责任表面专题
- 打包 token audit 深化专题
- 打包 GUI / CLI 表面专题
- 打包组织伸缩专题
- 吸收其他后续专题输入

如后续需要承接上述专题，应各自形成独立 handoff 实例，而不是继续向 `07a` 追加。

本 packet 的 `Ready` 只表示：

- 它已经具备被 [08-layer-3-task-start-template.md](./08-layer-3-task-start-template.md) 绑定的条件
- 它可以进入 Layer 3 启动判定

本 packet 的 `Ready` 不表示：

- 相关架构问题已经解决
- Repo 2 已获准开工
- 可以绕过 `08` 直接进入 Repo 2 承接

## 使用原则

- `07a` 只打包当前主题所必需的稳定输入，不扩张成混合 packet
- 若任务主题落在核心真相模型轴，默认先绑定 `07a`，而不是自行重拼输入包
- `07a` 只是可绑定实例，不是启动门；具体任务能否开始，仍由 `08` 判定
- 若承接过程中发现上游输入不足、语义不足、状态不足或产品边界不足，必须走 `Return Path`

## Packet Identity

- `Packet Name`：
  - `Core Truth Model Handoff`
- `Source Repo`：
  - `Repo 1 / Project Context Repo`
- `Target Repo`：
  - `Repo 2 / System Realization Repo`
- `Target Layer`：
  - `Layer 3`
- `Status`：
  - `Ready`
- `Scope Note`：
  - `仅覆盖核心真相模型的架构承接输入，不覆盖 UI、API、schema、event、存储、实现细节与其他专题输入`

## Canonical Source Bundle

以下文档构成 `07a` 的上游约束来源，不是普通参考列表：

1. [README.md](./README.md)
2. [AGENTS.md](./AGENTS.md)
3. [01-repo-charter.md](./01-repo-charter.md)
4. [02-original-prompt-intake.md](./02-original-prompt-intake.md)
5. [05-cross-layer-glossary.md](./05-cross-layer-glossary.md)
6. [06-open-questions-register.md](./06-open-questions-register.md)
7. [10-layer-1-concept-philosophy.md](./10-layer-1-concept-philosophy.md)
8. [20-layer-2-product-prd.md](./20-layer-2-product-prd.md)
9. [30-layer-3-architecture-handoff.md](./30-layer-3-architecture-handoff.md)

使用要求：

- `07a` 不重新拼装一套自己的 source bundle
- `07a` 只把与当前主题直接相关的上游稳定输入实例化打包
- 若 Repo 2 认为这些输入不足或冲突，必须走 `Return Path`

## Stable Inherited Inputs

本区块只记录 `核心真相模型` 主题 handoff 所必需的稳定输入，不是 Repo 1 全量稳定资产目录。

### Layer 1 Principles

- 动态目标是一等公民
- `progress` 必须建立在最小任务单元与验证结果之上
- token 优化不得压倒真实推进与持续合规
- 监管是过程能力，不是事后补丁
- 不得伪造状态、证据、进度或结果

### Layer 2 Product Decisions

- 产品必须能表达 `项目`、`当前有效目标`、`目标版本`、`任务单元`、`progress`、`token`、`监管`
- `当前有效目标` 与 `目标版本` 不能退化成静态任务列表的附属信息
- `progress` 必须可回到验证依据
- `token` 必须可记录、分类、归因、分析
- `监管` 必须可形成事件、证据、升级与纠偏闭环

### Glossary Terms

- `项目`
- `当前有效目标`
- `目标版本`
- `任务单元`
- `progress`
- `待验证进度`
- `正式进度`
- `token 分类`
- `监管事件`
- `纠偏动作`
- `验证`
- `验收`
- `归因`
- `目标变更`
- `冻结`
- `返工`

## Governance State Snapshot

本区块只带入与当前主题直接相关的治理状态快照。  
它不是状态解释区、状态裁决区或状态更新区。

本区块只允许：

- 引用与当前主题直接相关的 OQR
- 引用其当前状态
- 引用必要摘要

本区块不允许：

- 把临时假设包装成稳定输入
- 在 packet 内改写 register 的判断
- 用 packet 为 OQR 重新定性

本轮仅收录：

- `OQR-004` / `当前临时假设` / 当前只固定 `待验证进度` 与 `正式进度` 的语义区分与治理口径，不固定其产品呈现方式
- `OQR-008` / `已正式决定` / glossary 是唯一语义基准，`07a` 只消费其定义

本轮不将 `OQR-001`、`OQR-002`、`OQR-003`、`OQR-005` 带入 `07a`。若后续确认它们对核心真相模型形成直接主题级约束，再单独回到上游处理。

## Responsibility Surface

本区块只继承与当前 packet 接壤的最小责任边界，不展开默认双端点体系说明。

- 禁止改写项：
  - Repo 2 不得借当前真相模型承接重写 `OQR-001` 已关闭的默认双端点与非端点治理角色边界

## Questions Repo 2 Must Answer

本区块只承载 `07a` 绑定给 Repo 2 Layer 3 的架构承接问题。  
这些问题不是开放式研究方向，也不是架构自由发挥清单。

它们必须围绕：

- 核心对象关系
- 口径关系
- 版本变化后的追溯关系
- 审计与监管关联关系

不得混入：

- 产品补充问题
- 术语补充问题
- 治理裁决问题
- 实现便利性讨论

一旦触及这些区域，必须通过 `Return Path` 回退，而不是继续留在这里。

- `项目`、`当前有效目标`、`目标版本`、`任务单元`、`progress`、`token 分类`、`监管事件`、`纠偏动作` 之间的核心对象关系是什么
- `progress` 如何由 `任务单元 + 验证结果` 导出，并让 `待验证进度` 与 `正式进度` 保持为同一 progress 体系下的不同口径，而不是两个平行对象
- `目标变更` 与 `目标版本` 变化后，`任务单元`、`progress` 纳入规则、`token` 归因上下文、`监管事件` 追溯关系如何保持一致与可审计
- `token 分类`、`归因`、`监管事件` 与 `纠偏动作` 如何关联到 `任务单元` 与 `当前有效目标`，同时不把分类体系写成报表、不把事件写成动作

## Non-Negotiables

以下内容不是提醒，而是 Repo 2 在承接核心真相模型时不得为架构便利而突破的语义与治理红线：

- `progress` 不得退化成消息数、轮次数、提交次数或活动量
- `待验证进度` 与 `正式进度` 不得建成两个平行对象
- `token 分类` 不得被写成具体归因结果或统计报表本身
- `监管事件` 不得与 `纠偏动作` 混写
- `当前有效目标` 不得与 `目标版本`、`目标变更` 混写
- 不得为了架构便利切断验证、审计、监管三条追溯链

## Return Path

若当前承接中发现的问题属于上游输入不足、语义不足、状态不足或产品边界不足，就不应继续在 `07a` 或 Repo 2 内兜底，而应立刻回到对应上游位置。

回退映射：

- 术语缺口或现有术语不足 -> 回 [05-cross-layer-glossary.md](./05-cross-layer-glossary.md)
- OQR 状态不足以支撑当前承接 -> 回 [06-open-questions-register.md](./06-open-questions-register.md)
- `progress` / `token` / `监管` 的产品边界不足 -> 回 [20-layer-2-product-prd.md](./20-layer-2-product-prd.md)
- 当前 packet 的打包范围不足或与 handoff 控制接口冲突 -> 回 [07-repo1-to-repo2-handoff-packet-template.md](./07-repo1-to-repo2-handoff-packet-template.md)
- 当前问题已超出 `30` 定义的问题空间或承接边界 -> 回 [30-layer-3-architecture-handoff.md](./30-layer-3-architecture-handoff.md)

## L4 Placeholder

本区块只为后续实现层保留输入类别占位，不能提前泄漏实现方向、存储结构、接口形式、页面结构、技术偏好或任何轻量实现规划。

这里只保留：

- 核心对象模型追溯类别
- 验证证据链输入类别
- token 审计追溯类别
- 监管事件 / 纠偏动作追溯类别
