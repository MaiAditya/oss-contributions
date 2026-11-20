# crewAIInc/crewAI #9611: fix(llm): keep timeout and context&#95;window&#95;size when copying LLM

- **Status:** in review (opened 2026-11-20)
- **Pull request:** https://github.com/crewAIInc/crewAI/pull/9611
- **Issue:** https://github.com/crewAIInc/crewAI/issues/9610
- **Size:** +36 / -0 in 2 files, 1 commit(s)

## Problem

Copying an LLM that runs through LiteLLM reset `timeout` and `context_window_size` to `None`, so `Agent.copy()` and `Crew.kickoff_for_each()` lost those settings.

## Fix

Passed `timeout` and `context_window_size` to the constructor in `LLM.__copy__` and `LLM.__deepcopy__`.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`dcdc2c44`](https://github.com/crewAIInc/crewAI/pull/9611/commits/dcdc2c44a22db03241dd81ed2a497e8e27c37bae) | 2026-11-20 | MaiAditya | fix(llm): keep timeout and context&#95;window&#95;size when copying LLM |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>lib/crewai/src/crewai/llm.py</code> | +4 | -0 |
| <code>lib/crewai/tests/test&#95;llm.py</code> | +32 | -0 |
