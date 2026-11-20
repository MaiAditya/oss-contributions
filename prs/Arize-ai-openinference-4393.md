# Arize-ai/openinference #4393: fix(agno): set total, reasoning and audio token counts on every path

- **Status:** in review (opened 2026-11-20)
- **Pull request:** https://github.com/Arize-ai/openinference/pull/4393
- **Issue:** https://github.com/Arize-ai/openinference/issues/4392
- **Size:** +204 / -103 in 4 files, 1 commit(s)

## Problem

Agno `invoke`, `invoke_stream` and `ainvoke_stream` spans had no `llm.token_count.total`, and no path recorded reasoning or audio token counts.

## Fix

Merged four duplicated usage blocks into `_usage_attributes` and set total, reasoning and audio counts on every path.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`247fc491`](https://github.com/Arize-ai/openinference/pull/4393/commits/247fc4912d4443216d26d0a1bcede95cee7d4bce) | 2026-11-19 | MaiAditya | fix(agno): set total, reasoning and audio token counts on every path |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>python/instrumentation/openinference-instrumentation-agno/src/openinference/instrumentation/agno/&#95;model&#95;wrapper.py</code> | +29 | -91 |
| <code>python/instrumentation/openinference-instrumentation-agno/tests/test&#95;anthropic&#95;token&#95;counts.py</code> | +10 | -12 |
| <code>python/instrumentation/openinference-instrumentation-agno/tests/test&#95;instrumentor.py</code> | +2 | -0 |
| <code>python/instrumentation/openinference-instrumentation-agno/tests/test&#95;openai&#95;token&#95;counts.py</code> | +163 | -0 |
