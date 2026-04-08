---
name: project-doc-routing
description: 当用户想为任何大型项目建立、重构或校准一套不混乱的文档体系时，立即使用本技能。尤其适用于这些场景：用户问“这个项目文档应该怎么搭”“接手的人先看什么”“现状、规划、施工记录怎么分开”“大型仓库的文档越写越乱怎么办”“怎么做唯一入口和权威顺序”“如何把未来任务拆成清晰链路”“文档体系搭完后怎么另起开发线程”“怎么准备全项目代码审查线程提示词”。本技能会把文档拆成总入口层、现状层、阶段/优先级层、未来路径层、任务链层、实现事实层和过程记录层，并额外交付两份线程模板提示词，帮助代理在任何大型仓库里搭出一套可接手、可校准、可持续维护的文档结构与后续协作起点。
---

# 大型项目文档分流

## 核心目标

- 为任何大型项目建立一套不混写的文档骨架。
- 先用真实代码与 git 状态校准，再回写正式文档。
- 让正式文档只保留稳定结论，把过程噪音留在工作日志。
- 在文档体系落地后，额外交付两份可直接复制的新线程提示词。

把这套体系想成一栋楼，目的是让后来的人一眼分清三件事：

- 现在真实是什么。
- 接下来准备做什么。
- 这次施工过程中发生了什么。

推荐骨架如下：

- `docs/INDEX.md` 是门厅，决定从哪进。
- `CURRENT_STATE / STAGE_DECISIONS / FUTURE_PATH / IMPLEMENTATION_*` 是楼层图和施工图。
- `docs/task-chains/*` 是未来路线图和分项验收单。
- 各子系统的实现事实文档是现场实景图。
- `.worklog/CURRENT.txt` 是施工日志，不是竣工说明。

如果用户要“直接开工”，不要只讲原则。优先读取 `references/template-map.md`，并使用 `assets/project-doc-kit/` 里的模板骨架来落地。
如果用户要“搭完文档后顺手交接开发或审查”，再读取两份线程提示词参考文件并一并交付。

## 启动动作

首次处理任意大型项目的文档请求时，按下面顺序行动：

1. 先找项目根目录和现有文档目录，确认有没有现成入口文档。
2. 读取 `references/doc-routing.md`，确认权威顺序、分流表和同步规则。
3. 如果仓库已有类似 `INDEX / CURRENT_STATE / FUTURE_PATH / task-chains / CLAUDE / REALITY / worklog` 的文件，先做映射，不要急着改名。
4. 如果仓库没有这套骨架，再按本技能的模板新建最小骨架。
5. 如果任务要改现状类文档，先检查真实代码和 `git status`，不要只凭旧文档下结论。
6. 如果用户提到“交接线程”“开发线程模板”“审查线程模板”，读取对应提示词参考文件并输出给用户。

## 开箱模式

如果用户明确希望“直接给我一套能用的文档体系”，按下面顺序做：

1. 读取 `references/template-map.md`。
2. 使用 `assets/project-doc-kit/` 作为起步骨架。
3. 先落最小骨架，再根据仓库实际模块补子系统实现事实文档。
4. 所有模板都要替换占位内容，不要把尖括号占位符原样留给用户。
5. 如果仓库已有接近等价的文件，优先做内容迁移和角色校准，不要机械复制导致重复文档。

## 提示词交付

如果用户在搭建文档体系后，还希望能直接另起线程推进工作，默认交付下面两份提示词：

1. `通用开发线程模板提示词`
2. `全项目分阶段代码审查线程模板`

交付规则：

- 开发线程提示词：读取 `references/general-development-thread-prompt.md`
- 审查线程提示词：读取 `references/phased-review-thread-prompt.md`
- 如果用户要“更适合直接发给最终用户复制”的版本，优先读取：
  - `references/general-development-thread-prompt-delivery.md`
  - `references/phased-review-thread-prompt-delivery.md`
- 审查线程提示词必须明确要求使用子代理协作
- 如果当前环境没有子代理能力，必须在提示词说明里保留“无法按该模板完整执行”的提醒
- 输出给用户时，优先保留可直接复制的整段提示词，不要只给摘要

## 先做映射

不要把“通用方法”误用成“强制统一文件名”。

先判断仓库属于哪种情况：

- `已有体系但很乱`：保留现有命名，先做唯一入口和权威顺序，再把内容拆层。
- `已有部分骨架`：缺什么补什么，不要整套推倒。
- `几乎没文档`：可以直接按推荐模板落地。

如果项目已经有更贴近团队习惯的名字，比如：

- `REALITY.md`
- `STATUS.md`
- `ROADMAP.md`
- `ARCHITECTURE_NOTES.md`

可以保留原名，但要在总入口里明确它们分别承担什么角色。

## 先做分类

先把用户请求归到下面三类之一：

- `现状`：在问“现在真实有什么、没有什么、从哪里校验”。
- `未来`：在问“下一步做什么、阶段怎么排、边界怎么定”。
- `过程`：在问“做过什么、跑了什么命令、测试怎样、备份或检查点在哪”。

如果一段内容同时混着三类信息，先拆开再写。不要把它们塞进同一份正式文档。

## 分流规则

- 问总入口、接手顺序或“先看哪份文档”：写到 `docs/INDEX.md` 或现有总入口。
- 问当前真实已实现/未实现、当前校验方式、当前硬边界：写到 `docs/CURRENT_STATE.md` 或现有现状文档。
- 问当前阶段、优先级、为什么先做哪条链：写到 `docs/STAGE_DECISIONS.md` 或现有阶段判断文档。
- 问后续主线、锁死边界、未来顺序：写到 `docs/FUTURE_PATH.md` 或现有未来路径文档。
- 问第一版范围、交付批次、开工包：写到 `IMPLEMENTATION_BOARD`、`IMPLEMENTATION_PACKAGES` 或等价实施文档。
- 问未来任务如何拆、某条链的目标、依赖、完成定义：写到 `docs/task-chains/INDEX.md` 和对应链文件。
- 问某个子系统当前代码现实：写到该子系统的实现事实文档，例如 `backend/CLAUDE.md`、`frontend/CLAUDE.md`、`services/api/REALITY.md`、`infra/FACTS.md`。
- 问模块内工作约束、配置、接口、护栏：写到局部手册入口和对应专题手册。
- 问命令、测试、临时判断、备份、检查点：只写进 `.worklog/CURRENT.txt` 或等价过程日志。

## 更新规则

- 代码现实变化：更新 `CURRENT_STATE.md`，并同步相应 `CLAUDE.md`。
- 阶段判断变化：更新 `STAGE_DECISIONS.md`。
- 未来顺序或硬边界变化：更新 `FUTURE_PATH.md`；如果影响实施范围或分包，同步实施总表和实施分包文档；如果要拆细，再回写 `docs/task-chains/*`。
- 某个子系统局部接法变化：更新该子系统的局部手册入口和对应专题手册。
- 仅是执行过程：追加 `.worklog/CURRENT.txt`，不要搬回正式文档。

## 权威顺序

如果不同文档互相冲突，按下面顺序判断：

1. 真实代码与真实 git 状态
2. 现状文档
3. 各子系统实现事实文档
4. 局部手册与专题说明

不要让旧讨论、施工日志或外部参考压过真实实现。

## 铁律

- 不要把未来计划写进现状文档。
- 不要把过程记录写进正式文档。
- 不要把 `task-chains` 写成现状快照。
- 不要把实现事实文档写成理想方案。
- 不要把“方向已锁”写成“能力已实现”。
- 不要跳过代码校准，只拿文档互相抄。

## 推荐最小骨架

如果用户要你从零开始搭，优先给出这套最小骨架：

- `docs/INDEX.md`
- `docs/CURRENT_STATE.md`
- `docs/STAGE_DECISIONS.md`
- `docs/FUTURE_PATH.md`
- `docs/IMPLEMENTATION_BOARD.md`
- `docs/IMPLEMENTATION_PACKAGES.md`
- `docs/task-chains/INDEX.md`
- 关键子系统的实现事实文档
- `.worklog/CURRENT.txt`

这套骨架的实际效果像“医院分诊”：

- 总入口负责指路。
- 现状文档负责说明体检结果。
- 未来文档负责说明治疗计划。
- 任务链负责拆成一步步执行单。
- 实现事实文档负责说明现场真实情况。
- 工作日志负责收纳施工噪音。

## 回复用户时的表达方式

- 先直接说“该看哪份文档”或“该改哪份文档”。
- 再补一句原因，说明这份文档承接的是现状、未来还是过程。
- 如果需要联动多份文件，明确指出主文件和同步文件。
- 如果发现用户把三类信息混在一起，先帮用户拆成三层，再分别落位。

## 参考资料

需要更细的分流表、更新矩阵和常见误写示例时，读取 `references/doc-routing.md`。
需要直接使用模板骨架时，读取 `references/template-map.md` 并从 `assets/project-doc-kit/` 取对应模板。
需要交付新线程提示词时，读取 `references/general-development-thread-prompt.md` 与 `references/phased-review-thread-prompt.md`。
需要交付更适合最终用户直接复制的版本时，读取 `references/general-development-thread-prompt-delivery.md` 与 `references/phased-review-thread-prompt-delivery.md`。
