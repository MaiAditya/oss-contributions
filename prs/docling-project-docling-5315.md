# docling-project/docling #5315: feat(jats): add article keywords to the document metadata

- **Status:** in review (opened 2026-11-12)
- **Pull request:** https://github.com/docling-project/docling/pull/5315
- **Issue:** https://github.com/docling-project/docling/issues/5298
- **Size:** +274 / -1 in 4 files, 1 commit(s)

## Problem

Keywords listed in a JATS article's `<kwd-group>` were not carried into the converted document.

## Fix

Added article keywords to the document metadata as `KeywordsMetaField`.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`d60e3975`](https://github.com/docling-project/docling/pull/5315/commits/d60e3975bc5a4bdb60047189c8c9ceb74ac1850f) | 2026-11-12 | MaiAditya | feat(jats): add article keywords to the document metadata |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>docling/backend/xml/jats&#95;backend.py</code> | +68 | -0 |
| <code>tests/data/jats/groundtruth/elife-56337.nxml.json</code> | +12 | -0 |
| <code>tests/data/jats/groundtruth/elife-56337.nxml.md</code> | +3 | -1 |
| <code>tests/test&#95;backend&#95;jats.py</code> | +191 | -0 |
