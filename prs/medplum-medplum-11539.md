# medplum/medplum #11539: fix(ccda): map procedure status from statusCode and use in-progress for active

- **Status:** merged 2026-11-21 by @codyebberson
- **Pull request:** https://github.com/medplum/medplum/pull/11539
- **Issue:** https://github.com/medplum/medplum/issues/11517
- **Size:** +51 / -8 in 4 files, 1 commit(s)

## Problem

C-CDA import ignored the `statusCode` of Procedure Activity Acts, so cancelled procedures came in as completed, and `active` mapped to `active`, which is not a valid R4 `Procedure.status`.

## Fix

Mapped Act status through `PROCEDURE_STATUS_MAPPER` and mapped `active` to `in-progress`, with tests.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`739a9f43`](https://github.com/medplum/medplum/pull/11539/commits/739a9f43da4c76fbae0b259f4298b9e71ce7a4d4) | 2026-11-20 | MaiAditya | fix(ccda): map procedure status from statusCode and use in-progress for active |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>packages/ccda/src/ccda-to-fhir.ts</code> | +5 | -5 |
| <code>packages/ccda/src/roundtrip.test.ts</code> | +16 | -1 |
| <code>packages/ccda/src/systems.test.ts</code> | +29 | -1 |
| <code>packages/ccda/src/systems.ts</code> | +1 | -1 |
