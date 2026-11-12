# openlit/openlit #1953: fix(litellm): record model and messages passed positionally

- **Status:** in review (opened 2026-11-12)
- **Pull request:** https://github.com/openlit/openlit/pull/1953
- **Issue:** https://github.com/openlit/openlit/issues/1952
- **Size:** +237 / -16 in 4 files, 1 commit(s)

## Problem

Positional calls to LiteLLM `completion`, `acompletion`, `embedding` and `aembedding` were traced with a fallback model, unknown server address and no input.

## Fix

Mapped leading positional arguments onto `model`, `messages` and `input` when building telemetry.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`d4bc577b`](https://github.com/openlit/openlit/pull/1953/commits/d4bc577bc25f243b4440ecdb24ba10e775f3e101) | 2026-11-12 | MaiAditya | fix(litellm): record model and messages passed positionally |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>sdk/python/src/openlit/instrumentation/litellm/async&#95;litellm.py</code> | +21 | -8 |
| <code>sdk/python/src/openlit/instrumentation/litellm/litellm.py</code> | +21 | -8 |
| <code>sdk/python/src/openlit/instrumentation/litellm/utils.py</code> | +15 | -0 |
| <code>sdk/python/tests/test&#95;litellm&#95;positional&#95;args.py</code> | +180 | -0 |
