# langfuse/langfuse-python #2127: fix(serializer): record class objects as class references

- **Status:** in review (opened 2026-11-12)
- **Pull request:** https://github.com/langfuse/langfuse-python/pull/2127
- **Size:** +61 / -1 in 3 files, 1 commit(s)

## Problem

`@observe` recorded class arguments such as `schema=Invoice` as a dump of the class namespace or a double-quoted fallback string.

## Fix

Serialized class objects as `<class 'module.QualName'>` and removed the extra quotes from the fallback.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`237f0096`](https://github.com/langfuse/langfuse-python/pull/2127/commits/237f0096462da024cb436e4f430713b10e594a84) | 2026-11-12 | MaiAditya | fix(serializer): record class objects as class references |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>langfuse/&#95;utils/serializer.py</code> | +6 | -1 |
| <code>tests/unit/test&#95;observe.py</code> | +23 | -0 |
| <code>tests/unit/test&#95;serializer.py</code> | +32 | -0 |
