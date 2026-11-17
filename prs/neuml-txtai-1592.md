# neuml/txtai #1592: Pin llama-cpp-python to 0.3.36 on Windows builds

- **Status:** merged 2026-11-17 by @davidmezzetti
- **Pull request:** https://github.com/neuml/txtai/pull/1592
- **Issue:** https://github.com/neuml/txtai/issues/1584
- **Size:** +1 / -0 in 1 files, 1 commit(s)

## Problem

The Windows CI build failed because the GGML ANN backend crashed in `ggml_gallocr_new` when `ggml-python` and `llama-cpp-python` 0.3.37 shared a ggml DLL.

## Fix

Pinned `llama-cpp-python==0.3.36` in the Windows dependency step of the build workflow.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`3cbb3e77`](https://github.com/neuml/txtai/pull/1592/commits/3cbb3e770ef4fd8557ad2df7a1e6ea022288ca2b) | 2026-11-17 | MaiAditya | Pin llama-cpp-python to 0.3.36 on Windows builds, closes &#35;1584 |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>.github/workflows/build.yml</code> | +1 | -0 |
