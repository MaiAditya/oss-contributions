# PostHog/posthog-python #1277: fix(exceptions): match project root on directory boundaries for in&#95;app

- **Status:** merged 2026-11-18 by @turnipdabeets
- **Pull request:** https://github.com/PostHog/posthog-python/pull/1277
- **Size:** +28 / -5 in 3 files, 1 commit(s)

## Problem

With the default project root `/work/app`, frames in sibling directories like `/work/app-shared/lib.py` were wrongly marked `in_app=True`.

## Fix

Matched the project root on directory boundaries: the path equals the root or starts with the root plus `os.sep`.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`a707bc41`](https://github.com/PostHog/posthog-python/pull/1277/commits/a707bc419f365135642efeb31ab2af4fde7b7b32) | 2026-11-18 | MaiAditya | fix(exceptions): match project root on directory boundaries for in&#95;app |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>.sampo/changesets/in-app-project-root-boundary.md</code> | +5 | -0 |
| <code>posthog/exception&#95;utils.py</code> | +4 | -5 |
| <code>posthog/test/test&#95;exception&#95;utils.py</code> | +19 | -0 |
