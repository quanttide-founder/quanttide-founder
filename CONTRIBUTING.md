# 协作与贡献指南

## Skill 概览

本项目将高频工作流封装为 Skill，位于 `.agents/skills/` 目录：

| Skill | 用途 | 触发词 |
|-------|------|--------|
| [git-commit](.agents/skills/git-commit/SKILL.md) | 规范提交 | "提交"、"commit" |
| [devops-release](.agents/skills/devops-release/SKILL.md) | 发布 Release | "发布"、"release" |
| [git-submodule](.agents/skills/git-submodule/SKILL.md) | 子模块管理 | "子模块"、"submodule" |
| [devops-audit](.agents/skills/devops-audit/SKILL.md) | 流程审查 | "审查"、"review" |
| [journal-to-archive](.agents/skills/journal-to-archive/SKILL.md) | 归档一周以上日志 | "归档"、"archive" |
| [archive-to-domain](.agents/skills/archive-to-domain/SKILL.md) | 归档站资源移交领域 archive | "移交"、"领域归档" |

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

## 记忆集划分与提炼

`assets/memory` 的记忆按主题域分集（详见 `assets/memory/AGENTS.md`）。集与集之间有**提炼关系**，不是并列：

- **default（创业与个人主线）只保留 `journal/` 与 `profile/`**——时间线 + 个人特征两层，不放 roadmap / insight / intention。
- **work（工作主线）从 default 提炼**：工作相关的主体（业务、组织、平台、AI 协作）归 `work/` 的各层。
- **fiction（写作主线）同理**：保留 `journal/` 与 `profile/`（创作动机 / 创作方法 / 创作困境），另有 `history/`、`library/` 放作品与素材。
- **提炼不丢内容**：从 default 收进 work 的条目按主题落位；重复的合并，独有的保留。

## 发布规范

- 子模块先发布，主仓库后发布；主仓库发布前确认所有子模块引用最新
- 子模块操作前先 checkout main：`git checkout main && git pull`

详细流程见 [devops-release](.agents/skills/devops-release/SKILL.md)。

## 创始人第二大脑：功能与边界

创始人第二大脑（`assets/memory`）的定位是**个人感受与源头的提纯层**：日志中唯一不可替代的内容是个人的情绪、边界体验与状态收束，这是蒸馏个人档案的最纯原料。工作想法与公司事务随处可读，混入会稀释信号——日志里的饮食规则即判据：AI 开始读不出重点时，就该提纯。

| 主体 | 内容 | 归宿 |
|------|------|------|
| 个人 | 感受、边界体验、状态收束、日志管理元规则 | `assets/memory` 的 `default/` 集 |
| 创作 | 叙事日志与创作档案 | `assets/memory` 的 `fiction/` 集；存量 write 归档在 `quanttide-write` 仓库 `data/archive/` |
| 滁州公司 | 公司启用、业务市场、品牌策略、资产组织 | `roadriver-tech` 仓库 `data/journal/` |
| 工作 | 系统治理、工具链、组织结构、职业定义、AI 观点解读 | `quanttide-work` 仓库 `data/context/quanttide-founder/` |
| 游戏 | 游戏日志与设计档案 | `quanttide-work` 仓库 `data/context/quanttide-founder/game/` |

运作逻辑（对应元目标「从依赖个人到依赖规则」）：

1. **个人孵化**：个人空间只产生源头（感受与问题），保持单人交互的轻量与独立可发版。
2. **溢出度量**：迁出量即个人向组织的资源溢出量，是可观测的贡献指标。
3. **提交组织**：成熟想法按主体迁入对应组织仓库，成为可交付资产（收复领土、驱逐他者）。
4. **规则化分流**：判定与流程固化在 `assets/memory/default/README.md` 与各 Skill 中，由 AI 自主执行，创始人一对一投入递减。

## 人机协作原则

1. **最小干预**：仅在用户明确请求时操作；不主动创建文件（除非必要）；优先编辑现有文件；目录变更需与作者商议，能不更改尽量不更改
2. **原子提交**：每次提交独立完整；不提交不完整的更改；验证后再提交
3. **验证优先**：修改后运行构建验证；前端文件操作后必须验证；确保更改符合预期
4. **安全第一**：不创建可能被恶意使用的代码；检测安全漏洞并报告；遵循 OWASP 最佳实践

## 输出规范

- 不使用 emoji（除非用户明确请求）；输出简洁，适合 CLI 显示；使用 MyST Markdown
- 文件路径用 `code` 格式，每个引用独立、不合并，可选包含行号
- 代码示例用 fenced code blocks，包含语言标识符，保持简洁
