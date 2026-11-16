# docling-project/docling #5405: fix(jats): keep author affiliations given in place or without an id

- **Status:** in review (opened 2026-11-16)
- **Pull request:** https://github.com/docling-project/docling/pull/5405
- **Issue:** https://github.com/docling-project/docling/issues/5404
- **Size:** +1677 / -1504 in 5 files, 1 commit(s)

## Problem

JATS author affiliations kept ids and labels in their text, and affiliations placed inside `<contrib>` or without an id in a `<contrib-group>` were not assigned to authors.

## Fix

Built affiliation text without labels and ids, and read in-contrib and id-less group `<aff>` elements for authors.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`44d577e0`](https://github.com/docling-project/docling/pull/5405/commits/44d577e0db5fed24c093b5d85707246eb8110b44) | 2026-11-16 | MaiAditya | fix(jats): keep author affiliations given in place or without an id |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>docling/backend/xml/jats&#95;backend.py</code> | +48 | -7 |
| <code>tests/data/jats/groundtruth/ptag100.xml.itxt</code> | +568 | -567 |
| <code>tests/data/jats/groundtruth/ptag100.xml.json</code> | +945 | -930 |
| <code>tests/data/jats/groundtruth/ptag100.xml.md</code> | +2 | -0 |
| <code>tests/test&#95;backend&#95;jats.py</code> | +114 | -0 |
