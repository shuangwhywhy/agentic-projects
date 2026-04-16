# Gap Map And Fill Order

本文件说明：Repo 1 原型已经形成了什么，还缺什么，接下来应按什么顺序继续补齐。

## 当前已经具备的东西

### 已具备的稳定资产

- Repo 1 的定位与边界
- Repo 1 / Repo 2 的明确分工
- 四层 hierarchy 的固定秩序
- Agent 的接入入口与行为约束
- 原始提示词的吸纳与归位规则
- 跨层 glossary 语义基准
- 开放问题 register 治理基准
- Layer 1 的 concept/philosophy 基线
- Layer 2 的 product/PRD 基线
- Layer 3 和 Layer 4 的 handoff 入口

### 当前刻意没有做的事情

- 没有在 Repo 1 中提前落定最终架构
- 没有在 Repo 1 中提前写实现方案
- 没有把 execution stages 当成顶层目录或总项目结构

## 当前最缺的内容

虽然 Repo 1 原型已经成立，但仍缺少若干会影响后续工作效率的控制资产。

### 本轮已完成：术语与对象词汇表

已经新增跨层 glossary，完成了：

- 核心词与必要邻接词的最小闭合集合
- 术语类型区分
- canonical 主名与别名规则
- 高风险混淆项约束
- 对 Layer 3 / Layer 4 的语义边界约束

### 本轮已完成：开放问题注册表

已经新增统一 register，完成了：

- 四种状态的硬边界
- 决策状态变更的唯一 canonical 入口
- 统一总表与治理字段
- 首批治理项登记
- 对 Layer 2 / Layer 3 / Layer 4 的引用纪律

### Gap 1: Handoff Packet 模板

需要一个固定模板，把 Repo 1 向 Repo 2 的输入打包成清晰、可审阅、可回溯的 handoff packet。

### Gap 2: Layer 3 任务启动模板

需要把“架构层必须回答什么”进一步做成可操作模板，减少后续 Agent 重新组织问题的成本。

### Gap 3: Layer 4 追溯模板

需要让每个实现项能明确链接回：

- 哪条 Layer 1 原则
- 哪项 Layer 2 能力
- 哪个 Layer 3 对象或流程
- 哪个验证口径

### Gap 4: 用户端点与汇报节奏原型

当前 Product/PRD 已定义需要 endpoints，但还没有形成足够明确的用户端点职责草图和默认汇报节奏原型。

## 建议的补齐顺序

1. 先补 `Repo 1 -> Repo 2 handoff packet 模板`
2. 再补 `Layer 3 架构任务启动模板`
3. 再补 `Layer 4 实现追溯模板`
4. 最后补 `用户端点职责草图与汇报节奏原型`

这个顺序的理由是：

- glossary 与 register 已统一核心语言与治理状态，下一步应先固定 handoff 输入
- 先做好 handoff，才能让 Repo 2 有稳定入口
- 模板化 Layer 3/4，才能真正降低后续 Agent 接入成本

## 如何避免再次退化成 stage 混合仓库

Repo 1 后续新增内容时，必须先回答两个问题：

1. 这是 hierarchy 资产，还是局部 execution workflow 资产？
2. 它属于上位稳定输入，还是属于 Repo 2 的实现工作？

如果回答不清，就不应直接加入 Repo 1。

## Repo 1 的持续治理规则

- 新增文档必须说明自己服务于哪一层
- 若文档只服务于具体任务推进，应优先进入 Repo 2
- 若文档会改变上位原则或产品边界，必须显式说明影响范围
- 若文档只是局部 stage 模板，不得冒充 hierarchy 文档

## 这份原型对 Repo 2 的支持方式

Repo 1 现在已经能向 Repo 2 提供：

- 可稳定继承的上位原则
- 可稳定继承的产品定义
- 可稳定继承的核心术语语义基准
- 可稳定继承的开放问题与临时假设当前状态
- 明确的架构入口
- 明确的实现入口
- Agent 接入时的阅读顺序与纪律

因此 Repo 2 不需要再从“原始提示词 + 自行猜测”开始，而可以从一个被整理好的上下文控制面开始。
