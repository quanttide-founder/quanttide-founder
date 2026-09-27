---
name: archive-to-domain
description: 把 assets/archive（quanttide-archive-of-founder）中属于某领域的资源迁移到对应领域归档仓库（如 quanttide-write 的 data/archive），并完成跨仓库逐级提交。当用户要求归档站资源移交领域 archive、迁移 write 域资源时使用。
---

# 归档站到领域归档迁移

`assets/archive` 按域分类的资源可整体移交对应领域的归档仓库。领域归档是领域仓库的子模块，如 `quanttide-write/data/archive` → `quanttide-archive-of-narrative-engineering`。迁移 = 跨仓库移动文件 + 六步提交链。

## 已知映射

| 源（本归档站） | 目标 | 说明 |
|------|------|------|
| `journal/write/**` | `quanttide-write/data/archive/journal/**` | write 层与领域归档重合，平铺落位 |
| `journal/write/fiction/**` | 本仓库 `fiction/journal/**` | fiction 主题日志回迁（例外） |
| `<资产>/write/**` | `quanttide-write/data/archive/<资产>/**` | 去除 write 层落位 |

目标根：`/home/iguo/repos/quanttide/domains/<领域>/data/archive/`。fiction 域资源（如 `context/fiction/`）不随 write 迁移，归属由用户逐次确认。

## 迁移前检查

1. 双侧工作区干净：`git -C <路径> status --porcelain`。目标仓库若有未推送本地提交，确认是用户自己的提交后再一并推送，不要 rebase 掉。
2. 全量盘点源侧：`find assets/archive -type d -name write -not -path '*/.git/*'`。
3. 落位冲突：列出目标将存在的资产目录，与源文件比对，同名即停下问用户。
4. 读者扫描：`grep -rn '<资产>/write' --include='*.md'`，只改活跃文档；CHANGELOG 历史条目不改。

## 提交链（按序执行）

1. **移动**：`mv <源>/* <目标>/<资产>/`；目标资产目录不存在时直接 `mv <源> <目标>/<资产>`（整目录改名，内容不动）。
2. **领域 archive**：`git -C <目标> add -A && git -C <目标> commit -m "feat: 迁入..." && git -C <目标> push origin main`。
3. **领域仓库指针**：`git -C /home/iguo/repos/quanttide/domains/<领域> add data/archive`，提交 `chore: update data/archive submodule`，push。
4. **quanttide monorepo 指针**：`git -C /home/iguo/repos/quanttide add domains/<领域>`，提交 `chore: update domains/<领域> submodule`，push。该仓库常有其他子模块脏状态，只 add 本路径，不带别人的变更。
5. **本归档站**：删除 + 活跃读者文档 + CHANGELOG 映射条目，提交 `refactor: 迁出 <资产>/write 至 <领域>归档`，push。
6. **主仓库**：受影响 skill 文档单独提交，再 `chore: update assets/archive submodule` 指针提交，push。

## CHANGELOG 规范

- 纯路径迁移升 minor，条目附新旧路径映射表，跨仓库路径写全到仓库名或领域根。
- 同批次迁移合并进当次未发布条目；已发布条目不改写。

## Notes

- 只移动文件，不改内容；目标仓库的文件视图与提交历史独立，迁移在两侧各留一条提交，历史可各自追溯。
- 提交遵循 Conventional Commits：迁入侧用 `feat`，迁出侧用 `refactor`，指针用 `chore`。
- 完成后汇报：各级提交链接、迁移文件数、CHANGELOG 是否待发版。
