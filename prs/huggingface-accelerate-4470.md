# huggingface/accelerate #4470: Fix reduce(..., "mean") on integer tensors in distributed runs

- **Status:** in review (opened 2026-10-29)
- **Pull request:** https://github.com/huggingface/accelerate/pull/4470
- **Issue:** https://github.com/huggingface/accelerate/issues/4469
- **Size:** +19 / -3 in 3 files, 2 commit(s)

## Problem

`reduce(tensor, "mean")` crashed on integer tensors in multi-process runs with `result type Float can't be cast to ... Long`.

## Fix

Divided out of place in mean reduction so integer tensors are promoted to float.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`e2a7b4a5`](https://github.com/huggingface/accelerate/pull/4470/commits/e2a7b4a5cf2dae5b8731ea259858dd3b2e110796) | 2026-10-29 | MaiAditya | Fix `reduce(..., "mean")` on integer tensors in distributed runs |
| [`d14f0c89`](https://github.com/huggingface/accelerate/pull/4470/commits/d14f0c899870b591a03f7e3b92ad1bf197232f66) | 2026-10-29 | MaiAditya | Document float result of mean reduce on integer tensors |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>src/accelerate/accelerator.py</code> | +2 | -1 |
| <code>src/accelerate/test&#95;utils/scripts/test&#95;ops.py</code> | +13 | -0 |
| <code>src/accelerate/utils/operations.py</code> | +4 | -2 |
