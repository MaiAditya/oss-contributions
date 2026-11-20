# Arize-ai/openinference #4405: fix(cohere): record cached prompt tokens from chat usage

- **Status:** in review (opened 2026-11-20)
- **Pull request:** https://github.com/Arize-ai/openinference/pull/4405
- **Issue:** https://github.com/Arize-ai/openinference/issues/4404
- **Size:** +47 / -1 in 2 files, 1 commit(s)

## Problem

The Cohere instrumentor ignored `usage.cached_tokens` on chat and chat stream responses, so prompt cache hits were not visible on spans.

## Fix

Mapped `usage.cached_tokens` to `llm.token_count.prompt_details.cache_read` for chat, chat stream and embed spans.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`d8c77c78`](https://github.com/Arize-ai/openinference/pull/4405/commits/d8c77c78e28e8276efb43790511f6cbd51299afb) | 2026-11-20 | MaiAditya | fix(cohere): record cached prompt tokens from chat usage |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>python/instrumentation/openinference-instrumentation-cohere/src/openinference/instrumentation/cohere/&#95;response&#95;attributes&#95;extractor.py</code> | +3 | -0 |
| <code>python/instrumentation/openinference-instrumentation-cohere/tests/openinference/instrumentation/cohere/test&#95;instrumentor.py</code> | +44 | -1 |
