# Arize-ai/openinference #4377: fix(haystack): capture cache and reasoning token counts

- **Status:** in review (opened 2026-11-19)
- **Pull request:** https://github.com/Arize-ai/openinference/pull/4377
- **Issue:** https://github.com/Arize-ai/openinference/issues/4376
- **Size:** +102 / -0 in 4 files, 1 commit(s)

## Problem

The Haystack instrumentor dropped prompt-cache and reasoning token counts from the generator's usage, so cached and reasoning-heavy calls were under-reported in traces.

## Fix

Recorded cached, cache-write and reasoning token counts from `usage` details as span attributes, skipping missing values.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`9fe36422`](https://github.com/Arize-ai/openinference/pull/4377/commits/9fe364228f1fa5ba58ecd3ea4e7cc07c25dbd474) | 2026-11-19 | MaiAditya | fix(haystack): capture cache and reasoning token counts |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>python/instrumentation/openinference-instrumentation-haystack/src/openinference/instrumentation/haystack/&#95;wrappers.py</code> | +15 | -0 |
| <code>python/instrumentation/openinference-instrumentation-haystack/tests/openinference/haystack/cassettes/test&#95;instrumentor/test&#95;openai&#95;chat&#95;generator&#95;llm&#95;span&#95;has&#95;token&#95;count&#95;details&#91;cache-read&#93;.yaml</code> | +14 | -0 |
| <code>python/instrumentation/openinference-instrumentation-haystack/tests/openinference/haystack/cassettes/test&#95;instrumentor/test&#95;openai&#95;chat&#95;generator&#95;llm&#95;span&#95;has&#95;token&#95;count&#95;details&#91;cache-write&#93;.yaml</code> | +14 | -0 |
| <code>python/instrumentation/openinference-instrumentation-haystack/tests/openinference/haystack/test&#95;instrumentor.py</code> | +59 | -0 |
