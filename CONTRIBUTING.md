# 如何使用和维护 Skill

## Skill 概览

本项目将高频工作流封装为 Skill，位于 `.agents/skills/` 目录：

| Skill | 用途 | 触发词 |
|-------|------|--------|
| [git-commit](.agents/skills/git-commit/SKILL.md) | 规范提交 | "提交"、"commit" |
| [devops-release](.agents/skills/devops-release/SKILL.md) | 发布 Release | "发布"、"release" |
| [git-submodule](.agents/skills/git-submodule/SKILL.md) | 子模块管理 | "子模块"、"submodule" |
| [devops-audit](.agents/skills/devops-audit/SKILL.md) | 流程审查 | "审查"、"review" |
| [journal-to-archive](.agents/skills/journal-to-archive/SKILL.md) | 归档一周以上日志 | "归档"、"archive" |

每个 Skill 的 `SKILL.md` 包含：触发词、规则、工作流步骤。

## 使用 Skill

Agent 会根据用户输入的触发词自动匹配对应的 Skill 并执行。

## 维护 Skill

### 新建 Skill

```bash
mkdir -p .agents/skills/<name>
# 创建 .agents/skills/<name>/SKILL.md
```

SKILL.md 模板：

```markdown
# <name>

简要描述功能。

## 触发词

"关键词1"、"关键词2"

## 规则

- 必须遵守的约束

## 工作流

### 步骤名称

```bash
具体命令
```
```

### 修改 Skill

直接编辑 `.agents/skills/<name>/SKILL.md`，提交变更即可。

### 删除 Skill

```bash
rm -rf .agents/skills/<name>
```

## 提交规范

提交信息遵循 Conventional Commits 格式：

```bash
git commit -m "<type>: <description>"
```

| 类型 | 说明 |
|------|------|
| `feat` | 新功能 |
| `fix` | 修复 bug |
| `docs` | 文档更新 |
| `test` | 测试相关 |
| `refactor` | 代码重构 |
| `chore` | 构建/工具 |

### 提交纪律

- 子模块提交并推送后，主仓库随即提交子模块指针更新，不积压
- 验证通过再提交；提交即推送，main 更新会触发站点部署
- 一次提交只做一件事，提交后回报 GitHub 提交链接

## 版本与发布规范

### 版本契约（v1.0.0 起）

- 结构类变更（目录迁移、文件重命名、归档规范变化）属**破坏性变更**，必须升 major 版本（如 1.1.0 → 2.0.0）
- 内容新增升 minor，修复升 patch
- 子模块先发布，主仓库后发布；主仓库发布前确认所有子模块引用最新

### 大版本 CHANGELOG 规范

条目需包含：

1. **定位说明**：该版本的意义（如"首个正式发布"）
2. **破坏性变更**：单独声明，附旧路径 → 新路径迁移映射
3. **Removed 清单**：被删除的文档/目录
4. **内容总览**：内容型仓库（如 assets/*）附仓库全貌

详细流程见 [devops-release](.agents/skills/devops-release/SKILL.md)。

## 人机协作原则

1. **最小干预**：仅用户明确请求时操作
2. **原子提交**：每次提交独立完整
3. **验证优先**：修改后运行构建验证
