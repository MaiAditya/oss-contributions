# lancedb/lancedb #5003: fix(python): keep the guessed vector dimension across batches for on&#95;bad&#95;vectors

- **Status:** in review (opened 2026-11-12)
- **Pull request:** https://github.com/lancedb/lancedb/pull/5003
- **Issue:** https://github.com/lancedb/lancedb/issues/5002
- **Size:** +64 / -1 in 2 files, 1 commit(s)

## Problem

Creating a table from batches without a schema re-guessed the vector dimension per batch, so a later batch with another length failed on write despite `on_bad_vectors`.

## Fix

Kept the dimension guessed from the first batch with vectors for later batches.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`32fbda11`](https://github.com/lancedb/lancedb/pull/5003/commits/32fbda11b77a306baf4eb6b0c72493db57501a37) | 2026-11-12 | MaiAditya | fix(python): keep the guessed vector dimension across batches for on&#95;bad&#95;vectors |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>python/python/lancedb/table.py</code> | +1 | -1 |
| <code>python/python/tests/test&#95;table.py</code> | +63 | -0 |
