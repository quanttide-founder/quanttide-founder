# CHANGELOG

本文件记录 quanttide-founder 仓库的所有重要变更。

## 格式

基于 [Keep a Changelog](https://keepachangelog.com/) 格式：
- `Added`：新增功能
- `Changed`：变更现有功能
- `Deprecated`：即将移除的功能
- `Removed`：已移除的功能
- `Fixed`：Bug 修复
- `Security`：安全相关变更

**工作流程**：创建 Release 之前必须先更新此文件。

## [1.1.2] - 2026-09-26

日志归档能力与子模块同步：新增 journal-to-archive skill（跨 submodule 归档一周以上旧日志），memory 子模块升至 v1.1.1。

### Added

- **journal-to-archive Skill**：`assets/memory/journal/` → `assets/archive/journal/` 一周以上日志归档（7 天截止、双侧工作区与冲突检查、双侧提交）；AGENTS.md、CONTRIBUTING.md、.agents/README.md 索引同步

### Removed

- **memory-to-fiction Skill**：取材 skill 移除

### 子模块

- **assets/memory → v1.1.1**：journal-to-insight 认知洞察层（insight/ 四主题，已确认/假说分级）与三蒸馏触发规则
- **assets/fiction**：指针更新至远端 main 最新（+27 提交，目录重组与新稿）

## [1.1.1] - 2026-09-26

Skill 体系整顿与创作取材能力：新增 memory-to-fiction 取材 skill，devops 系列 skill 改名归位，docs-deploy 迁出至 gallery 仓库。

### Added

- **memory-to-fiction Skill**：从 memory 五轴档案按需取材供给创作（选轴 → 主体转换 → 落盘），单向只读，含试写验证协议
- **apps/qtfounder**：provider 部署至阿里云 FC custom runtime，新增 secret key 访问控制

### Changed

- **Skill 改名**：`devops-commit` → `git-commit`，`devops-submodule` → `git-submodule`，`devops-review` → `devops-audit`；AGENTS.md、CONTRIBUTING.md、.agents/README.md 索引同步
- **AGENTS.md**：移除「自我更新」节（归档站不作业务用途）；快速索引改用完整 skill 名并补流程审查条目
- **仓库链接**：迁移至 quanttide-founder 组织后链接同步更新

### Removed

- **docs-deploy Skill**：内容迁移至 quanttide-gallery-of-devops（`docs/gallery/myst-markdown/deploy.md`）
- 移除 `.quanttide` 配置

### 子模块

- **assets/memory → v1.1.0**：五轴档案（emotions/values/triggers/methods/expressions）与双蒸馏 skill（journal-to-profile / journal-to-roadmap）、主题路线图首批、AGENTS/README 重组
- apps/qtfounder、assets/fiction、assets/archive 等指针更新，详见各子模块 CHANGELOG

## [1.1.0] - 2026-08-15

### Added

- **packages/quanttide-founder-toolkit**：新增子模块（新增 `packages/` 目录），工具包仓库初始化
- **apps/qtfounder**：site 进入 v0.1.0 系列迭代（alpha 阶段），新增 studio 初始化、docs 体系（user-guide / api-reference / STATUS.md）、资产契约与数据模型文档、创作职能分组导航、资产目录实现
- **assets/memory**：新增 intention 概念、insight 条目、转化方法论、fiction roadmap

### Changed

- **apps/qtfounder**：移除 /brain 页面，SPA 路由修复（basename、200 keys），创作页实现与简化，logo 量潮
- **assets/fiction**：包子店成稿，作品编号重排
- **assets/memory**：叙事化重写、意图准确化

### Submodules

- 全部 9 个子模块更新至各自最新版本

## [1.0.1] - 2026-08-10

### Changed

- **README / AGENTS / CONTRIBUTING**：按 v1.0.0 规范更新（目录结构、子模块列表、Skill 索引、版本契约与发布规范）
- **CHANGELOG**：修正 v1.0.0 条目中子模块数量（9 → 8）

## [1.0.0] - 2026-08-10

首个正式发布（1.0.0）：核心资产子仓库 archive / fiction / memory 已全部升级至 v1.0.0，子模块结构趋于稳定，后续遵循语义化版本规范，破坏性变更将单独声明。

### Changed

- **assets/archive**：更新至 v1.0.0，journal 日报备份归档扩展至 2026-07-28
- **assets/fiction**：更新至 v1.0.0，新增重生系列与大量场景成稿、创作文档
- **assets/memory**：更新至 v1.0.0，report 与 roadmap 目录扁平化，新增 voice-input 报告
- **apps/qtfounder**：更新至最新提交（site 目录重构）
- **apps/qtgame-war / examples/default**：更新至最新提交

### Removed

- **asset-vision skill**：移除过时技能（`.agents/skills/asset-vision/`）

### Submodules

- 全部 8 个子模块更新至各自最新版本

## [0.8.1] - 2026-06-27

### Removed

- **apps/qtadmin**：移除 qtadmin 子模块

### Changed

- **assets/memory**：更新至最新提交，简化 fiction 路线图

## [0.8.0] - 2026-06-27

### Added

- **apps/qtgame-weiqi**：新增围棋游戏子模块

### Changed

- **子模块路径迁移**：`docs/fiction` → `assets/fiction`，`docs/memory` → `assets/memory`
- **fiction 子模块**：更新至 v0.4.0，新增母题分析提纲和创作情境引导
- **memory 子模块**：更新至 v0.5.0，新增写作方法论和写作云蓝图

### Removed

- **ROADMAP.md**：移除过时的路线图文件

## [0.7.4] - 2026-06-12

### Changed

- **docs/archive 子模块**：移至 `assets/archive`
- **docs/fiction 子模块**：更新子模块引用；重新组织 1_1 咖啡厅重逢提纲，新增创作情境引导与知名校友心理活动
- **docs/memory 子模块**：更新子模块引用

### Added

- **assets/**：新增目录，添加 `.gitkeep`

## [0.7.3] - 2026-06-01

### Changed

- **docs/archive 子模块**：更新至 v0.4.0
- **docs/memory 子模块**：更新子模块引用
- **examples 子模块**：移除 company、execute、game、human、innov、org 子模块，保留 default

## [0.7.2] - 2026-05-28

### Removed

- **apps/qtadmin 子模块**：移除
- **assets/context-of-knowledge-engineering 子模块**：移除，迁移至 quanttide-knowl docs/context

### Changed

- **archive 子模块**：从 archive/ 移至 docs/archive/
- **docs/memory 子模块**：归档大量内容至 docs/archive（journals、context、brochure、report、profile、vision、essay、laboratory、roadmap）；handbook 整理为正式章程

## [0.7.1] - 2026-05-15

### Changed

- **archive 子模块**：从 docs/archive 移至 archive/

## [0.7.0] - 2026-05-15

### Added

- **examples/default 子模块**：新增 quanttide-example-of-founder 示例仓库

### Changed

- **qtadmin 子模块**：更新至最新提交
- **qtgame-war 子模块**：更新至最新提交
- **fiction 子模块**：更新至 v0.2.0-47
- **memory 子模块**：更新至 v0.4.3-121
- **archive 子模块**：更新至 v0.3.1-3

### Fixed

- **examples/default 子模块**：修复本地提交被远端覆盖的问题

## [0.6.2] - 2026-05-08

### Changed

- **fiction 子模块**：更新至 v0.2.0，新增夜市约会、便利店闲坐、朋友圈互动等场景成稿
- **memory 子模块**：更新至 v0.4.3，新增 journal 日报（2026-05-06 ~ 2026-05-08）

### Submodules

- fiction：v0.1.0 → v0.2.0
- memory：v0.4.2 → v0.4.3

---

## [0.6.1] - 2026-05-06

### Changed

- **日志归档到 archive**：将 memory 子仓库中 journal/default/、product/、game/、qtcloud/ 批量备份至 archive 子仓库
- **memory 子模块引用更新**：更新至 v0.4.2（移除已归档目录，新增 2026-05-06 日报）
- **archive 子模块引用更新**：更新至 v0.3.1（接收 memory 归档内容）
- **qtadmin 子模块引用更新**：更新至最新提交
- **qtgame-war 子模块引用更新**：更新至最新提交

### Submodules

- memory：v0.4.0 → v0.4.2
- archive：v0.3.0 → v0.3.1
- qtadmin：cli/v0.0.1-beta.5-35 → cli/v0.0.1-beta.5-48
- qtgame-war：更新至最新提交

---

## [0.6.0] - 2026-05-05

### Added

- **qtadmin 子模块**：新增管理后台子项目
- **文档归档工作流**：从 memory 子仓库向 archive 子仓库归档日报和写作日志

### Changed

- **AGENTS.md**：更新子模块列表和工作原则
- **子模块引用全面更新**：所有子模块更新至最新版本

### Submodules

- memory：更新至 v0.4.0，清理过时文件，归档日报，重构目录结构
- fiction：更新至 v0.1.0（首个正式版本）
- archive：更新至 v0.3.0，接收 archive 归档
- qtadmin：新增子模块，添加 assets/

---

## [0.5.2] - 2026-05-03

### Changed

- **AGENTS.md 清理**：移除冗余内容，优化结构

### Submodules

- memory：更新至最新提交
- fiction：更新至最新提交
- qtgame-war：更新至最新提交，包含 Flutter 初始化、兵力模块 PMD、历史资产、战斗文档扩展、场景资产
- qtgame-tycoon：更新至最新提交

---

## [0.5.1] - 2026-05-01

### Added

- **qtgame-war 子模块**：新增战争叙事游戏子项目
- **transfer.md**：新增学习迁移 essay，记录 SaaS 工程能力到游戏架构的映射认知

### Removed

- **旧原型代码**：删除 `apps/qtgame-war/src/` 目录（HTML 单文件原型已废弃）

### Changed

- **文档迁移**：将 `docs/memory/platform/` 下的 add.md / prd.md / qa.md 移至 `apps/qtgame-war/docs/` 对应目录
- **设计文档重构**：`apps/qtgame-war/docs/add/` 丢弃旧模块化方案，以架构设计文档作为入口
- **essay 重构**：prototype.md 按认知过程重新组织

### Submodules

- qtgame-war：新增子模块，包含架构设计、PRD、QA 文档
- memory：更新至最新提交，移除 platform/ 目录文件，新增 transfer essay

## [0.5.0] - 2026-04-29

### Removed

- **子模块清理**：
  - 移除 `docs/context` 子模块，删除远端仓库 `quanttide/quanttide-context-of-founder`
  - 移除 `docs/vision` 子模块，删除远端仓库 `quanttide/quanttide-vision-of-founder`

### Changed

- memory 子模块：更新至 v0.3.1，新增 context/ 目录文档和 vision/default/ 愿景层文档
- fiction 子模块：更新至最新提交

### Submodules

- memory：更新至 v0.3.1 (a656a56)
- fiction：更新至最新提交
- context：已移除
- vision：已移除

## [0.4.6] - 2026-04-27

### Added
- memory v0.2.0：新增 qtcloud-think.md 整合思考云产品愿景
- visualization.md：数据可视化方案
- sync.md：协作同步机制
- internal-training.md：内部培训蓝图

### Changed
- memory 子模块：整合 vision qtcloud-think 原始思考到结构化产品愿景
- vision 子模块：移除 .quanttide 目录和废弃 skills
- fiction 子模块：更新至最新提交

### Submodules
- memory：更新至 v0.2.0 (e6395c8)
- vision：更新至 v0.0.1-4 (390d376)
- fiction：更新至最新提交 (7780d30)

---

## [0.4.5] - 2026-04-25

### Removed

- **子模块清理**：
  - 移除 `docs/roadmap` 子模块
- **远端仓库删除**：删除 `quanttide/quanttide-roadmap-of-founder` 仓库

---

## [0.4.3] - 2026-04-20

### Added

- **archive 子模块**：新增创始人档案归档仓库
  - 来源：https://github.com/quanttide/quanttide-archive-of-founder.git
  - 路径：`docs/archive`

### Changed

- **fiction 子模块**：更新至最新提交 `7cc7844`
- **memory 子模块**：更新至最新提交 `b0029e6`

---

## [0.4.2] - 2026-04-18

### Added

- **memory 子模块**：新增创始人工作记忆仓库
  - 来源：https://github.com/quanttide/quanttide-memory-of-founder.git
  - 包含 roadmap 目录结构重构
- **devops-commit Skill 增强**：自动 push 并返回 GitHub 提交链接

### Changed

- **资产契约更新**：`.quanttide/asset/contract.yaml` 添加 memory 子模块
- **devops-release Skill**：优化输出格式，添加返回链接

---

## [0.4.1] - 2026-04-14

### Added

- **devops-review Skill**：新增流程审查 Skill
  - 版本号格式验证（semver）
  - CHANGELOG 完整性验证（版本存在 + 内容不为空）
  - 工作区状态验证
  - 子模块状态验证（初始化 + 更新检查）
  - 标签冲突检测
  - 远程仓库连接验证
  - 支持发布前检查、代码审查、文档审查等多场景

### Changed

- **devops-release Skill 增强**：
  - 新增依赖声明（devops-commit、devops-submodule）
  - 新增预检查流程（版本格式、CHANGELOG、标签冲突、工作区状态）
  - 新增发布前确认对话框
  - 新增错误处理和回滚机制
  - 新增常见错误诊断表
  - 新增标准化输出（成功/失败状态）
- **AGENTS.md 更新**：新增 devops-review Skill 索引

### Removed

- **devops-validate Skill**：重命名为 devops-review，扩展审查场景

---

## [0.4.0] - 2026-04-14

### Changed

- **devops-release Skill 增强**：
  - 新增预发布检查清单（子模块版本锁定、CI 测试验证、CHANGELOG 校验、构建验证）
  - 新增预发布版本流程（vX.Y.Z-rc.1）
  - 优化 Release Notes 生成逻辑（精确提取 CHANGELOG 版本段）

### Removed

- **子模块清理**：
  - 移除 `docs/journal` 子模块
  - 移除 `docs/archive` 子模块
- **远端仓库删除**：删除 `quanttide/quanttide-journal-of-founder` 仓库
- **远端仓库重命名**：`quanttide/quanttide-archive-of-founder` → `quanttide-archive-of-asset-management`，描述更新为"量潮数字资产工作归档"

### Fixed

- **Release Notes 生成**：修复从 CHANGELOG.md 提取版本段内容为空的问题

---

## [0.3.2] - 2026-04-12

### Added

- **Skill 体系**：`.agents/skills/` 目录，封装高频 DevOps 工作流
  - `devops-commit`：规范提交
  - `devops-release`：发布 Release
  - `devops-submodule`：子模块管理（add/remove/update/fix/status）
  - 符合 [agentskills.io](https://agentskills.io/specification) 规范（YAML Frontmatter + 标准目录结构）
- **docs/context 子模块**：新增上下文文档子模块
- **docs/fiction 子模块**：新增小说创作子模块
- **docs/vision 子模块**：新增愿景文档子模块
- **.agents/README.md**：Skill 索引和使用说明

### Changed

- **CONTRIBUTING.md 重构**：从详细工作流指南 → Skill 使用和维护指南
- **AGENTS.md 更新**：新增 Skill 索引，快速索引改为引用 Skill
- **文档精简**：移除 IDENTITY.md、SOUL.md、TOOLS.md、USER.md
- **提交规范**：移除 commitizen 依赖，直接使用 Conventional Commits 格式

### Removed

- **子模块清理**：移除多个未使用的子模块
  - `apps/qtcloud-asset`
  - `apps/qtcloud-org`
  - `apps/qtcloud-think`
  - `docs/essay`
  - `docs/profile`（云端仓库已删除）

### Submodules

- **archive**：归档 journal entries before 2026-04-11
- **context**：新增，包含资产定价和 Git 仓库规范文档
- **fiction**：新增
- **journal**：归档非今日日志到 archive，合并 tutorial 到 context
- **roadmap**：新增 qtcloud-devops 路线图
- **vision**：新增，初始版本

---

## [0.3.1] - 2026-04-05

### Changed

- **目录结构重构**：
  - `meta/` 目录下的文件（IDENTITY, SOUL, TOOLS, USER）移至根目录
  - `meta/AGENTS.md` 合并到根 `AGENTS.md`
  - `src/` 重命名为 `apps/`

### Added

- **examples/generate_product_roadmap.py**：从产品日志生成产品路线图的示例脚本

### Removed

- **meta/ 目录**：所有文件已迁移或删除
- **scripts/README.md**：删除冗余文档

### Submodules

- **qtcloud-think**：新增子模块，包含记忆卡片解析和画像报告生成
- **archive**：归档 meta/memory 文件至 report/default/diary

---

## [0.3.0] - 2026-04-03

### Changed

- **meta 目录重构**：精简元目录结构
  - 移除 memory classification 引用
  - 简化 CONTRIBUTING.md 和 AGENTS.md

### Removed

- **子模块清理**：移除多个未使用的子模块
  - bylaw, data, devops, gallery, history, library, qtcloud-data, specification, tutorial, usercase

### Submodules

- **qtadmin**：更新至 cli/v0.0.1-alpha.6
- **journal**：更新至 v0.2.0
- **profile**：更新至 v0.2.5
- **archive**：更新至 v0.1.0

---

## [0.2.4] - 2026-03-28

### Added

- **meta/profile/contract.yaml**：数据契约（单一事实源）
  - semantics：记忆分类框架（九宫格、五层）
  - models：Schema 定义（子模块、Release）
  - quality：质量约束（命名、版本、文件约定）
  - data：实际数据
- **meta/spec/contract.md**：契约元规则（工程标准）
- **meta/paper/contract-hierarchy.md**：契约层次论文
  - 区分 contract.yaml（数据实例）、handbook（使用手册）、spec（元规则）

### Changed

- **meta/profile/ 重构**：
  - 删除 submodules.yaml（合并到 contract.yaml）
  - 合并 memory.md、release.md、repo.md、submodule.md 为 contract.md
  - contract.md 最终移至 meta/handbook/
- **meta/IDENTITY.md**：更新 Release 列表和子模块列表

### Submodules

- **journal**：0122b16，新增 23 个文件（日常记录和教程）
- **qtadmin**：c5883ee，新增 qtdata PRD 和 .env.example

---

## [0.2.3] - 2026-03-23

### Added

- **docs/history 子模块**：新增发展历程子模块
  - 来源：https://github.com/quanttide/quanttide-history-of-founder.git
- **meta/roadmap/vision.md**：愿景蓝图文档
- **meta/essay/work-pattern.md**：实证迭代法工作模式

### Changed

- **ROADMAP.md**：整合创始人战略目标
- **meta/profile/**：更新子模块注册表和 Release 列表

### Submodules

- **archive**：v0.2.0，添加 journal 和 report 归档
- **bylaw**：v0.0.1，初始版本
- **essay**：v0.0.2，添加实证迭代法
- **handbook**：v0.0.2，更新职能板块
- **history**：v0.0.1，初始版本
- **journal**：v0.2.0，重构目录结构
- **paper**：v0.0.1，添加实证迭代法
- **profile**：v0.2.5，归档 org 内容
- **roadmap**：v0.0.1，初始版本
- **tutorial**：v0.0.1，初始版本
- **usercase**：v0.1.1，添加 journal 归档

---

## [0.2.2] - 2026-03-21

### Added

- **docs/bylaw 子模块**：新增 bylaws 工作章程子模块
  - 来源：https://github.com/quanttide/quanttide-bylaw-of-founder.git
  - 添加 bylaw 资产结构：asset/founder/bylaw.md, profile.md, report.md
- **meta/SOUL.md 增强**：添加能力、价值、目标章节
- **meta/report/**：合并 meta/journal 到 meta/report

### Changed

- **AGENTS.md**：添加子模块操作前先 checkout main 规则
- **ROADMAP.md**：更新规划文档
- **meta 目录重构**：
  - meta/tutorial/category.md → meta/essay/category.md

### Removed

- **meta/brochure/index.md**：合并到 meta/SOUL.md
- **meta/bylaw/*.md**：移动到 docs/bylaw 子模块
- **meta/journal/2026-03-18.md, 2026-03-20.md**：合并到 meta/report
- **meta/handbook/profile.md, scripts/**：归档到对应子模块

### Submodules

- **archive**：添加 connect/ 和 profile/ 归档
- **journal**：归档每日日志文件
- **profile**：归档旧结构（74 文件）
- **roadmap**：添加 strategy/ 归档

---

## [0.2.1] - 2026-03-20

### Added

- **数字资产治理工具**：doc_check.py, submodule_sync.py
- **meta/roadmap/scripts/**：脚本摸索文档目录
- **docs/handbook/scripts-to-thera.md**：Scripts 演进到 Thera 的判断标准

### Changed

- **子模块名重命名**：`[submodule "platform"]` → `[submodule "thera"]`
- **README 更新**：添加 Thera 和 Qtadmin 到程序型记忆体系
- **AGENTS 更新**：添加脚本使用规范
- **submodule.md 改造**：改为 YAML 事实源

### Removed

- **src/thera/src/studio**：删除 Flutter 项目
- **src/thera/scripts**：删除

---

## [0.2.0] - 2026-03-20

### Changed

- **目录结构重构**：
  - `platform` → `src/thera`：技术平台改名
  - 所有子模块移动到 `docs/` 下：archive, essay, handbook, journal, paper, profile, report, specification, tutorial, usercase

### Added

- **src/qtadmin**：新增管理后台子模块
- **ROADMAP.md**：v0.2.x 版本目标规划

### Removed

- **根目录子模块**：全部移动到 docs/ 下

---

## [0.1.3] - 2026-03-19

### Changed

- **工作论文修改记忆定义**：
  - 基础教程 → 工作教程：产教融合体系的枢纽，内外部教学和培训的主要资料
  - 发展蓝图 → 工作蓝图：更聚焦于当下的具体问题
  - 发展历程 → 工作历程：更聚焦于具体视角

- **meta vs tutorial 读写规范**：明确 meta 目录给 AI 读，tutorial 子模块给人读

---

## [0.1.2] - 2026-03-18

### Added

- **meta/AGENTS.md**：AI 自我认知文档，由 AI 自维护
- **meta/TOOLS.md**：工具清单，记录项目中使用的开发工具
- **meta/journal/**：工作日志目录，记录 meta 目录的日常变更
  - `meta/journal/README.md`：日志说明和规范
  - `meta/journal/2026-03-18.md`：工作日志
- **meta/tutorial/**：使用指南目录，包含教程和分类哲学
  - `meta/tutorial/index.md`：如何使用创始人的第二大脑指南
  - `meta/tutorial/category.md`：范畴论为基础的分类和命名哲学教程
- **范畴论教程**：从本体论到范畴论的分类哲学教程

### Changed

- **meta 目录重构**：
  - 将 `meta/brochure/company.md` 移到 `meta/tutorial/index.md`
  - 更新 `meta/IDENTITY.md` 目录结构
  - 更新 `meta/README.md` 结构和说明
  - 添加 `meta/journal/` 和 `meta/tutorial/` 到记忆分层模型

- **CHANGELOG 工作流**：
  - 恢复 CHANGELOG.md
  - 标题改为大写（CHANGELOG）
  - 更新 AGENTS.md 和 CONTRIBUTING.md 中的 CHANGELOG 工作流程
  - 明确 Release notes 应该只包含对应版本的内容

- **GitHub Release 清理**：
  - 删除旧版本 Release（v0.0.2, v0.0.1）
  - 更新 0.1.0 和 0.1.1 Release notes 为标准格式
  - 只保留 0.1.0 和 0.1.1 两个 Release

- **子模块更新**：
  - archive: 提交 97cf161，新增 journal/code 和 journal/default
  - journal: 提交 c24fca7，重构 code 目录，添加 code/README.md

### Removed

- **meta/brochure/company.md**：已移到 `meta/tutorial/index.md`

### Fixed

- **CHANGELOG.md**：恢复并更新 Changelog 文件
- **GitHub Release**：修复 0.1.0 Release notes 包含整个 CHANGELOG.md 的问题

---



---

## [0.1.1] - 2026-03-17

### Added

- **meta/brochure/**：宣传册目录
  - `meta/brochure/index.md`：项目宣传册（感性化介绍项目价值和愿景）
  - `meta/brochure/company.md`：内部使用指南（量潮科技成员使用指南）
- **meta/journal/**：工作日志目录
  - `meta/journal/2026-03-17.md`：原始事件记录（按时间线）
- **meta/report/**：工作报告目录
  - 记日报/总结（按记忆分类：事件记忆、语义记忆、自我记忆）
- **meta/bylaw/report.md`：元报告章程（定义报告规范）
- **meta/bylaw/profile.md`：Profile 维护章程
- **meta/bylaw/bylaw.md`：元章程和人机分工

### Changed

- **目录结构重构**：
  - 分离原始事件记录和日报总结
  - `meta/bylaw/journal.md` → `meta/bylaw/report.md`

- **人机分工明确**：
  - bylaw：人类主导制定，AI 总结
  - handbook：AI 主导整理，人类验收
  - profile/journal：AI 自动维护

- **记忆分层模型**：
  - bylaw（最高优先级）→ handbook → profile → report（基础优先级）

### Removed

- **CHANGELOG.md**：已删除（内容已分散到各文件，现已恢复）
- **旧版本标签 v0.0.2**：已删除

---

## [0.1.0] - 2026-03-17

### Added

- **元数据重构**：将详细信息移到 `meta/profile/` 目录
  - `meta/profile/submodule.md`：子模块列表
  - `meta/profile/release.md`：Release 列表
  - `meta/profile/memory.md`：记忆建模知识
  - `meta/profile/repo.md`：仓库结构规范

- **客体介绍**：重构 `meta/IDENTITY.md` 为客体介绍文档
  - 仓库定位和核心价值
  - 核心框架概要
  - 项目状态展示

### Changed

- **子模块更新**：
  - archive: v0.1.0 (2026-03-17)
  - handbook: v0.1.0 (2026-03-17)
  - profile: v0.2.4 (2026-03-17)

- **文档重构**：
  - 将子模块信息移到 `meta/profile/submodule.md`
  - 将 Release 信息移到 `meta/profile/release.md`
  - 将记忆建模知识移到 `meta/profile/memory.md`
  - 将仓库结构知识移到 `meta/profile/repo.md`

### Fixed

- **CHANGELOG.md**：恢复并更新 Changelog 文件
