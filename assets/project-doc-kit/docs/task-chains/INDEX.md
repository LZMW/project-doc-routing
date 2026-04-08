# <项目名> 任务链索引

> 最后更新：<YYYY-MM-DD>
> 用途：把未来开发路径拆成可执行任务链。
> 说明：这里只写目标、依赖、边界和验收，不写现状快照。

---

## 1. 阅读方式

- 要看当前现状：回到 [../CURRENT_STATE.md](../CURRENT_STATE.md)
- 要看当前阶段结论：回到 [../STAGE_DECISIONS.md](../STAGE_DECISIONS.md)
- 要看未来总顺序：回到 [../FUTURE_PATH.md](../FUTURE_PATH.md)
- 要看当前版本范围：回到 [../IMPLEMENTATION_BOARD.md](../IMPLEMENTATION_BOARD.md)
- 要看当前版本分包：回到 [../IMPLEMENTATION_PACKAGES.md](../IMPLEMENTATION_PACKAGES.md)

---

## 2. 任务链列表

| # | 链名 | 文件 | 当前状态 |
|---|---|---|---|
| 01 | `<链名1>` | `[01-<slug>.md](./01-<slug>.md)` | `<未开始/进行中/完成>` |
| 02 | `<链名2>` | `[02-<slug>.md](./02-<slug>.md)` | `<未开始/进行中/完成>` |
| 03 | `<链名3>` | `[03-<slug>.md](./03-<slug>.md)` | `<未开始/进行中/完成>` |

---

## 3. 使用规则

- 任务链只写未来目标、依赖、边界和验收
- 现状事实统一写在正式现状文档里
- 施工过程统一写入 `.worklog`
- 如果某条链的边界变化，先更新 `FUTURE_PATH.md`，再回写这里
