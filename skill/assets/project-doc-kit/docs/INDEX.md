# <项目名> 文档总入口

> 最后更新：<YYYY-MM-DD>
> 用途：作为 `<项目名>` 当前正式文档体系的唯一入口。
> 阅读原则：先看正式文档，再按需要下钻子系统现状或未来任务链；过程日志不参与主入口判断。

---

## 1. 默认阅读顺序

如果你是新线程或新接手工程师，统一按下面顺序开始：

1. [CURRENT_STATE.md](./CURRENT_STATE.md)
2. [STAGE_DECISIONS.md](./STAGE_DECISIONS.md)
3. [FUTURE_PATH.md](./FUTURE_PATH.md)
4. [IMPLEMENTATION_BOARD.md](./IMPLEMENTATION_BOARD.md)
5. [IMPLEMENTATION_PACKAGES.md](./IMPLEMENTATION_PACKAGES.md)
6. [task-chains/INDEX.md](./task-chains/INDEX.md)
7. [../<子系统A>/REALITY.md](../<子系统A>/REALITY.md)
8. [../<子系统B>/REALITY.md](../<子系统B>/REALITY.md)

如果任务只涉及某个局部模块，再看该模块的局部手册入口。

如果你需要追命令、测试、临时判断或原始审计，再看：

- [../.worklog/CURRENT.txt](../.worklog/CURRENT.txt)

---

## 2. 正式文档角色

- [CURRENT_STATE.md](./CURRENT_STATE.md)
  - 记录当前真实现状
  - 只回答“现在真实有什么 / 没有什么 / 从哪校验”

- [STAGE_DECISIONS.md](./STAGE_DECISIONS.md)
  - 记录当前阶段结论
  - 只回答“当前在哪个阶段 / 为什么这样判断 / 哪些优先”

- [FUTURE_PATH.md](./FUTURE_PATH.md)
  - 记录未来开发路径
  - 只回答“后面按什么顺序做 / 守什么硬边界 / 哪些方向已锁”

- [IMPLEMENTATION_BOARD.md](./IMPLEMENTATION_BOARD.md)
  - 记录当前版本实施范围
  - 只回答“这一版先做什么 / 不做什么 / 做到什么算交付”

- [IMPLEMENTATION_PACKAGES.md](./IMPLEMENTATION_PACKAGES.md)
  - 记录当前版本实施包分组
  - 只回答“这一版按哪几包开工 / 哪些可以并行推进”

- [task-chains/INDEX.md](./task-chains/INDEX.md)
  - 把未来路径拆成任务链
  - 只承接目标、顺序、依赖、边界和验收，不承接现状快照

- `[子系统]/REALITY.md`
  - 对应子系统当前实现事实

---

## 3. 过程日志角色

- [../.worklog/CURRENT.txt](../.worklog/CURRENT.txt)
  - 只记录命令、测试、临时判断、备份、检查点和施工过程
  - 不是正式文档，不替代现状、阶段和未来结论

---

## 4. 维护规则

- 现状变化时：
  - 更新 [CURRENT_STATE.md](./CURRENT_STATE.md)
  - 同步更新对应子系统的实现事实文档

- 阶段判断变化时：
  - 更新 [STAGE_DECISIONS.md](./STAGE_DECISIONS.md)

- 未来顺序、边界或方向变化时：
  - 更新 [FUTURE_PATH.md](./FUTURE_PATH.md)
  - 如涉及版本范围，同步更新 [IMPLEMENTATION_BOARD.md](./IMPLEMENTATION_BOARD.md)
  - 如涉及分包，同步更新 [IMPLEMENTATION_PACKAGES.md](./IMPLEMENTATION_PACKAGES.md)
  - 如需拆细，再更新 [task-chains/INDEX.md](./task-chains/INDEX.md) 与对应链文件

- 关键过程记录：
  - 统一追加到 [../.worklog/CURRENT.txt](../.worklog/CURRENT.txt)
  - 不直接把流水账搬回正式文档

---

## 5. 当前一句话结论

`<项目名>` 当前文档体系已经按“现状 / 阶段 / 未来 / 任务链 / 实现事实 / 过程日志”分层，接手时先看正式文档，再按需下钻模块现实与过程记录。
