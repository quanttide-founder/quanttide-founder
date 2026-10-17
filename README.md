# 量潮创始人第二大脑

基于认知科学记忆分类框架的组织知识库，以 Git 子模块方式管理应用、资产与示例仓库。

## 目录

```
quanttide-founder/
├── apps/            # 应用子模块（qtfounder）
├── assets/          # 创作资产子模块（blog / fiction / qtgame-war）
├── data/            # 数据子模块（archive / brochure / context / history / insight / intention / journal / library / profile / report / roadmap）
├── docs/            # 文档子模块（bylaw / essay / gallery / handbook / specification / tutorial）
├── examples/        # 示例子模块
├── packages/        # 包子模块
├── .agents/skills/  # Agent Skill
├── AGENTS.md        # Agent 工作指南
├── CHANGELOG.md     # 变更日志
├── CONTRIBUTING.md  # 贡献指南
└── README.md        # 项目说明
```

## 子模块

| 路径 | 仓库 | 版本 |
|------|------|------|
| `apps/qtfounder` | qtfounder | site/v0.0.1-4-g51cb1a1 |
| `assets/blog` | quanttide-blog-of-founder | main |
| `assets/fiction` | quanttide-fiction-of-founder | v1.0.0 |
| `assets/qtgame-war` | qtgame-war | main |
| `data/archive` | quanttide-archive-of-founder | v1.2.0 |
| `data/brochure` | quanttide-brochure-of-founder | main |
| `data/context` | quanttide-context-of-founder | v1.4.1 |
| `data/history` | quanttide-history-of-founder | main |
| `data/insight` | quanttide-insight-of-founder | main |
| `data/intention` | quanttide-intention-of-founder | main |
| `data/journal` | quanttide-journal-of-founder | v1.0.0 |
| `data/library` | quanttide-library-of-founder | main |
| `data/profile` | quanttide-profile-of-founder | main |
| `data/report` | quanttide-report-of-founder | main |
| `data/roadmap` | quanttide-roadmap-of-founder | main |
| `docs/bylaw` | quanttide-bylaw-of-founder | v0.1.0 |
| `docs/essay` | quanttide-essay-of-founder | main |
| `docs/gallery` | quanttide-gallery-of-founder | main |
| `docs/handbook` | quanttide-handbook-of-founder | main |
| `docs/specification` | quanttide-specification-of-founder | main |
| `docs/tutorial` | quanttide-tutorial-of-founder | main |
| `examples/quanttide-founder-lab` | quanttide-founder-lab | main |
| `packages/quanttide-founder-toolkit` | quanttide-founder-toolkit | main |

版本契约：结构类变更（目录迁移、重命名、归档规范变化）为破坏性变更，需升 major 版本并在 CHANGELOG 写明迁移映射。

## 常用命令

### 子模块初始化

```bash
git submodule update --init --recursive
```

### 更新子模块到远程最新

```bash
git submodule update --init --remote
```
