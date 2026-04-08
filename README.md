# project-doc-routing

> Codex 专用技能：大型项目文档分流体系

## 安装

将 `skill/` 文件夹整体复制到 Codex 技能目录即可。

```
# Codex 技能目录
your-codex-skills/
└── project-doc-routing/     ← 复制这个文件夹
    ├── SKILL.md             # 技能主文件
    ├── assets/              # 模板资源
    └── references/          # 参考文档
```

## 简介

本技能用于为任何大型项目建立一套不混乱的文档体系。它把文档拆成七层：

| 层级 | 作用 | 典型文件 |
|------|------|----------|
| 总入口层 | 决定从哪开始读 | `docs/INDEX.md` |
| 现状层 | 记录当前真实已实现/未实现 | `docs/CURRENT_STATE.md` |
| 阶段/优先级层 | 说明当前阶段和为什么先做这些 | `docs/STAGE_DECISIONS.md` |
| 未来路径层 | 后续主线、锁死边界 | `docs/FUTURE_PATH.md` |
| 任务链层 | 拆解未来任务，定义依赖和验收 | `docs/task-chains/*` |
| 实现事实层 | 各子系统的代码现实 | `backend/CLAUDE.md` 等 |
| 过程记录层 | 命令、测试、临时判断 | `.worklog/CURRENT.txt` |

## 核心理念

把文档体系想成一栋楼：

- **门厅**（INDEX）：决定从哪进
- **楼层图**（现状/阶段/未来）：告诉访客现在在哪、要去哪
- **施工图**（任务链）：拆成一步步执行单
- **现场实景图**（实现事实）：记录真实代码状态
- **施工日志**（worklog）：收纳过程噪音，不是竣工说明

## 铁律

- 不把未来计划写进现状文档
- 不把过程记录写进正式文档
- 不把 task-chains 写成现状快照
- 不跳过代码校准，只拿文档互相抄

## 技能包结构

```
skill/
├── SKILL.md                    # 技能主文件（Codex 加载用）
├── assets/
│   └── project-doc-kit/        # 开箱即用的模板骨架
│       ├── docs/               # 文档模板
│       ├── subsystems/         # 子系统模板
│       └── .worklog/           # 工作日志模板
└── references/                 # 参考文档
    ├── doc-routing.md          # 详细分流表
    ├── template-map.md         # 模板映射
    ├── general-development-thread-prompt.md      # 开发线程提示词
    ├── general-development-thread-prompt-delivery.md
    ├── phased-review-thread-prompt.md            # 审查线程提示词
    └── phased-review-thread-prompt-delivery.md
```

## 适用场景

- "这个项目文档应该怎么搭？"
- "接手的人先看什么？"
- "现状、规划、施工记录怎么分开？"
- "大型仓库的文档越写越乱怎么办？"
- "文档体系搭完后怎么另起开发线程？"

## 许可证

[MIT License](LICENSE)

## 作者

LZMW
