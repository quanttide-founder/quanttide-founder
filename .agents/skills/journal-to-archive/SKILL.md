---
name: journal-to-archive
description: 把 assets/memory/journal/ 中一周以上的日志归档到 assets/archive/journal/。当用户要求归档日志、备份旧日志、清理 journal 或说"归档一周以上的日志"时使用。
---

# Journal 归档

源仓库 `assets/memory` 与归档站 `assets/archive` 都是 git submodule，归档 = 跨 submodule 移动文件。

## Steps

1. 计算截止日期：`cutoff = 今天 - 7 天`。只有文件名日期 **早于** cutoff（即 `< cutoff`）才归档；等于 cutoff 的保留。
2. 检查两个 submodule 工作区干净：`git -C assets/memory status --porcelain`、`git -C assets/archive status --porcelain`。有未提交改动先停下问用户。
3. 列出待归档文件（源目录含根目录及各分类子目录，文件名形如 `YYYY-MM-DD.md`）：

   ```sh
   find assets/memory/journal -type f -name '20??-??-??.md' | while read src; do
     base=$(basename "$src" .md)
     [ "$base" \< "$cutoff" ] && echo "$src"
   done
   ```

4. 冲突检查：把每个源路径的 `assets/memory/journal` 前缀替换成 `assets/archive/journal`，确认目标不存在。有冲突先停下问用户。
5. 移动，保持分类子目录结构（归档站缺该分类目录时 `mkdir -p` 创建）：

   ```sh
   dest="assets/archive/journal/${src#assets/memory/journal/}"
   mkdir -p "$(dirname "$dest")" && mv "$src" "$dest"
   ```

6. 删除源侧因此变空的分类目录：`find assets/memory/journal -type d -empty -delete`
7. 汇报：按分类统计移动数量、保留的近期文件清单、删除的空目录。
8. 提交：两个 submodule 各自 `git add -A` 并 commit（源侧移除、归档侧新增），然后主仓库 `git add assets/memory assets/archive` 并 `git commit -m "chore: archive journal entries older than one week"`。

## Notes

- 只移动，不修改文件内容。
- 根目录下未归档的文件留在原处，不要求分类。
- 归档站已有历史分类目录（agent、default、execute 等），源侧当前分类子目录（如 `default/`）可能与之不完全一致，按源侧分类原样落位即可。
