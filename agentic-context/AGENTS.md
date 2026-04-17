# Agent Entry Protocol

任何 Agent 进入这个仓库时，都必须先完成定位，再开始工作。

## 你先要回答的五个问题

1. 我当前被要求处理的是哪一层？
2. 这一层在 Repo 1 中是“实质内容层”还是“入口/约束层”？
3. 哪些内容已经由上层确定，不能被我直接推翻？
4. 哪些内容仍是开放项，但必须在既有边界内处理？
5. 我现在是否真的已经被授权进入 execution-stage workflow？

## 强制阅读顺序

1. [README.md](./README.md)
2. [01-repo-charter.md](./01-repo-charter.md)
3. [02-original-prompt-intake.md](./02-original-prompt-intake.md)
4. [05-cross-layer-glossary.md](./05-cross-layer-glossary.md)
5. [06-open-questions-register.md](./06-open-questions-register.md)
6. 根据任务进入对应层文档
7. 若要进入 Layer 3 或 Layer 4，必须先看完 [30-layer-3-architecture-handoff.md](./30-layer-3-architecture-handoff.md) 或 [40-layer-4-implementation-handoff.md](./40-layer-4-implementation-handoff.md)
8. 若要真正进入 Repo 2，必须再承认 [07-repo1-to-repo2-handoff-packet-template.md](./07-repo1-to-repo2-handoff-packet-template.md) 这个 handoff 控制接口
9. 若要真正进入 Repo 2 的 Layer 3，必须再通过 [08-layer-3-task-start-template.md](./08-layer-3-task-start-template.md) 这道启动门

## 角色定位规则

- 在 Repo 1 中，Agent 的首要身份不是“自由分析者”，而是“受约束的项目参与者”
- 你必须先接受 hierarchy，再在 hierarchy 内工作
- 你不能因为看到了原始提示词、旧习惯或局部实现想法，就把自己抬升到比 Layer 1/2 更高的位置

## 术语基准纪律

- [05-cross-layer-glossary.md](./05-cross-layer-glossary.md) 是 Repo 1 的公共语义基准与强制阅读项
- glossary 一旦定义术语，后续 Layer 1/2/3/4 默认不得各自重定义
- 下层若只是在说明如何使用这些术语，可以补充 operational context；但不能改写 semantic core
- 若发现现有术语不足以支撑工作，应先回到 Repo 1 补 glossary，再继续下层推进

## 治理状态纪律

- [06-open-questions-register.md](./06-open-questions-register.md) 是 Repo 1 的统一决策状态治理面
- 开放问题、临时假设、正式决定的状态变更，只能先在 register 中发生
- Layer 1/2/3/4 文档只能引用 register 的当前状态，不能各自维持平行状态
- 若下层发现新的开放项，应先回到 register 建项，再继续推进

## Handoff 控制接口纪律

- [07-repo1-to-repo2-handoff-packet-template.md](./07-repo1-to-repo2-handoff-packet-template.md) 是进入 Repo 2 前必须承认的控制接口
- `07` 只打包稳定输入，不拥有独立术语定义权、状态定义权或新决定生成权
- 若 Repo 2 觉得输入不足或冲突，必须按 `07` 的 `Return Path` 回 Repo 1，而不是在 Repo 2 内私自补定义

## Layer 3 启动门纪律

- [08-layer-3-task-start-template.md](./08-layer-3-task-start-template.md) 是进入 Repo 2 Layer 3 前必须通过的启动门
- `08` 负责某次具体任务能不能启动，不负责打包稳定输入，也不负责重新定义 Layer 3 问题空间
- 没有通过 `08` 的 `Start Gate`，任务就不能进入 Repo 2 的 Layer 3 承接

## 层级纪律

### Layer 1

- 负责项目抽象定义、工程哲学、方法论、不可协商边界
- 这里形成的是上位判断基准
- 下层不能以“实现更方便”或“架构更漂亮”为由绕开它

### Layer 2

- 负责产品定义、PRD、用户目标、能力边界、交付方式
- 这里形成的是产品层面的稳定输入
- Layer 3 必须解释如何承接它，而不是替换它

### Layer 3

- 在 Repo 1 中只存在为 `architecture handoff`
- 你可以定义架构问题空间、输入条件、必须回应的问题、禁止越过的边界
- 你不可以在 Repo 1 中把最终架构实现成既成事实

### Layer 4

- 在 Repo 1 中只存在为 `implementation handoff`
- 你可以定义实现进入条件、验证口径、追溯要求、执行工作流约束
- 你不可以在 Repo 1 中偷偷把实现层细节当成既定方案落地

## Execution Stages 的地位

- `research / design / implementation / review` 是局部 workflow，不是整个项目的 hierarchy
- 只有当你的层级定位已经明确，且任务被切成具体工作项时，才允许进入 execution stages
- execution stages 只能服务于某个明确问题、明确任务、明确范围，不能反向统治 Repo 1

## 发现冲突时怎么做

- 若实现想法与架构入口冲突：回到 Layer 3 处理
- 若架构设想与产品定义冲突：回到 Layer 2 处理
- 若产品定义与上位原则冲突：回到 Layer 1 处理
- 若某个术语在下层工作中不够用：先回到 glossary 处理
- 若某个治理项的状态需要变化：先回到 register 处理
- 若原始提示词中的片段与当前层级结构冲突：先做归位判断，不得原样搬运

## 禁止行为

- 禁止把 Repo 1 误做成实现仓库
- 禁止把 execution stages 升格为总项目结构
- 禁止绕开 Layer 1/2 直接定义 Layer 3/4 的最终结果
- 禁止绕开 glossary 在下层文档里私自造义或改义
- 禁止绕开 register 在下层文档里私自改治理项状态
- 禁止以“用户没逐项列出”为理由忽略关键 open questions
- 禁止站在仓库外重新否定“两仓库 + 四层 hierarchy”的总设计
- 禁止把原始提示词当成项目结构本身直接继承

## 允许行为

- 允许在既有边界内主动补全完成项目所必需的关键缺口
- 允许把原始提示词中的混合内容拆开并重新归位
- 允许为 Layer 3/4 设计明确 handoff 入口、决策前提、阅读顺序、约束和升级逻辑
- 允许把下层发现的问题上推，但不允许下层私自改写上层

## 进入 Repo 2 的前置判断

只有同时满足以下条件，才应进入 Repo 2：

- 当前任务确实属于 Layer 3 或 Layer 4
- Layer 1 和 Layer 2 已能提供稳定输入
- glossary 已能提供稳定的核心术语语义
- register 已能提供开放问题与临时假设的当前状态
- handoff packet 已能提供进入 Repo 2 的稳定控制接口
- Layer 3 任务启动模板已完成当前任务的准入检查
- 尚未确定的事项被标注为开放项，而不是被伪装成已决事实
- 目标、任务、组织、token、监管四类关键要求没有被遗漏
- 当前工作不再是“理解项目”，而是“承接项目并推进具体产物”
