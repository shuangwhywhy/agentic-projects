# Layer 3 Task Start: Core Truth Model Mainline Skeleton

本文件是基于 [08-layer-3-task-start-template.md](./08-layer-3-task-start-template.md) 形成的第一份具体 `08` 启动实例。  
它绑定 [07a-repo1-to-repo2-handoff-packet-core-truth-model.md](./07a-repo1-to-repo2-handoff-packet-core-truth-model.md)，只用于 `核心真相模型` 主轴骨架任务的 Layer 3 启动判定。

## 文档定位与边界

本文件是一次 `scoped judgment`，不是 whole-project judgment。  
它只判定以下范围是否允许进入 Repo 2 的 Layer 3：

- `项目`、`当前有效目标`、`目标版本`、`任务单元`、`progress`、`token 分类`、`监管事件`、`纠偏动作` 的核心对象关系
- `progress` 由 `任务单元 + 验证结果` 导出的统一口径
- `目标变更`、`目标版本` 变化后的追溯一致性骨架
- `token 分类`、`归因`、`监管事件`、`纠偏动作` 与真相主轴的关联约束

本文件不判定以下专题是否已可启动：

- UI / GUI 呈现
- API / schema / event / 存储设计
- 默认双端点专题深化
- token audit 深化专题
- 组织伸缩专题
- 任何 Layer 4 实现方案

若任务范围扩张到上述专题，本文件的结论不再自动成立，应转入 `Return Required` 或形成新的 handoff / start gate。

## Task Identity

- `Task Name`：
  - `核心真相模型主轴骨架建模启动`
- `Target Repo`：
  - `Repo 2 / System Realization Repo`
- `Target Layer`：
  - `Layer 3`
- `Task Owner / Role`：
  - `Repo 2 Layer 3 Architect`
- `Bound Handoff Packet`：
  - [07a-repo1-to-repo2-handoff-packet-core-truth-model.md](./07a-repo1-to-repo2-handoff-packet-core-truth-model.md)
- `Current Status`：
  - `Pass`

## Required Input Package

以下输入在启动前已经齐备，且只在当前任务范围内成立。

- `Concrete Handoff Packet`
  - 已绑定 [07a-repo1-to-repo2-handoff-packet-core-truth-model.md](./07a-repo1-to-repo2-handoff-packet-core-truth-model.md)
  - `07a` 当前状态为 `Ready`
  - `07a` 已明确其 scope 只覆盖核心真相模型主轴，不覆盖 UI、API、schema、event、存储、实现细节与其他专题输入
- `Canonical Sources`
  - 必须同时承认两层来源，不能只列当前直接依赖项
  - `Full Canonical Source Bundle`
    - 本 bundle 完整继承自 `07a` 的上游 `Canonical Source Bundle`
    - 它是随 `07a` 一起附带进入本任务的 canonical 输入，不是当前 `08` 任务自由重组出来的新 bundle
    - 完整列表：
      1. [README.md](./README.md)
      2. [AGENTS.md](./AGENTS.md)
      3. [01-repo-charter.md](./01-repo-charter.md)
      4. [02-original-prompt-intake.md](./02-original-prompt-intake.md)
      5. [05-cross-layer-glossary.md](./05-cross-layer-glossary.md)
      6. [06-open-questions-register.md](./06-open-questions-register.md)
      7. [10-layer-1-concept-philosophy.md](./10-layer-1-concept-philosophy.md)
      8. [20-layer-2-product-prd.md](./20-layer-2-product-prd.md)
      9. [30-layer-3-architecture-handoff.md](./30-layer-3-architecture-handoff.md)
  - `Current Task Directly Acknowledged Sources`
    - 以下是当前任务直接依赖并显式承认的工作集，但它们不是替代上面 full bundle 的“新 source bundle”
    - 直接依赖列表：
      1. [07a-repo1-to-repo2-handoff-packet-core-truth-model.md](./07a-repo1-to-repo2-handoff-packet-core-truth-model.md)
      2. [05-cross-layer-glossary.md](./05-cross-layer-glossary.md)
      3. [06-open-questions-register.md](./06-open-questions-register.md)
      4. [10-layer-1-concept-philosophy.md](./10-layer-1-concept-philosophy.md)
      5. [20-layer-2-product-prd.md](./20-layer-2-product-prd.md)
      6. [30-layer-3-architecture-handoff.md](./30-layer-3-architecture-handoff.md)
- `Glossary Terms`
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
  - `归因`
  - `目标变更`
  - `冻结`
  - `返工`
- `OQR Snapshot`
  - `OQR-008` / `已正式决定` / glossary 是唯一语义基准，本任务只能消费不能改义
  - `OQR-004` / `当前临时假设` / 待验证进度与正式进度的产品呈现方式未定，但当前不阻塞语义建模
  - `OQR-001` / `已正式决定` / 默认双端点边界不可被当前任务重开或吞并
- `Layer 2 Accepted Decisions`
  - 产品必须表达 `项目`、`当前有效目标`、`目标版本`、`任务单元`、`progress`、`token`、`监管`
  - `当前有效目标` 与 `目标版本` 不得混写
  - `progress` 必须可回到验证依据
  - `token` 必须可记录、分类、归因、分析
  - `监管` 必须形成事件、证据、升级与纠偏闭环

## Canonical Source Acknowledgement

本区块表达的不是“我看过了”，而是“我接受这些上游文档作为本任务的约束来源”。

- `Full Canonical Source Bundle`
  - 当前任务承认 `07a` 所附带的完整上游 bundle 是本任务的 canonical 输入底座
  - 该 bundle 来自 `07a` 的上游 `Canonical Source Bundle`，不是当前任务重新拼装的新 bundle
- `Current Task Directly Acknowledged Sources`
  - 当前任务直接依赖并显式承认以下文档：
    - [07a-repo1-to-repo2-handoff-packet-core-truth-model.md](./07a-repo1-to-repo2-handoff-packet-core-truth-model.md)
    - [05-cross-layer-glossary.md](./05-cross-layer-glossary.md)
    - [06-open-questions-register.md](./06-open-questions-register.md)
    - [10-layer-1-concept-philosophy.md](./10-layer-1-concept-philosophy.md)
    - [20-layer-2-product-prd.md](./20-layer-2-product-prd.md)
    - [30-layer-3-architecture-handoff.md](./30-layer-3-architecture-handoff.md)
- `Acknowledgement Statement`
  - 当前任务接受 `07a` 所附带的 full canonical source bundle 作为上游约束来源，并对上述直接依赖工作集做显式承认；若输入不足，必须走 `Return Path`，不得在 Repo 2 私自补定义、补决策或重组 source bundle。

## Questions Repo 2 Must Answer

以下问题都已经被 `07a` 收缩到当前任务范围内，并且属于 `30-layer-3-architecture-handoff.md` 已定义的 Layer 3 问题空间。

- `项目`、`当前有效目标`、`目标版本`、`任务单元`、`progress`、`token 分类`、`监管事件`、`纠偏动作` 的核心对象关系是什么
- `progress` 如何由 `任务单元 + 验证结果` 导出，并把 `待验证进度` 与 `正式进度` 保持在同一 progress 体系下，而不是两个平行对象
- `目标变更` 与 `目标版本` 变化后，`任务单元` 纳入规则、`progress` 追溯、`token` 归因上下文、`监管事件` 关联如何保持一致
- `token 分类`、`归因`、`监管事件`、`纠偏动作` 如何关联到 `任务单元` 与 `当前有效目标`，同时不把分类写成报表、不把事件写成动作

## Non-Absorbable Upstream Unknowns

以下事项只要被当前任务触达，Repo 2 就不能自己拍板，只能停下或回退。

- `OQR-004`
  - `待验证进度` 与 `正式进度` 的产品呈现方式仍未关闭
  - 若任务开始要求 UI 呈现或状态可视化决策，必须回退，不能在本任务内吸收
- `OQR-003`
  - 不同复杂度任务是否需要不同产品工作模式仍是 `当前临时假设`
  - 若任务开始编码多模式真相模型或复杂度分层治理结构，必须回退，不能在本任务内吸收
- `07a` scope boundary
  - `07a` 未打包默认双端点专题、组织伸缩专题、token audit 深化专题
  - 若当前任务需要这些输入，必须回退或另建 handoff，而不是在本任务内扩张吸收

## Return Path

以下回退路径是强制映射，不是建议项。

- `需要新术语或现有术语不足`
  - 当前任务若发现 glossary 语义无法支撑对象建模，就不能在 Repo 2 私自补词
  - 回到 [05-cross-layer-glossary.md](./05-cross-layer-glossary.md)
- `需要改 OQR 状态或吸收新的开放项`
  - 当前任务若发现现有治理状态不足以支撑承接，必须先回 register 处理状态，而不是在 task-start 文档里自定状态
  - 回到 [06-open-questions-register.md](./06-open-questions-register.md)
- `需要补产品边界`
  - 当前任务若触及 progress 呈现、多模式产品策略、默认双端点责任面等产品边界，必须先回 Layer 2
  - 回到 [20-layer-2-product-prd.md](./20-layer-2-product-prd.md)
- `需要扩展 packet 范围或超出 Layer 3 问题空间`
  - 当前任务若超出 `07a` 打包范围，或超出 `30` 已定义的承接边界，就不能继续沿当前启动门推进
  - 回到 [07a-repo1-to-repo2-handoff-packet-core-truth-model.md](./07a-repo1-to-repo2-handoff-packet-core-truth-model.md) 或 [30-layer-3-architecture-handoff.md](./30-layer-3-architecture-handoff.md)

## Expected Layer 3 Outputs

这里只写允许产出的结果类别，不写结果内容。

- 核心对象模型与关系约束
- `progress` 导出与追溯规则
- `目标版本 / 目标变更 / 任务单元 / token / 监管` 的一致性约束
- 可供 Layer 4 继承的追溯类别与边界说明

## Start Gate

这是当前任务范围内的硬门槛判定。

- `Concrete Handoff Packet`：`Pass`
- `Canonical Source Acknowledgement`：`Pass`
- `OQR Support Sufficiency`：`Pass`
- `Glossary Sufficiency`：`Pass`
- `Question Type Purity`：`Pass`
- `Closed Layer 2 Decisions Reopen Check`：`Pass`
- `Final Gate Result`：`Pass`

判定理由：

- `07a` 已是 `Ready` 的具体 packet，且附带完整上游 canonical source bundle
- 当前任务只消费已存在 glossary、已接受的 Layer 2 决定与 `30` 已定义问题空间，没有要求 Repo 2 代替上游补义或补决策
- 当前仍未关闭的事项只影响产品呈现或更大专题扩张，不改写本次“主轴骨架”任务的架构启动前提

## Acceptance Checks

- 本文件显式声明自己是 `scoped judgment`，不是 whole-project judgment
- 本文件同时出现 `Full Canonical Source Bundle` 与 `Current Task Directly Acknowledged Sources` 两层，且前者明确来自 `07a` 上游 bundle，不是当前任务自己重组的 bundle
- 本文件不引入 UI、API、schema、event、数据库、表结构、模块实现方案、页面结构等实现或方案化内容
- 本文件不重开 `OQR-001`，也不把 `待验证进度` 与 `正式进度` 写成两个平行对象
- 本文件中的问题列表全部可以回指到 `07a` 与 `30` 已定义的问题空间
- 本文件将当前未关闭但不阻塞的事项放入 `Non-Absorbable Upstream Unknowns` 与 `Return Path`，不留成模糊备注
