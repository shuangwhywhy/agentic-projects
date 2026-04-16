# Open Questions Register

本文件是 Repo 1 的统一决策状态治理面。  
它不是某一层的附属文档，而是 Repo 1 用来治理开放问题、临时假设、正式决定及其当前状态的唯一 canonical register。

## 文档目标与权威性说明

本 register 的目标不是“把问题记下来”，而是为 Repo 1 提供一个跨层唯一的决策状态治理面，使开放问题、临时假设和正式决定不再分散漂移。

它负责：

- 承载开放问题、临时假设、正式决定及其当前治理状态
- 固定这些治理项的当前状态、影响层级、阻塞面、owner、next action 和来源依据
- 作为决策状态变更的唯一 canonical 入口

一旦某个治理项进入本 register，后续 Layer 1 / Layer 2 / Layer 3 / Layer 4 只能引用本文件中的当前状态，不能各自维持平行状态解释。

## Register 边界与非目标

本 register 不是：

- issue tracker
- task board
- implementation backlog
- schema backlog
- architecture backlog
- feature request list

它只承载：

- 开放问题
- 临时假设
- 正式决定
- 以及它们的当前治理状态

它不吸收执行层任务、开发排期、实现步骤或代码工作项。  
若某事项已经变成执行任务，应去 Repo 2 的对应工作流处理，而不是继续停留在本 register 中。

## 当前状态定义

### 必须现在决定

- 含义：
  - 没有安全默认处理，已经阻塞或即将直接阻塞当前紧邻工作
- 判定标准：
  - 若继续不决定，会让当前 Repo 1 或其最近 handoff 无法安全继续推进
- 记录要求：
  - `当前默认处理 / 决定摘要` 必须写 `无安全默认处理` 或等价明确表述
  - `next action` 必须明确：谁来决定、依据什么、在哪个上游 canonical 文档吸纳

### 可以延后决定

- 含义：
  - 当前未决，但在既有上位约束和当前默认路径下，不阻塞最近一层工作
- 判定标准：
  - 虽然未决，但短期内可以安全保持未定状态，不会让当前紧邻工作失真或停摆

### 当前临时假设

- 含义：
  - 已经在推动当前工作，但仍不是正式决定
- 判定标准：
  - 当前工作必须继续依赖某个明确默认处理才能推进，但该处理尚未被 canonical 文档正式吸纳为稳定决定
- 记录要求：
  - `当前默认处理 / 决定摘要` 必须写清当前依赖的默认处理
  - `next action` 必须同时写明：何时回看，或在什么触发条件下升级复审

### 已正式决定

- 含义：
  - 该事项已经被 Repo 1 的 canonical 文档正式吸纳，且不再依赖临时默认处理继续推进
- 判定标准：
  - 该事项已有稳定上游落点，可被其他文档直接继承，不再需要以“先这么假设”推进
- 记录要求：
  - `来源 / 依据` 必须能指向已吸纳它的 canonical 文档或明确计划

## 状态迁移规则

**本 register 是决策状态变更的唯一 canonical 入口。**

这意味着：

- open question 变成临时假设：先改 register
- 临时假设变成已正式决定：先改 register
- 可以延后决定变成必须现在决定：先改 register
- 已正式决定若因上位变化重新变成未决：也必须先改 register

各 layer 文档不允许各自偷偷改状态，只能引用 register 的当前状态。  
如果 Layer 2 / Layer 3 / Layer 4 发现新的开放项，也必须先回到本 register 建项，再继续推进。

## 主表字段说明

- `ID`
  - 稳定标识符，格式固定为 `OQR-###`
- `条目`
  - 只写一个治理项，不能混多个未决点
- `当前状态`
  - 只能使用本文件定义的四种状态值
- `当前默认处理 / 决定摘要`
  - 对未决项写当前默认处理
  - 对正式决定写当前已吸纳的决定摘要
- `影响层级`
  - 使用 `L2` / `L3` / `L4` 或组合表示直接影响范围
- `若不决定，会卡住什么`
  - 必须写清近端阻塞面，不能写抽象担忧
- `owner`
  - 治理责任角色，不等于执行人
  - 负责推动该条目状态变化，不代表必须亲自完成所有相关工作
  - 初始使用角色名，例如 `Repo 1 Owner` / `L2 Owner` / `L3 Owner`
  - 若后续形成更具体角色体系，可更新角色名，但不能改成模糊责任描述
- `next action`
  - 必须是下一步可执行的治理动作
  - 不能写成纯备注、纯判断或纯感想
  - 对 `当前临时假设`，必须写回看时机或升级触发条件
  - 对 `必须现在决定`，必须直接指向决策责任、依据来源和吸纳落点
- `来源 / 依据`
  - 至少必须能追溯到 Repo 1 中的 canonical 文档、明确计划、已吸纳的上位约束，或本 register 已承认的临时假设来源
  - 不允许出现无来源的主观条目
  - 不接受“大家都知道”“实现上方便”这类无锚点依据

## 统一总表

| ID | 条目 | 当前状态 | 当前默认处理 / 决定摘要 | 影响层级 | 若不决定，会卡住什么 | owner | next action | 来源 / 依据 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| OQR-001 | 默认用户对接 endpoints 的最小角色集与职责合并边界 | 必须现在决定 | 无安全默认处理；不能继续只用“少数 endpoints”泛称推进下游设计 | L2 / L3 | 卡住 handoff packet、用户对接模型、组织责任结构 | L2 Owner | 由 L2 Owner 基于 `20-layer-2-product-prd.md` 的用户关系模型与 `30-layer-3-architecture-handoff.md` 的组织治理输入，在 `20-layer-2-product-prd.md` 吸纳最小 endpoints 角色集与合并边界 | `20-layer-2-product-prd.md` 当前产品层开放项；`30-layer-3-architecture-handoff.md` 对 endpoints 与责任结构的要求 |
| OQR-002 | GUI 最小可用视图优先级 | 可以延后决定 | 当前只保留产品表面对象列表，不对 GUI MVP 视图做先后排序 | L2 / L3 / L4 | 卡住后续 GUI 信息架构与前端切片，但不阻塞当前 Repo 1 治理资产 | L2 Owner | 当 GUI handoff packet 或 GUI slice 启动时回看，并将优先级结果吸纳到 `20-layer-2-product-prd.md` | `20-layer-2-product-prd.md` 产品表面对象与当前产品层开放项 |
| OQR-003 | 不同复杂度任务是否需要不同产品工作模式 | 当前临时假设 | 当前沿用单一默认产品工作模式，不额外拆复杂度模式 | L2 / L3 | 若长期不决定，会卡住复杂度分层下的产品入口与治理策略 | L2 Owner | 当 Layer 3 启动复杂度分层设计，或当前单一模式无法承接具体 handoff 时，升级复审并决定是否在 `20-layer-2-product-prd.md` 吸纳多模式策略 | `20-layer-2-product-prd.md` 当前只定义一套默认交互模型；同文件当前产品层开放项已提出该问题 |
| OQR-004 | 待验证进度与正式进度的产品呈现方式 | 当前临时假设 | 当前只固定语义区分与治理口径，不固定 UI 表达方式 | L2 / L3 / L4 | 卡住后续 GUI 呈现方案与状态可视化，但不阻塞当前语义与 handoff 约束 | L2 Owner | 当 GUI 产品切片开始，或 progress 可视化进入 Layer 3 / Layer 4 设计时回看；若出现 UI 方案冲突，立即升级复审 | `05-cross-layer-glossary.md` 已固定两者的口径关系；`20-layer-2-product-prd.md` 当前产品层开放项仍未决定其呈现方式 |
| OQR-005 | 直连指定 agent 的用户界面如何保持责任与上下文不失真 | 可以延后决定 | 当前保留“可直连但非默认模式”的产品原则，不预先固定具体 UI 处理 | L2 / L4 | 卡住后续直连模式的界面与交互治理，但不阻塞当前 Repo 1 的默认模式定义 | L2 Owner | 当直连模式进入 GUI 设计或交互 handoff 时回看，并把处理原则吸纳到 `20-layer-2-product-prd.md` | `20-layer-2-product-prd.md` 特殊模式定义与当前产品层开放项 |
| OQR-006 | Repo 1 / Repo 2 的分工固定为 context/control 与 realization | 已正式决定 | Repo 1 负责上位原则、产品定义、语义基准和 handoff；Repo 2 负责架构与实现 | L2 / L3 / L4 | 若被动摇，会让仓库职责与交付边界重新漂移 | Repo 1 Owner | 在后续文档中持续引用该决定；若出现冲突，先回 register 变更状态，再改上游 canonical 文档 | `README.md` 仓库职责说明；`01-repo-charter.md` 两仓库分工与总秩序 |
| OQR-007 | hierarchy 先于 execution stages | 已正式决定 | execution stages 只能作为局部 workflow，不能替代项目 hierarchy | L2 / L3 / L4 | 若被动摇，会让 Repo 1 重新退化成 stage 混合仓库 | Repo 1 Owner | 在新增治理文档与 handoff 文档中持续引用；若需要改变，先在 register 降级状态，再改 canonical 文档 | `01-repo-charter.md` 项目总秩序；`AGENTS.md` execution stages 地位说明 |
| OQR-008 | glossary 是 Repo 1 的公共语义基准 | 已正式决定 | 所有核心术语都先由 glossary 定义，其他文档只能消费其 semantic core | L2 / L3 / L4 | 若被动摇，会让术语解释重新分散并跨层漂移 | Repo 1 Owner | 在新增文档中持续引用 glossary；若发现缺词，先补 glossary，再登记治理项 | `05-cross-layer-glossary.md` 权威性说明；`README.md` 与 `AGENTS.md` 的强制阅读与纪律 |
| OQR-009 | 产品默认形态为 CLI + GUI 并存 | 已正式决定 | 当前产品默认承认 CLI 与 GUI 并存，而不是只选其一 | L2 / L3 / L4 | 若被动摇，会让产品边界、handoff 输入与实现目标重新失焦 | L2 Owner | 在后续产品与 handoff 文档中持续引用；如需改变，先在 register 变更状态，再回 Layer 2 canonical 文档吸纳 | `20-layer-2-product-prd.md` 产品定义；`README.md` 仓库当前状态与阅读链 |

## 使用纪律与跨文档引用规则

- 每一行只能表达一个治理项的当前状态
- 若某条目实际包含两个以上可独立迁移状态的事项，必须拆成多行
- register 中所有术语必须使用 glossary 的 canonical 主名
- 若 register 想写的新术语在 glossary 中还没有，不能直接落 register 作为正式术语
- 必须先回补 glossary，再回来登记治理项
- register 不拥有术语解释权，只消费 glossary 的语义基准

### 与各 layer 文档的关系

- Layer 2 文档只能保留开放项摘要，并指向本 register；不再形成独立开放项权威源
- Layer 3 / Layer 4 handoff 文档只能引用本 register 中已存在的治理项，不能各自新建平行未决列表
- 若下层发现新的开放项，应先回到本 register 建项，再继续推进

### 与后续工作的关系

- 本 register 记录的是治理项的当前状态，不是执行排期
- 一旦某事项从治理面进入执行面，应在 Repo 2 的具体工作流中继续推进
- 若执行工作反向暴露出新的开放项，应先回到本 register 处理状态，再继续执行
