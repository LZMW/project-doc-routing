# 通用项目文档分流表

## 1. 五层结构速记

| 层级 | 作用 | 典型文件 |
|---|---|---|
| 总入口层 | 决定从哪开始读 | `docs/INDEX.md` |
| 主文档层 | 分开承接现状、阶段、未来、第一版实施 | `CURRENT_STATE.md`、`STAGE_DECISIONS.md`、`FUTURE_PATH.md`、`V1_IMPLEMENTATION_*` |
| 任务链层 | 拆未来主线，不写现状 | `docs/task-chains/*` |
| 实现事实层 | 记录前后端当前代码现实 | `backend/CLAUDE.md`、`frontend/CLAUDE.md` |
| 过程记录层 | 记录命令、测试、临时判断、备份、检查点 | `.worklog/CURRENT.txt` |

## 2. 权威顺序

发生冲突时，按这个顺序服从：

1. 真实代码与真实 git 状态
2. `docs/CURRENT_STATE.md`
3. 各子系统实现事实文档
4. 局部手册与专题说明

`task-chains`、`.worklog`、外部参考材料都不能反过来盖过当前实现事实。

## 3. 请求到文件的分流表

| 用户真正想知道什么 | 应该先看/先改哪里 |
|---|---|
| 我刚接手，先从哪看起？ | `docs/INDEX.md` |
| 现在真实做到了什么？哪些还没做？ | `docs/CURRENT_STATE.md` |
| 当前为什么先做这几条链？ | `docs/STAGE_DECISIONS.md` |
| 后面主线怎么走？哪些边界锁死了？ | `docs/FUTURE_PATH.md` |
| 当前版本到底做哪几包？能不能并行？ | `docs/IMPLEMENTATION_BOARD.md`、`docs/IMPLEMENTATION_PACKAGES.md` 或等价文档 |
| 某条未来链的目标、依赖、验收是什么？ | `docs/task-chains/INDEX.md` 与对应链文件 |
| 某个系统或模块当前代码现实是什么？ | 对应子系统实现事实文档，例如 `backend/CLAUDE.md`、`frontend/CLAUDE.md`、`services/api/REALITY.md` |
| 某个子系统怎么接？ | 对应局部手册入口与专题手册 |
| 最近跑了什么命令、做了哪些临时判断？ | `.worklog/CURRENT.txt` |

## 4. 更新矩阵

| 变化类型 | 主文件 | 联动文件 |
|---|---|---|
| 已实现/未实现现实变化 | `docs/CURRENT_STATE.md` | 对应实现事实文档 |
| 当前阶段或优先级变化 | `docs/STAGE_DECISIONS.md` | 必要时同步 `docs/FUTURE_PATH.md` |
| 未来顺序、硬边界、路线变化 | `docs/FUTURE_PATH.md` | 视影响同步 `IMPLEMENTATION_*`、`docs/task-chains/*` |
| 当前版本实施范围或分包变化 | `IMPLEMENTATION_BOARD`、`IMPLEMENTATION_PACKAGES` 或等价文档 | 必要时同步 `docs/FUTURE_PATH.md` |
| 某个子系统局部接法变化 | 对应局部手册入口与专题手册 | 必要时同步实现事实文档 |
| 只新增命令、测试、备份、检查点 | `.worklog/CURRENT.txt` | 无 |

## 5. 常见误写

- 把“准备做”写成“已经做了”。
- 把某次讨论或临时判断写成正式现状。
- 把 `.worklog` 里的过程记录抄回主文档。
- 把 `task-chains` 写成当前快照，而不是未来拆解。
- 只改一份主文档，不同步对应实现事实文档。

## 6. 从零搭建时的推荐模板

如果项目还没有体系，优先建立：

- `docs/INDEX.md`
- `docs/CURRENT_STATE.md`
- `docs/STAGE_DECISIONS.md`
- `docs/FUTURE_PATH.md`
- `docs/IMPLEMENTATION_BOARD.md`
- `docs/IMPLEMENTATION_PACKAGES.md`
- `docs/task-chains/INDEX.md`
- 若干子系统实现事实文档
- `.worklog/CURRENT.txt`

如果用户要的是“直接可复制的一套空白骨架”，不要只描述名字。去读 `template-map.md`，并直接使用 `../assets/project-doc-kit/` 中的模板。

## 7. 一个简单判断句

落笔前先问自己一句：

“这句话是在描述现在真实存在的东西、未来决定要做的东西，还是这次施工过程里发生的事情？”

答完再选文件，通常就不容易写混。
