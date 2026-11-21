# crewAIInc/crewAI #9634: fix(llm): use api&#95;base as the endpoint for openai-compatible providers

- **Status:** in review (opened 2026-11-21)
- **Pull request:** https://github.com/crewAIInc/crewAI/pull/9634
- **Issue:** https://github.com/crewAIInc/crewAI/issues/9633
- **Size:** +44 / -1 in 2 files, 1 commit(s)

## Problem

Passing `api_base` to `LLM(...)` had no effect for OpenAI-compatible providers such as `ollama` and `hosted_vllm`, so requests went to the default localhost endpoint.

## Fix

Passed `base_url or api_base` to `_resolve_base_url`, so `api_base` now overrides env vars and defaults.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`4d1e1a62`](https://github.com/crewAIInc/crewAI/pull/9634/commits/4d1e1a6226a1f94c29c366620136564f542f864a) | 2026-11-21 | MaiAditya | fix(llm): use api&#95;base as the endpoint for openai-compatible providers |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>lib/crewai/src/crewai/llms/providers/openai&#95;compatible/completion.py</code> | +5 | -1 |
| <code>lib/crewai/tests/llms/openai&#95;compatible/test&#95;openai&#95;compatible.py</code> | +39 | -0 |
