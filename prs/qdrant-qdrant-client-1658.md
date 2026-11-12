# qdrant/qdrant-client #1658: fix(local): reject invalid geo polygons in filters

- **Status:** in review (opened 2026-11-02)
- **Pull request:** https://github.com/qdrant/qdrant-client/pull/1658
- **Issue:** https://github.com/qdrant/qdrant-client/issues/1657
- **Size:** +93 / -1 in 3 files, 1 commit(s)

## Problem

Local mode accepted `geo_polygon` filters with unclosed or too-short rings that the server rejects, and crashed with `IndexError` on an empty exterior.

## Fix

Validated geo polygon rings in local mode with the server's rules and error messages.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`072018ef`](https://github.com/qdrant/qdrant-client/pull/1658/commits/072018ef3579d3fbeb9cd560f89c2c170923c745) | 2026-11-02 | MaiAditya | fix(local): reject invalid geo polygons in filters |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>qdrant&#95;client/local/payload&#95;filters.py</code> | +18 | -0 |
| <code>qdrant&#95;client/local/tests/test&#95;payload&#95;filters.py</code> | +33 | -1 |
| <code>tests/congruence&#95;tests/test&#95;geo&#95;polygon&#95;filter&#95;query.py</code> | +42 | -0 |
