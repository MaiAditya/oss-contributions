# deepset-ai/haystack-core-integrations #4303: fix: Ollama - map done&#95;reason "length" to finish&#95;reason "length"

- **Status:** in review (opened 2026-11-19)
- **Pull request:** https://github.com/deepset-ai/haystack-core-integrations/pull/4303
- **Issue:** https://github.com/deepset-ai/haystack-core-integrations/issues/4302
- **Size:** +20 / -0 in 2 files, 1 commit(s)

## Problem

`OllamaChatGenerator` reported `finish_reason=None` when Ollama stopped at `num_predict` with `done_reason="length"`, so truncated replies could not be detected.

## Fix

Added `length` to `FINISH_REASON_MAPPING` so streaming and non-streaming replies report it, with a parametrized test.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`48fa2614`](https://github.com/deepset-ai/haystack-core-integrations/pull/4303/commits/48fa2614a561ccf772691cdd28e36a79debbc8ff) | 2026-11-19 | MaiAditya | fix: Ollama - map done&#95;reason "length" to finish&#95;reason "length" |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>integrations/ollama/src/haystack&#95;integrations/components/generators/ollama/chat/chat&#95;generator.py</code> | +1 | -0 |
| <code>integrations/ollama/tests/test&#95;chat&#95;generator.py</code> | +19 | -0 |
