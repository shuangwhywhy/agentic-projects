# Agentic Context Repo

这个仓库是整个大项目的 `Project Context Repo`，不是实现仓库，也不是零散文档仓库。

它的职责是把项目的上位秩序固定下来，让后续 Agent 在进入项目时先获得受控认知，再进入具体工作。

## 这个仓库负责什么

- 固定两仓库分工：`Repo 1 = context/control`，`Repo 2 = realization`
- 固定四层 hierarchy：`Layer 1 Concept/Philosophy`、`Layer 2 Product/PRD`、`Layer 3 Architecture`、`Layer 4 Implementation`
- 固定跨层 glossary，作为 Repo 1 的公共语义基准
- 沉淀 Layer 1 和 Layer 2 的稳定资产
- 为 Layer 3 和 Layer 4 提供进入条件、边界、阅读顺序、handoff 逻辑与工作约束
- 约束后续 Agent 不要越级推翻上层，不要把 execution stages 误当成项目总秩序

## 这个仓库不负责什么

- 不负责完成最终系统架构
- 不负责输出代码、运行时配置、测试脚本、部署工件
- 不把 `research / design / implementation / review` 提升为项目的第一组织原则
- 不把原始提示词原样当成最终项目结构

## 建议阅读顺序

1. [AGENTS.md](./AGENTS.md)
2. [01-repo-charter.md](./01-repo-charter.md)
3. [02-original-prompt-intake.md](./02-original-prompt-intake.md)
4. [05-cross-layer-glossary.md](./05-cross-layer-glossary.md)
5. [06-open-questions-register.md](./06-open-questions-register.md)
6. 按职责进入对应层文档：
   - [10-layer-1-concept-philosophy.md](./10-layer-1-concept-philosophy.md)
   - [20-layer-2-product-prd.md](./20-layer-2-product-prd.md)
   - [30-layer-3-architecture-handoff.md](./30-layer-3-architecture-handoff.md)
   - [40-layer-4-implementation-handoff.md](./40-layer-4-implementation-handoff.md)
7. 若要从 Repo 1 进入 Repo 2，必须再读取 [07-repo1-to-repo2-handoff-packet-template.md](./07-repo1-to-repo2-handoff-packet-template.md)
8. 若任务主题落在核心真相模型轴，默认先绑定 [07a-repo1-to-repo2-handoff-packet-core-truth-model.md](./07a-repo1-to-repo2-handoff-packet-core-truth-model.md) 这份当前首个可绑定实例，而不是自行重拼输入包
9. 若要进入 Repo 2 的 Layer 3，必须再通过 [08-layer-3-task-start-template.md](./08-layer-3-task-start-template.md) 这道启动门；`07a = Ready` 只表示可被 `08` 绑定，不表示可直接开工
10. 最后查看 [90-gap-map.md](./90-gap-map.md)

## 这个原型的核心产物

- `AGENTS.md`
  - Agent 接入入口与行为约束
- `01-repo-charter.md`
  - Repo 1 的宪章、边界、与 Repo 2 的分工
- `02-original-prompt-intake.md`
  - 原始提示词的吸纳、归位、分离与重组方式
- `05-cross-layer-glossary.md`
  - Repo 1 的跨层公共语义基准与 canonical 术语来源
- `06-open-questions-register.md`
  - Repo 1 的统一决策状态治理面与唯一 canonical register
- `07-repo1-to-repo2-handoff-packet-template.md`
  - Repo 1 向 Repo 2 移交稳定输入的 handoff 控制接口模板
- `07a-repo1-to-repo2-handoff-packet-core-truth-model.md`
  - 核心真相模型主题的首个可绑定 handoff 实例
- `08-layer-3-task-start-template.md`
  - Repo 2 Layer 3 具体任务的准入控制模板与启动门
- `10-layer-1-concept-philosophy.md`
  - 第一层的稳定哲学与不可协商边界
- `20-layer-2-product-prd.md`
  - 第二层的产品定义、能力边界与 PRD 原型
- `30-layer-3-architecture-handoff.md`
  - 给架构层的上下文入口与 handoff 约束
- `40-layer-4-implementation-handoff.md`
  - 给实现层的上下文入口与 handoff 约束
- `90-gap-map.md`
  - 当前缺口、优先补齐顺序、防漂移规则

## Repo 1 的使用方式

- 若你在做项目理解、原则确认、产品界定，工作应停留在 Repo 1
- 若你在使用或解释核心术语，先回到 [05-cross-layer-glossary.md](./05-cross-layer-glossary.md)，不要在下层文档里自行改义
- 若你在改变开放问题、临时假设或正式决定的状态，先回到 [06-open-questions-register.md](./06-open-questions-register.md)，不要在 layer 文档里私自改状态
- 若你要从 Repo 1 进入 Repo 2，先按 [07-repo1-to-repo2-handoff-packet-template.md](./07-repo1-to-repo2-handoff-packet-template.md) 的 `Canonical Source Bundle` 进入，不要把它当成普通参考文档
- 若你的任务主题落在核心真相模型轴，默认先绑定 [07a-repo1-to-repo2-handoff-packet-core-truth-model.md](./07a-repo1-to-repo2-handoff-packet-core-truth-model.md)，不要自己重新拼第一份输入包
- 若你要进入 Repo 2 的 Layer 3，必须再通过 [08-layer-3-task-start-template.md](./08-layer-3-task-start-template.md) 的启动门；未通过时不能开工
- 若你要开始系统结构设计，先完成 Repo 1 的阅读与定位，再到 Repo 2 进行 Layer 3 工作
- 若你要开始编码、测试、配置、原型实现，只能在 Repo 2 进行 Layer 4 工作
- 若你在下层发现冲突，不应直接修改下层以自洽，而应回到对应上层重新处理

## 这个原型当前状态

- Layer 1 已形成可用的 concept/philosophy 基线
- Layer 2 已形成可继续扩展的 product/PRD 基线
- 默认双端点与非端点治理角色的产品边界已经被正式吸纳
- 跨层 glossary 已形成 Repo 1 的公共语义基准
- 开放问题 register 已形成 Repo 1 的统一决策状态治理面
- Repo 1 -> Repo 2 handoff packet 模板已形成当前 handoff 控制接口
- 核心真相模型主题已经有首个可绑定 handoff packet 实例
- Layer 3 任务启动模板已形成具体任务的准入控制模板
- Layer 3 和 Layer 4 仅形成入口、边界与 handoff 约束，还没有被错误地提前实现
- 原始提示词已经被吸纳为项目要求来源，但未被当成最终结构直接照搬
