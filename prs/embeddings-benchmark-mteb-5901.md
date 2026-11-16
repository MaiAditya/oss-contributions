# embeddings-benchmark/mteb #5901: fix: keep results without a model revision in BenchmarkResults tables

- **Status:** in review (opened 2026-11-16)
- **Pull request:** https://github.com/embeddings-benchmark/mteb/pull/5901
- **Issue:** https://github.com/embeddings-benchmark/mteb/issues/5900
- **Size:** +78 / -3 in 3 files, 2 commit(s)

## Problem

Results with a `None` model revision disappeared from `BenchmarkResults.join_revisions`, `to_dataframe` and `get_aggregated_scores`.

## Fix

Grouped with `dropna=False` and filled a missing revision with `no_revision_available` before pivoting.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`b110279b`](https://github.com/embeddings-benchmark/mteb/pull/5901/commits/b110279b40cb735cad5a013afc90e0ff5f27a050) | 2026-11-16 | MaiAditya | fix: keep results without a model revision in BenchmarkResults tables |
| [`5073324c`](https://github.com/embeddings-benchmark/mteb/pull/5901/commits/5073324c415380cecc2a9987c455017a61d7ed40) | 2026-11-16 | MaiAditya | fix: narrow the restored revision to str for mypy |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>mteb/results/benchmark&#95;results.py</code> | +4 | -2 |
| <code>mteb/results/model&#95;result.py</code> | +7 | -0 |
| <code>tests/test&#95;results/test&#95;benchmark&#95;results.py</code> | +67 | -1 |
