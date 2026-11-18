# huggingface/huggingface_hub #5363: &#91;Repocard&#93; Detect empty YAML front matter

- **Status:** in review (opened 2026-11-15)
- **Pull request:** https://github.com/huggingface/huggingface_hub/pull/5363
- **Issue:** https://github.com/huggingface/huggingface_hub/issues/5343
- **Size:** +97 / -9 in 2 files, 2 commit(s)

## Problem

Repo cards with an empty YAML block (`---` directly followed by `---`) were not detected, so a later `---` line was parsed as YAML and `metadata_save` deleted text.

## Fix

Let the closing fence directly follow the opening one in `REGEX_YAML_BLOCK`.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`305cdbe2`](https://github.com/huggingface/huggingface_hub/pull/5363/commits/305cdbe24f01d0ba47517a5553fd9717fa0a7bf7) | 2026-11-15 | MaiAditya | &#91;Repocard&#93; Detect empty YAML front matter |
| [`c9f38271`](https://github.com/huggingface/huggingface_hub/pull/5363/commits/c9f382712c39be37c821b6be74644957971c881d) | 2026-11-18 | Wauplin | Merge branch 'main' into fix/repocard-empty-front-matter |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>src/huggingface&#95;hub/repocard.py</code> | +5 | -2 |
| <code>tests/test&#95;repocard.py</code> | +92 | -7 |
