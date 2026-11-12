# lancedb/lancedb #4989: fix(python): support nested constrained types in pydantic schemas

- **Status:** in review (opened 2026-11-12)
- **Pull request:** https://github.com/lancedb/lancedb/pull/4989
- **Issue:** https://github.com/lancedb/lancedb/issues/4988
- **Size:** +69 / -1 in 2 files, 1 commit(s)

## Problem

Pydantic models with constrained types nested in `Optional` or `List`, such as `Optional[PositiveInt]`, failed with `unsupported type typing.Annotated`.

## Fix

Converted `Annotated` types nested in `Optional` or `List` to their underlying Arrow type.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`928045a2`](https://github.com/lancedb/lancedb/pull/4989/commits/928045a2fec6e287edb9b1582ca7b78dca345b15) | 2026-11-12 | MaiAditya | fix(python): support nested constrained types in pydantic schemas |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>python/python/lancedb/pydantic.py</code> | +9 | -0 |
| <code>python/python/tests/test&#95;pydantic.py</code> | +60 | -1 |
