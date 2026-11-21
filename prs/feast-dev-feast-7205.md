# feast-dev/feast #7205: fix: Transform every row when writing to a singleton Python ODFV

- **Status:** in review (opened 2026-11-21)
- **Pull request:** https://github.com/feast-dev/feast/pull/7205
- **Issue:** https://github.com/feast-dev/feast/issues/7204
- **Size:** +282 / -27 in 2 files, 1 commit(s)

## Problem

Writing to a singleton Python on-demand feature view with `write_to_online_store=True` failed for UDFs returning scalars and for filtered dataframes whose index lacked `0`.

## Fix

Ran the UDF once per row by position and expanded each output into rows before writing.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`03852fde`](https://github.com/feast-dev/feast/pull/7205/commits/03852fdec62bf153b9d4695c202c8e827026ddeb) | 2026-11-21 | MaiAditya | fix: Transform every row when writing to a singleton Python ODFV |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>sdk/python/feast/feature&#95;store.py</code> | +53 | -26 |
| <code>sdk/python/tests/unit/online&#95;store/test&#95;online&#95;writes.py</code> | +229 | -1 |
