# roboflow/supervision #2965: fix(metrics): report -1 for mean average recall without targets

- **Status:** merged 2026-11-24 by @Borda
- **Pull request:** https://github.com/roboflow/supervision/pull/2965
- **Issue:** https://github.com/roboflow/supervision/issues/2964
- **Size:** +121 / -20 in 6 files, 5 commit(s)

## Problem

`MeanAverageRecall` returned `0.0` with no targets or for an empty size bucket, where `MeanAveragePrecision` and pycocotools return `-1`.

## Fix

Returned the `-1` sentinel for the no-target cases and added a test against pycocotools.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`414db92c`](https://github.com/roboflow/supervision/pull/2965/commits/414db92c1ad5706aa64be6fbb52660dd4a79067e) | 2026-11-12 | MaiAditya | fix(metrics): report -1 for mean average recall without targets |
| [`131ee9fc`](https://github.com/roboflow/supervision/pull/2965/commits/131ee9fc2f740ecda382aaf709e3aa8cd0f212e4) | 2026-11-12 | MaiAditya | docs: link changelog entry to &#35;2965 |
| [`a357de23`](https://github.com/roboflow/supervision/pull/2965/commits/a357de2319eff9353c2e8379194d76b8cd6d342a) | 2026-11-12 | pre-commit-ci&#91;bot&#93; | fix(pre&#95;commit): 🎨 auto format pre-commit hooks |
| [`a25bfa2c`](https://github.com/roboflow/supervision/pull/2965/commits/a25bfa2c3c16941485ff4bc15c2ed5803c5185f3) | 2026-11-23 | Borda | chore: merge develop into mean average recall fix |
| [`947b4a0c`](https://github.com/roboflow/supervision/pull/2965/commits/947b4a0c4f32e9d4e42c4d76f4ddd4a0c253dc96) | 2026-11-23 | Borda | fix(metrics): label undefined recall in plots |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>docs/changelog.md</code> | +2 | -0 |
| <code>src/supervision/metrics/mean&#95;average&#95;recall.py</code> | +7 | -6 |
| <code>src/supervision/metrics/utils/aggregate.py</code> | +9 | -2 |
| <code>tests/metrics/test&#95;mean&#95;average&#95;recall.py</code> | +44 | -6 |
| <code>tests/metrics/test&#95;size&#95;bucket&#95;regressions.py</code> | +6 | -6 |
| <code>tests/metrics/utils/test&#95;aggregate.py</code> | +53 | -0 |
