# huggingface/datasets #9048: Fix `batch(by_column=..., drop_last_batch=True)` dropping complete groups

- **Status:** in review (opened 2026-11-15)
- **Pull request:** https://github.com/huggingface/datasets/pull/9048
- **Issue:** https://github.com/huggingface/datasets/issues/9028
- **Size:** +28 / -1 in 3 files, 1 commit(s)

## Problem

`Dataset.batch` and `IterableDataset.batch` with `by_column` and `drop_last_batch=True` dropped complete groups, or every row of a single-group dataset.

## Fix

Stopped forwarding `drop_last_batch` in the `by_column` branch of both methods and noted it in the docstrings.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`6c121053`](https://github.com/huggingface/datasets/pull/9048/commits/6c1210536ecee8854cc1b1ce8eb85a41c6569a0d) | 2026-11-15 | MaiAditya | Fix batch(by&#95;column) with drop&#95;last&#95;batch dropping complete groups |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>src/datasets/arrow&#95;dataset.py</code> | +3 | -0 |
| <code>src/datasets/iterable&#95;dataset.py</code> | +1 | -1 |
| <code>tests/test&#95;arrow&#95;dataset.py</code> | +24 | -0 |
