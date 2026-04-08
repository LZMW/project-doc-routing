# 开箱模板地图

## 1. 什么时候使用模板骨架

优先在下面三种情况下直接使用 `assets/project-doc-kit/`：

- 项目几乎没有正式文档。
- 项目文档非常零散，用户明确希望“直接搭一套新的”。
- 用户要的是“给我现成模板，不要只讲方法”。

如果仓库已经有稳定体系，不要整套照搬。先映射角色，再按需借用单个模板。

## 2. 模板文件对应关系

| 模板路径 | 用途 |
|---|---|
| `assets/project-doc-kit/docs/INDEX.md` | 总入口与阅读顺序 |
| `assets/project-doc-kit/docs/CURRENT_STATE.md` | 当前真实现状 |
| `assets/project-doc-kit/docs/STAGE_DECISIONS.md` | 当前阶段判断与优先级 |
| `assets/project-doc-kit/docs/FUTURE_PATH.md` | 后续主线和硬边界 |
| `assets/project-doc-kit/docs/IMPLEMENTATION_BOARD.md` | 当前版本实施总表 |
| `assets/project-doc-kit/docs/IMPLEMENTATION_PACKAGES.md` | 当前版本实施分包 |
| `assets/project-doc-kit/docs/task-chains/INDEX.md` | 任务链入口 |
| `assets/project-doc-kit/docs/task-chains/TASK_CHAIN_TEMPLATE.md` | 单条任务链模板 |
| `assets/project-doc-kit/subsystems/SUBSYSTEM_REALITY.md` | 子系统实现事实模板 |
| `assets/project-doc-kit/subsystems/SUBSYSTEM_GUIDE.md` | 子系统局部手册入口模板 |
| `assets/project-doc-kit/.worklog/CURRENT.txt` | 过程记录模板 |

## 3. 推荐落地顺序

1. 先落 `INDEX.md`，建立唯一入口。
2. 再落 `CURRENT_STATE.md`，固定现状真源。
3. 再落 `FUTURE_PATH.md` 与 `STAGE_DECISIONS.md`，拆开“现在”和“接下来”。
4. 然后落 `IMPLEMENTATION_BOARD.md` 与 `IMPLEMENTATION_PACKAGES.md`，把当前版本范围说清。
5. 接着落 `task-chains`，把未来主线拆成链。
6. 最后按模块补 `SUBSYSTEM_REALITY.md` 和 `SUBSYSTEM_GUIDE.md`。
7. 全程把命令、测试、备份、临时判断写进 `.worklog/CURRENT.txt`。

## 4. 使用模板时的铁律

- 替换所有占位符，不要留下 `<项目名>`、`<模块名>` 之类空标记。
- 先看真实代码和 git 状态，再填现状模板。
- 如果仓库已有等价文件，优先合并，不要制造第二套并行文档。
- 模板只是脚手架，不能替代理解仓库现实。

## 5. 线程提示词交付

如果用户在搭完文档体系后，还要继续交付“另起线程可直接使用”的提示词，再补交下面两份文件：

- `general-development-thread-prompt.md`
- `phased-review-thread-prompt.md`

其中第二份必须保留“必须使用子代理协作”的硬要求。

如果用户明确说“我要直接发给别人复制”“我要最终交付版”“我要带占位符说明的版本”，优先交付：

- `general-development-thread-prompt-delivery.md`
- `phased-review-thread-prompt-delivery.md`
