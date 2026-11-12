# docling-project/docling #5283: fix(jats): keep the text of &lt;preformat&gt; and &lt;code&gt; blocks

- **Status:** merged 2026-11-11 by @PeterStaar-IBM
- **Pull request:** https://github.com/docling-project/docling/pull/5283
- **Issue:** https://github.com/docling-project/docling/issues/5282
- **Size:** +73 / -2 in 2 files, 1 commit(s)

## Problem

Verbatim `<preformat>` and `<code>` blocks in JATS articles were dropped, or merged into the paragraph text without their line breaks.

## Fix

Added `<preformat>` and `<code>` blocks as code items, keeping line breaks and the code language.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`1b9f2ca3`](https://github.com/docling-project/docling/pull/5283/commits/1b9f2ca36a4d3e87f376ce07b2cae525d9681816) | 2026-11-10 | MaiAditya | fix(jats): keep the text of &lt;preformat&gt; and &lt;code&gt; blocks |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>docling/backend/xml/jats&#95;backend.py</code> | +29 | -2 |
| <code>tests/test&#95;backend&#95;jats.py</code> | +44 | -0 |
