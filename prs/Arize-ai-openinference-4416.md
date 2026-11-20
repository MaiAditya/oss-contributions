# Arize-ai/openinference #4416: fix(beeai): record prompt cache read and write token counts

- **Status:** in review (opened 2026-11-20)
- **Pull request:** https://github.com/Arize-ai/openinference/pull/4416
- **Issue:** https://github.com/Arize-ai/openinference/issues/4415
- **Size:** +74 / -0 in 4 files, 1 commit(s)

## Problem

BeeAI LLM spans recorded cache read and write token counts only as `metadata.usage.*` strings, so Phoenix showed no cache usage for them.

## Fix

Mapped cached prompt and cache creation tokens to `llm.token_count.prompt_details.cache_read` and `cache_write` when non-zero.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`70ed13a4`](https://github.com/Arize-ai/openinference/pull/4416/commits/70ed13a40ebd9e0fd3f37a5ae314ed41c06bb3b2) | 2026-11-20 | MaiAditya | fix(beeai): record prompt cache read and write token counts |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>python/instrumentation/openinference-instrumentation-beeai/src/openinference/instrumentation/beeai/processors/chat.py</code> | +12 | -0 |
| <code>python/instrumentation/openinference-instrumentation-beeai/tests/openinference/instrumentation/beeai/cassettes/test&#95;instrumentor/test&#95;llm&#95;records&#95;prompt&#95;cache&#95;token&#95;counts.yaml</code> | +28 | -0 |
| <code>python/instrumentation/openinference-instrumentation-beeai/tests/openinference/instrumentation/beeai/conftest.py</code> | +5 | -0 |
| <code>python/instrumentation/openinference-instrumentation-beeai/tests/openinference/instrumentation/beeai/test&#95;instrumentor.py</code> | +29 | -0 |
