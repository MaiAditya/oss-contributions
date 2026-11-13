# reflex-dev/reflex #7892: fix: name a forwarded scheme mismatch in the origin rejection warning

- **Status:** in review (opened 2026-11-13)
- **Pull request:** https://github.com/reflex-dev/reflex/pull/7892
- **Issue:** https://github.com/reflex-dev/reflex/issues/7857
- **Size:** +59 / -11 in 3 files, 1 commit(s)

## Problem

With trusted proxies, a socket origin rejected because `X-Forwarded-Proto` was `https` produced a warning that only named the Host headers and advised the wrong fix.

## Fix

Named the trusted `X-Forwarded-Proto` in the warning and added a hint for the scheme mismatch case.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`fb02d245`](https://github.com/reflex-dev/reflex/pull/7892/commits/fb02d24508eb50999499e89eb7ca1308ff2bba61) | 2026-11-13 | MaiAditya | fix: name a forwarded scheme mismatch in the origin rejection warning |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>news/+origin-warning-forwarded-proto.bugfix.md</code> | +1 | -0 |
| <code>reflex/app.py</code> | +19 | -11 |
| <code>tests/units/test&#95;app.py</code> | +39 | -0 |
