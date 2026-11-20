# Unstructured-IO/unstructured #4816: fix(chunking): keep a table's caption when the table is split into TableChunks

- **Status:** in review (opened 2026-11-20)
- **Pull request:** https://github.com/Unstructured-IO/unstructured/pull/4816
- **Issue:** https://github.com/Unstructured-IO/unstructured/issues/4815
- **Size:** +105 / -9 in 5 files, 1 commit(s)

## Problem

When chunking split an oversized table, its `<caption>` was missing from every `TableChunk`, though `partition_html()` kept it in the `Table` element.

## Fix

Added the caption to the first chunk's text and HTML, reduced its row budget, and restored it when reconstructing tables.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`712d87cf`](https://github.com/Unstructured-IO/unstructured/pull/4816/commits/712d87cf3b528a1b7eb91af6f369a24c4f4c0872) | 2026-11-20 | MaiAditya | fix(chunking): keep a table's caption when the table is split into TableChunks |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>test&#95;unstructured/chunking/test&#95;base.py</code> | +35 | -0 |
| <code>test&#95;unstructured/common/test&#95;html&#95;table.py</code> | +19 | -0 |
| <code>unstructured/chunking/base.py</code> | +36 | -9 |
| <code>unstructured/chunking/dispatch.py</code> | +3 | -0 |
| <code>unstructured/common/html&#95;table.py</code> | +12 | -0 |
