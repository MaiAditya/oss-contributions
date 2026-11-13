# reflex-dev/reflex #7881: fix: handle symlinks when zipping the app for export

- **Status:** in review (opened 2026-11-13)
- **Pull request:** https://github.com/reflex-dev/reflex/pull/7881
- **Issue:** https://github.com/reflex-dev/reflex/issues/7851
- **Size:** +183 / -9 in 3 files, 2 commit(s)

## Problem

Exporting an app containing a directory symlink outside the app or a dangling symlink crashed with an error and left a partial `backend.zip`.

## Fix

Made the zip step follow outside links, skip dangling, looping and in-app directory symlinks, and walk each directory once.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`719ce530`](https://github.com/reflex-dev/reflex/pull/7881/commits/719ce5309f851d31d66718b7e3dd2d5b386d44ae) | 2026-11-13 | MaiAditya | fix: handle symlinks when zipping the app for export |
| [`bd018b46`](https://github.com/reflex-dev/reflex/pull/7881/commits/bd018b4611d93346c6099f22eaa1301e56449d3f) | 2026-11-13 | MaiAditya | fix: skip looping symlinks and test the directory loop guard |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>news/+export-zip-symlinks.bugfix.md</code> | +1 | -0 |
| <code>reflex/utils/build.py</code> | +39 | -9 |
| <code>tests/units/utils/test&#95;build.py</code> | +143 | -0 |
