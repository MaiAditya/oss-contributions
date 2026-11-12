# huggingface/peft #4157: FIX BOFT and OFT Conv2d layers

- **Status:** in review (opened 2026-11-12)
- **Pull request:** https://github.com/huggingface/peft/pull/4157
- **Issue:** https://github.com/huggingface/peft/issues/4152
- **Size:** +85 / -177 in 4 files, 1 commit(s)

## Problem

BOFT Conv2d layers failed with a shape error on non-square kernels, and OFT Conv2d's unmerged output differed from its merged output, even changing the base model at initialization.

## Fix

Fixed BOFT kernel shapes and made OFT Conv2d rotate the weight in forward, matching its merged output.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`0e1e6037`](https://github.com/huggingface/peft/pull/4157/commits/0e1e60375a1c59e3ae7b1261b0657d73e2bbb4ed) | 2026-11-11 | MaiAditya | FIX BOFT and OFT Conv2d layers |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>src/peft/tuners/boft/layer.py</code> | +11 | -11 |
| <code>src/peft/tuners/oft/layer.py</code> | +49 | -106 |
| <code>tests/test&#95;initialization.py</code> | +12 | -0 |
| <code>tests/test&#95;vision&#95;models.py</code> | +13 | -60 |
