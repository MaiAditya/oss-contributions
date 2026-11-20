# crewAIInc/crewAI #9595: fix(artifacts): never cache save&#95;artifact tool results

- **Status:** merged 2026-11-20 by @gabemilani
- **Pull request:** https://github.com/crewAIInc/crewAI/pull/9595
- **Issue:** https://github.com/crewAIInc/crewAI/issues/9594
- **Size:** +48 / -1 in 2 files, 1 commit(s)

## Problem

With `Crew(cache=True)`, a repeated `save_artifact` call with the same arguments was served from the tool cache, so a rewritten file saved no new version.

## Fix

Opted `SaveArtifactTool` out of caching with `_never_cache_function`, so each call saves a new version.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`ab40a895`](https://github.com/crewAIInc/crewAI/pull/9595/commits/ab40a895551b98a6076d3d8f5fa6134eecd6dc9e) | 2026-11-20 | MaiAditya | fix(artifacts): never cache save&#95;artifact tool results |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>lib/crewai/src/crewai/artifacts.py</code> | +5 | -1 |
| <code>lib/crewai/tests/test&#95;artifacts.py</code> | +43 | -0 |
