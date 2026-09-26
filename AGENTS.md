# AGENTS.md

## 相关文档

| 文档 | 用途 |
|------|------|
| [README](README.md) | 项目概述、子模块列表 |
| [CONTRIBUTING](CONTRIBUTING.md) | Skill 使用和维护指南 |

### Skill 索引

| Skill | 用途 | 路径 |
|-------|------|------|
| [git-commit](.agents/skills/git-commit/SKILL.md) | 规范提交 | `.agents/skills/git-commit/SKILL.md` |
| [devops-release](.agents/skills/devops-release/SKILL.md) | 发布 Release | `.agents/skills/devops-release/SKILL.md` |
| [git-submodule](.agents/skills/git-submodule/SKILL.md) | 子模块管理 | `.agents/skills/git-submodule/SKILL.md` |
| [devops-audit](.agents/skills/devops-audit/SKILL.md) | 流程审查 | `.agents/skills/devops-audit/SKILL.md` |
| [journal-to-archive](.agents/skills/journal-to-archive/SKILL.md) | 归档一周以上日志 | `.agents/skills/journal-to-archive/SKILL.md` |

---

## 快速索引

| 任务 | 操作位置 |
|------|---------|
| 提交变更 | Skill: `git-commit` |
| 发布 Release | Skill: `devops-release` |
| 修改子模块 | Skill: `git-submodule` |
| 流程审查 | Skill: `devops-audit` |
| 记录日报 | `assets/memory/default/YYYY-MM-DD.md`（当天放集根，更早日志在 `assets/memory/default/journal/`） |
| 归档旧日志 | Skill: `journal-to-archive` |

---

## 我的工作原则

### 最小干预
- 仅在用户明确请求时操作
- 不主动创建文件（除非必要）
- 优先编辑现有文件
- 目录变更需与作者商议：作者对目录使用有严格规范，能不更改尽量不更改

### 原子提交
- 每次提交独立完整
- 不提交不完整的更改
- 验证后再提交

### 验证优先
- 修改后运行构建验证
- 前端文件操作后必须验证
- 确保更改符合预期

### 安全第一
- 不创建可能被恶意使用的代码
- 检测安全漏洞并报告
- 遵循 OWASP 最佳实践

## 输出规范

### 内容格式
- 不使用 emoji（除非用户明确请求）
- 输出简洁，适合 CLI 显示
- 使用 MyST Markdown

### 文件引用
- 使用 `code` 格式表示文件路径
- 每个引用独立，不合并
- 可选包含行号信息

### 代码示例
- 使用 fenced code blocks
- 包含语言标识符
- 保持代码简洁

## Git 提交规范

遵循 Conventional Commits 格式，详见 [CONTRIBUTING.md](CONTRIBUTING.md)。

**Commit 类型：**

| 类型 | 说明 | 示例 |
|------|------|------|
| `feat` | 新功能 | `feat: add user authentication` |
| `fix` | 修复 bug | `fix: resolve null pointer exception` |
| `docs` | 文档更新 | `docs: update README` |
| `test` | 测试相关 | `test: add unit tests for api` |
| `refactor` | 代码重构 | `refactor: simplify logic` |
| `chore` | 构建/工具 | `chore: update dependencies` |

## 重要提示

- **子模块操作前先 checkout main**：`git checkout main && git pull`
- **版本号**：使用 `vX.Y.Z` 格式（如 v1.0.0），Release 标题由 qtcloud-devops 自动生成
- **Release notes**：只包含对应版本内容
- **版本契约（v1.0.0 起；v1.2.0 修订）**：破坏性变更指**语义或模型的变更**——四层结构、边界规则、蒸馏逻辑、文件含义改变，读者按原理解会得出错误结论；必须升 major 版本（1.1.0 → 2.0.0），CHANGELOG 写明影响面。内容新增升 minor，修复升 patch
- **纯路径迁移升 minor**：目录迁移、文件重命名、归档规范变化，若内容逐字节不变、语义与模型不变，升 minor；但 CHANGELOG 必须附新旧路径映射表，且**全部已知读者（文档、skill、代码）在同一次发布内同步改完**——漏改一处即按破坏性变更处理
- **大版本 CHANGELOG 规范**：条目需包含定位说明、破坏性变更与迁移指南、Removed 清单；内容型仓库附内容总览。minor 条目不套用此规格
- **发布顺序**：先发布子模块，再发布主仓库；主仓库发布前确认所有子模块引用最新

---

## 如何维护 AGENTS.md

| 类型 | 写在哪里 |
|------|---------|
| 详细说明、工作流步骤 | `.agents/skills/` 中的 Skill 文件 |
| 给链接、导航索引 | AGENTS.md |

更新时机：新增文档、新增任务类型、重要规则变化时更新；README/Skill 已有的内容不重复。
