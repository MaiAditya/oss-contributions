# crewAIInc/crewAI #9595: fix(artifacts): never cache save&#95;artifact tool results

- **Status:** in review (opened 2026-11-20)
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
| [`4bf11a69`](https://github.com/crewAIInc/crewAI/pull/9595/commits/4bf11a692c3647cc6b307d972b1ec5b399abafbe) | 2026-11-20 | MaiAditya | fix(artifacts): never cache save&#95;artifact tool results |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>lib/crewai/src/crewai/artifacts.py</code> | +5 | -1 |
| <code>lib/crewai/tests/test&#95;artifacts.py</code> | +43 | -0 |
