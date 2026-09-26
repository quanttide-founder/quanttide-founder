---
name: journal-to-archive
description: 把 assets/memory/<集>/ 中一周以上的日志归档到 assets/archive/journal/<集>/。当用户要求归档日志、备份旧日志、清理日志或说"归档一周以上的日志"时使用。
---

# Journal 归档

源仓库 `assets/memory` 与归档站 `assets/archive` 都是 git submodule，归档 = 跨 submodule 移动文件。

日志分布在两处，都要扫：

| 源 | 说明 |
|----|------|
| `assets/memory/<集>/journal/*.md` | 历史日志 |
| `assets/memory/<集>/*.md` | 集根的当天日志（手机端直写，可能长期未移入 `journal/`） |

归档站分类目录与记忆集同名（`default`、`write`），两边可直接对应。

## Steps

1. 计算截止日期：`cutoff = 今天 - 7 天`。只有文件名日期 **早于** cutoff（即 `< cutoff`）才归档；等于 cutoff 的保留。
2. 检查两个 submodule 工作区干净：`git -C assets/memory status --porcelain`、`git -C assets/archive status --porcelain`。有未提交改动先停下问用户。
3. 列出待归档文件（两个来源，文件名形如 `YYYY-MM-DD.md`）：

   ```sh
   find assets/memory -mindepth 2 -maxdepth 3 -type f -name '20??-??-??.md' \
     ! -path '*/.agents/*' | while read src; do
     base=$(basename "$src" .md)
     [ "$base" \< "$cutoff" ] && echo "$src"
   done
   ```

4. 冲突检查：每个源路径形如 `assets/memory/<集>/(journal/)?<文件>`，目标为 `assets/archive/journal/<集>/<文件>`（`<集>` 取源路径第二段），确认目标不存在。有冲突先停下问用户。
5. 移动，目标分类目录缺则 `mkdir -p` 创建：

   ```sh
   set=$(echo "$src" | cut -d/ -f3)          # default | write | ...
   file=$(basename "$src")
   dest="assets/archive/journal/$set/$file"
   mkdir -p "$(dirname "$dest")" && mv "$src" "$dest"
   ```

6. 删除源侧因此变空的 `journal/` 目录：`find assets/memory -mindepth 2 -maxdepth 3 -type d -empty -delete`（不动记忆集根目录本身）。
7. 汇报：按记忆集统计移动数量、保留的近期文件清单、删除的空目录。
8. 提交：两个 submodule 各自 `git add -A` 并 commit（源侧移除、归档侧新增），然后主仓库 `git add assets/memory assets/archive` 并 `git commit -m "chore: archive journal entries older than one week"`。

## Notes

- 只移动，不修改文件内容。
- 集根未归档的当天日志留在原处，不要求先移入 `journal/`。
- 归档站已有历史分类目录（agent、default、execute 等），与当前记忆集名不完全一致时，按记忆集名原样落位即可。
