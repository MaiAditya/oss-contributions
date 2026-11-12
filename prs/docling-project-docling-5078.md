# docling-project/docling #5078: fix(jats): keep tables published as an image

- **Status:** merged 2026-11-06 by @ceberam
- **Pull request:** https://github.com/docling-project/docling/pull/5078
- **Issue:** https://github.com/docling-project/docling/issues/5077
- **Size:** +105 / -4 in 2 files, 6 commit(s)

## Problem

Tables published as an image were dropped from JATS articles together with their label and caption, so the converted document lost them.

## Fix

Kept image-only tables as pictures with their labels and captions.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`9353fa2e`](https://github.com/docling-project/docling/pull/5078/commits/9353fa2e7c9dbc8f9f55127468a1ec895b072f44) | 2026-10-28 | MaiAditya | fix(jats): keep tables published as an image |
| [`ed0ad210`](https://github.com/docling-project/docling/pull/5078/commits/ed0ad21010124c1cfe7a631cf88a0c1f07374b79) | 2026-10-28 | MaiAditya | test(jats): cover alternative and mixed renditions of image tables |
| [`9fa8c634`](https://github.com/docling-project/docling/pull/5078/commits/9fa8c63448809734f83b607b2e5e9d15c2568954) | 2026-10-29 | MaiAditya | test(jats): cover image tables without a caption and table-wraps without content |
| [`bde10531`](https://github.com/docling-project/docling/pull/5078/commits/bde10531b4da7e39432e7a1d0c71b9d040b32190) | 2026-11-06 | MaiAditya | fix(jats): keep tables published as an inline graphic |
| [`ab2be4d4`](https://github.com/docling-project/docling/pull/5078/commits/ab2be4d4206ebcb7992ea3c01eb4c18d7c730bb6) | 2026-11-06 | ceberam | fix(jats): drop inline-graphic support for image tables |
| [`059c63f1`](https://github.com/docling-project/docling/pull/5078/commits/059c63f1e7badae627fc691c601bb25a271a8859) | 2026-11-06 | ceberam | test(jats): move image table tests to the main JATS test file |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>docling/backend/xml/jats&#95;backend.py</code> | +8 | -4 |
| <code>tests/test&#95;backend&#95;jats.py</code> | +97 | -0 |
