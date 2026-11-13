# reflex-dev/reflex #7880: fix: validate the trusted X-Forwarded-For entry as client&#95;ip

- **Status:** in review (opened 2026-11-13)
- **Pull request:** https://github.com/reflex-dev/reflex/pull/7880
- **Issue:** https://github.com/reflex-dev/reflex/issues/7854
- **Size:** +86 / -2 in 4 files, 3 commit(s)

## Problem

With `trusted_proxy_hops` set, `client_ip` could hold an `X-Forwarded-For` entry with a port, IPv6 brackets or non-address text.

## Fix

Added `_forwarded_client_ip()` to strip ports and brackets, normalise addresses and fall back to the peer address if invalid.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`b3a32ee9`](https://github.com/reflex-dev/reflex/pull/7880/commits/b3a32ee9c93c5504c6b3a4f88121f1451d947f31) | 2026-11-13 | MaiAditya | fix: validate the trusted X-Forwarded-For entry as client&#95;ip |
| [`47a5c935`](https://github.com/reflex-dev/reflex/pull/7880/commits/47a5c935626fb71a87f44585b7c897a5b6c1d0b7) | 2026-11-13 | MaiAditya | fix: reject malformed brackets and ports in X-Forwarded-For entries |
| [`1b0af00e`](https://github.com/reflex-dev/reflex/pull/7880/commits/1b0af00eb6ade34757746516f3a4ed1bed7f54d0) | 2026-11-13 | MaiAditya | fix: reject IPv6 zone indexes in X-Forwarded-For entries |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>docs/advanced&#95;onboarding/configuration.md</code> | +1 | -1 |
| <code>news/+forwarded-client-ip-validation.bugfix.md</code> | +1 | -0 |
| <code>reflex/app.py</code> | +48 | -1 |
| <code>tests/units/test&#95;app.py</code> | +36 | -0 |
