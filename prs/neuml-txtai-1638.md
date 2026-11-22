# neuml/txtai #1638: Pass stripthink=False through the LLM and RAG API endpoints

- **Status:** merged 2026-11-22 by @davidmezzetti
- **Pull request:** https://github.com/neuml/txtai/pull/1638
- **Issue:** https://github.com/neuml/txtai/issues/1637
- **Size:** +27 / -4 in 4 files, 1 commit(s)

## Problem

The `/llm`, `/batchllm`, `/rag` and `/batchrag` endpoints dropped an explicit `stripthink=false`, so thinking text was always stripped from non-streaming responses.

## Fix

Forwarded any parameter that is not `None` in the LLM and RAG routers, so `False` reaches the pipeline.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`44abb631`](https://github.com/neuml/txtai/pull/1638/commits/44abb6313e51c6fd3e670624619928bb1c0d22bd) | 2026-11-22 | MaiAditya | Pass stripthink=False through the LLM and RAG API endpoints, closes &#35;1637 |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>src/python/txtai/api/routers/llm.py</code> | +2 | -2 |
| <code>src/python/txtai/api/routers/rag.py</code> | +2 | -2 |
| <code>test/python/testapi/testapiembeddings.py</code> | +9 | -0 |
| <code>test/python/testapi/testapipipeline.py</code> | +14 | -0 |
