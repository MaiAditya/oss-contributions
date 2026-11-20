# docling-project/docling-core #1059: fix(doclang): wrap additional InlineGroup children of a TextItem in &lt;text&gt;

- **Status:** in review (opened 2026-11-20)
- **Pull request:** https://github.com/docling-project/docling-core/pull/1059
- **Issue:** https://github.com/docling-project/docling-core/issues/1058
- **Size:** +50 / -1 in 2 files, 1 commit(s)

## Problem

`export_to_doclang()` wrote the second and later `InlineGroup` children of a `TextItem` as bare runs, which was invalid DocLang and lost plain text on read-back.

## Fix

Wrapped additional `InlineGroup` children of a `TextItem` in `<text>`, leaving first-group nesting unchanged.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`1250c3ff`](https://github.com/docling-project/docling-core/pull/1059/commits/1250c3ff10a6ab66fc60824c0876afbbedc20fc1) | 2026-11-19 | MaiAditya | fix(doclang): wrap additional InlineGroup children of a TextItem in &lt;text&gt; |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>docling&#95;core/transforms/serializer/doclang.py</code> | +7 | -1 |
| <code>tests/test&#95;serialization&#95;doclang.py</code> | +43 | -0 |
