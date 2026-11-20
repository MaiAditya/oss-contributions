# vibrantlabsai/ragas #3135: fix(testset): generate exactly testset&#95;size samples

- **Status:** in review (opened 2026-11-20)
- **Pull request:** https://github.com/vibrantlabsai/ragas/pull/3135
- **Issue:** https://github.com/vibrantlabsai/ragas/issues/3134
- **Size:** +108 / -2 in 3 files, 1 commit(s)

## Problem

`TestsetGenerator.generate(testset_size=N)` returned more than N samples (12 for 10, 54 for 50), costing extra LLM calls.

## Fix

Split sizes by largest remainder and capped `generate_scenarios` at `n`, so exactly `testset_size` samples come back.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`36959a0c`](https://github.com/vibrantlabsai/ragas/pull/3135/commits/36959a0cf23a10ca76bfca1bcd798bbcc8dde62e) | 2026-11-20 | MaiAditya | fix(testset): generate exactly testset&#95;size samples |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>src/ragas/testset/synthesizers/base.py</code> | +4 | -0 |
| <code>src/ragas/testset/synthesizers/utils.py</code> | +11 | -2 |
| <code>tests/unit/test&#95;testset&#95;size.py</code> | +93 | -0 |
