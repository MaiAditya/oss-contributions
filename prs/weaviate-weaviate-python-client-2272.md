# weaviate/weaviate-python-client #2272: fix(generative): return xAI and DeepSeek metadata in generative results

- **Status:** in review (opened 2026-11-20)
- **Pull request:** https://github.com/weaviate/weaviate-python-client/pull/2272
- **Issue:** https://github.com/weaviate/weaviate-python-client/issues/2271
- **Size:** +11 / -1 in 3 files, 1 commit(s)

## Problem

Generative queries with the xAI or DeepSeek provider and `return_metadata=True` always returned `generative.metadata` as `None`, though the server sent usage.

## Fix

Read the `xai` and `deepseek` metadata fields and added their types to the `GenerativeMetadata` union.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`a9331b44`](https://github.com/weaviate/weaviate-python-client/pull/2272/commits/a9331b44542a6d001830766f6575c64d29c0e9ff) | 2026-11-20 | MaiAditya | fix(generative): return xAI and DeepSeek metadata in generative results |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>test/collection/test&#95;generative&#95;metadata.py</code> | +5 | -1 |
| <code>weaviate/collections/classes/internal.py</code> | +2 | -0 |
| <code>weaviate/collections/queries/base&#95;executor.py</code> | +4 | -0 |
