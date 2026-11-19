# Arize-ai/openinference #4367: fix(portkey): capture cache and reasoning token counts

- **Status:** merged 2026-11-19 by @caroger
- **Pull request:** https://github.com/Arize-ai/openinference/pull/4367
- **Issue:** https://github.com/Arize-ai/openinference/issues/4366
- **Size:** +171 / -11 in 4 files, 2 commit(s)

## Problem

The Portkey instrumentor dropped prompt-cache read and reasoning token counts from `usage`, so cached and reasoning-heavy calls were under-reported in traces.

## Fix

Recorded `cached_tokens` and `reasoning_tokens` as span attributes, matching the groq instrumentor.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`d023717e`](https://github.com/Arize-ai/openinference/pull/4367/commits/d023717eb526db8629ab97721c042510cf9dbc00) | 2026-11-19 | MaiAditya | fix(portkey): capture cache and reasoning token counts |
| [`a5627bab`](https://github.com/Arize-ai/openinference/pull/4367/commits/a5627bab99f02498a50a01ac581264a3ddee45ea) | 2026-11-19 | caroger | fix(portkey): fold Anthropic gateway cache counts into the prompt total |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>python/instrumentation/openinference-instrumentation-portkey/src/openinference/instrumentation/portkey/&#95;request&#95;attributes&#95;extractor.py</code> | +5 | -7 |
| <code>python/instrumentation/openinference-instrumentation-portkey/src/openinference/instrumentation/portkey/&#95;response&#95;attributes&#95;extractor.py</code> | +34 | -4 |
| <code>python/instrumentation/openinference-instrumentation-portkey/src/openinference/instrumentation/portkey/&#95;utils.py</code> | +6 | -0 |
| <code>python/instrumentation/openinference-instrumentation-portkey/tests/test&#95;instrumentor.py</code> | +126 | -0 |
