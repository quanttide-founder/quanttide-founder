# AGENTS.md

不要过度思考：直接动手，做必要的最小改动，不发散不铺开。变更一律提交并推送（子模块逐层指针一并更新），不必逐次确认。

## 相关文档

| 文档 | 用途 |
|------|------|
| [README](README.md) | 项目概述、子模块列表 |
| [CONTRIBUTING](CONTRIBUTING.md) | 工作原则、输出规范、第二大脑功能与边界、Skill 使用维护、版本契约 |

## 快速索引

| 任务 | 操作位置 |
|------|---------|
| 提交变更 | Skill: `git-commit`（规范见 CONTRIBUTING） |
| 发布 Release | Skill: `devops-release` |
| 修改子模块 | Skill: `git-submodule` |
| 流程审查 | Skill: `devops-audit` |
| 记录日报 | `assets/memory/default/YYYY-MM-DD.md`（当天放集根，更早日志在 `assets/memory/default/journal/`） |
| 归档旧日志 | Skill: `journal-to-archive` |
| 移交领域归档 | Skill: `archive-to-domain` |

## 如何维护 AGENTS.md

| 类型 | 写在哪里 |
|------|---------|
| 详细说明、工作流步骤 | `.agents/skills/` 中的 Skill 文件 |
| 协作原则、输出规范、背景理解、版本契约 | [CONTRIBUTING.md](CONTRIBUTING.md) |
| 给链接、导航索引 | AGENTS.md |

更新时机：新增文档、新增任务类型、重要规则变化时更新；README/Skill/CONTRIBUTING 已有的内容不重复。
