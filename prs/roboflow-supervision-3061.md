# roboflow/supervision #3061: fix(detection): load class-agnostic results in `from_transformers`

- **Status:** merged 2026-11-25 by @Borda
- **Pull request:** https://github.com/roboflow/supervision/pull/3061
- **Issue:** https://github.com/roboflow/supervision/issues/3060
- **Size:** +71 / -8 in 4 files, 2 commit(s)

## Problem

`sv.Detections.from_transformers` raised `KeyError: 'labels'` on SAM 3 results and `AttributeError` on OWL-ViT/OWLv2 image-guided results, which have no class labels.

## Fix

Made `labels` optional, giving `class_id=None`, and kept `(N, H, W)` masks unsqueezed.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`ce542ef6`](https://github.com/roboflow/supervision/pull/3061/commits/ce542ef6f611136379bd9e165a22c3800106a3a0) | 2026-11-24 | MaiAditya | fix(detection): load class-agnostic results in `from_transformers` |
| [`82c792b9`](https://github.com/roboflow/supervision/pull/3061/commits/82c792b9ceb3e6c593427065d327e30ea3f49c5d) | 2026-11-24 | MaiAditya | docs: link &#35;3061 in the changelog entry |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>docs/changelog.md</code> | +2 | -0 |
| <code>src/supervision/detection/core.py</code> | +5 | -0 |
| <code>src/supervision/detection/tools/transformers.py</code> | +21 | -8 |
| <code>tests/detection/tools/test&#95;transformers.py</code> | +43 | -0 |
