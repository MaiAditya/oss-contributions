# reflex-dev/reflex #7891: fix: resolve relative alembic script&#95;location before matching frames

- **Status:** in review (opened 2026-11-13)
- **Pull request:** https://github.com/reflex-dev/reflex/pull/7891
- **Issue:** https://github.com/reflex-dev/reflex/issues/7856
- **Size:** +90 / -20 in 3 files, 1 commit(s)

## Problem

With a relative `script_location` in `alembic.ini`, a failing hand-edited `env.py` was logged with a full traceback instead of the one-line `reflex db init` hint.

## Fix

Resolved the script directory and traceback file paths in `_raised_in_env_py()` before comparing them.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`a29c76dd`](https://github.com/reflex-dev/reflex/pull/7891/commits/a29c76dda29fd9e7cf8810d14b91b25954dfef99) | 2026-11-13 | MaiAditya | fix: resolve relative alembic script&#95;location before matching frames |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>news/+alembic-relative-script-location.bugfix.md</code> | +1 | -0 |
| <code>reflex/utils/migrations.py</code> | +4 | -2 |
| <code>tests/units/utils/test&#95;migrations.py</code> | +85 | -18 |
