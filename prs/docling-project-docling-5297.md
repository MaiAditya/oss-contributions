# docling-project/docling #5297: fix(jats): keep attributions, speakers and statement labels

- **Status:** in review (opened 2026-11-11)
- **Pull request:** https://github.com/docling-project/docling/pull/5297
- **Issue:** https://github.com/docling-project/docling/issues/5296
- **Size:** +38 / -1 in 2 files, 1 commit(s)

## Problem

Quote attributions, speech speakers and statement labels and titles were dropped when converting JATS articles.

## Fix

Kept `<attrib>`, `<speaker>` and statement labels and titles as text items.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`ff83f897`](https://github.com/docling-project/docling/pull/5297/commits/ff83f8973d896467cbf11b1a7a04435b09494eb7) | 2026-11-11 | MaiAditya | fix(jats): keep attributions, speakers and statement labels |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>docling/backend/xml/jats&#95;backend.py</code> | +7 | -1 |
| <code>tests/test&#95;backend&#95;jats.py</code> | +31 | -0 |
