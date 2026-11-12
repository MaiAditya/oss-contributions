# docling-project/docling #5301: fix(jats): cover more JATS elements (&#35;1067)

- **Status:** in review (opened 2026-11-11)
- **Pull request:** https://github.com/docling-project/docling/pull/5301
- **Issue:** https://github.com/docling-project/docling/issues/5298
- **Size:** +1788 / -394 in 5 files, 2 commit(s)

## Problem

Many JATS elements lost content on conversion, including list formatting, definition-list terms, MathML formulas, box titles and supplementary-material labels.

## Fix

Extended the JATS backend to keep formatting, terms, formulas, headings and labels for these elements.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`cfa04be1`](https://github.com/docling-project/docling/pull/5301/commits/cfa04be176eee2ff989ee801fd8dfb3ccd747f2a) | 2026-11-11 | MaiAditya | fix(jats): cover more JATS elements (&#35;1067) |
| [`be8d951e`](https://github.com/docling-project/docling/pull/5301/commits/be8d951e5e9fc1c77c760afa42d0b3eef4753c6e) | 2026-11-11 | MaiAditya | fix(jats): keep the textual form of a display formula |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>docling/backend/xml/jats&#95;backend.py</code> | +438 | -55 |
| <code>tests/data/jats/groundtruth/elife-56337.nxml.itxt</code> | +119 | -113 |
| <code>tests/data/jats/groundtruth/elife-56337.nxml.json</code> | +317 | -226 |
| <code>tests/data/jats/groundtruth/elife-56337.nxml.md</code> | +12 | -0 |
| <code>tests/test&#95;backend&#95;jats.py</code> | +902 | -0 |
