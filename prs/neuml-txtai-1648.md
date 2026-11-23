# neuml/txtai #1648: Fix OpenAI chat completions with generation parameters for embeddings and workflows

- **Status:** merged 2026-11-22 by @davidmezzetti
- **Pull request:** https://github.com/neuml/txtai/pull/1648
- **Issue:** https://github.com/neuml/txtai/issues/1647
- **Size:** +30 / -5 in 2 files, 1 commit(s)

## Problem

The OpenAI-compatible chat endpoint returned a 500 error for `embeddings` or workflow models when a request set `stream` or `max_completion_tokens`.

## Fix

Stopped forwarding `stream` and `maxlength` to `search()` and `workflow()`, and sent streamed string results as one chunk.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`80b988f5`](https://github.com/neuml/txtai/pull/1648/commits/80b988f5010ef14c8079d4413ae59849483722e7) | 2026-11-22 | MaiAditya | Fix OpenAI chat completions with generation parameters for embeddings and workflows, closes &#35;1647 |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>src/python/txtai/api/routers/openai.py</code> | +6 | -5 |
| <code>test/python/testapi/testopenai.py</code> | +24 | -0 |
