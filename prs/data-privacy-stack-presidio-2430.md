# data-privacy-stack/presidio #2430: fix(analyzer): detect Indian vehicle registrations written with separators

- **Status:** in review (opened 2026-10-28)
- **Pull request:** https://github.com/data-privacy-stack/presidio/pull/2430
- **Issue:** https://github.com/data-privacy-stack/presidio/issues/2429
- **Size:** +129 / -2 in 2 files, 3 commit(s)

## Problem

Indian vehicle registration numbers written with spaces or hyphens, such as `MH 12 AB 1234`, were never detected.

## Fix

Added context-gated patterns that detect separated Indian vehicle registration numbers.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`31a31911`](https://github.com/data-privacy-stack/presidio/pull/2430/commits/31a31911aeda7f09c258001f173788b510d9262c) | 2026-10-28 | MaiAditya | fix(analyzer): detect Indian vehicle registrations written with separators |
| [`fc80f517`](https://github.com/data-privacy-stack/presidio/pull/2430/commits/fc80f5172a50ed80f01f3f8ec0a40a753bc5b8db) | 2026-10-28 | MaiAditya | fix(analyzer): gate separated Indian plates on context, not validation |
| [`ebe201f2`](https://github.com/data-privacy-stack/presidio/pull/2430/commits/ebe201f2ec554712ea5fc5276d1803ed3f397ebc) | 2026-11-11 | MaiAditya | fix(analyzer): lower separated Indian plate score to 0.2 |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>presidio-analyzer/presidio&#95;analyzer/predefined&#95;recognizers/country&#95;specific/india/in&#95;vehicle&#95;registration&#95;recognizer.py</code> | +33 | -1 |
| <code>presidio-analyzer/tests/test&#95;in&#95;vehicle&#95;registration&#95;recognizer.py</code> | +96 | -1 |
