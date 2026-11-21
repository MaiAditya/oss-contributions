# pipecat-ai/pipecat #6902: fix(zoom): confirm the finalize for an empty committed transcript

- **Status:** in review (opened 2026-11-20)
- **Pull request:** https://github.com/pipecat-ai/pipecat/pull/6902
- **Issue:** https://github.com/pipecat-ai/pipecat/issues/6901
- **Size:** +34 / -0 in 3 files, 3 commit(s)

## Problem

In turn detection mode, `ZoomAISTTService` pushed nothing when a committed transcript was empty, so the turn waited out the STT timeout before ending.

## Fix

Called `_push_transcription_finalized()` for an empty committed transcript, as the Deepgram services do.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`e96fcff7`](https://github.com/pipecat-ai/pipecat/pull/6902/commits/e96fcff7423393a5644721f055ef46b592939984) | 2026-11-20 | MaiAditya | Confirm the Zoom Scribe finalization when a commit's transcript is empty |
| [`753bee05`](https://github.com/pipecat-ai/pipecat/pull/6902/commits/753bee05722129304f80a654b22015fbfb9809a1) | 2026-11-20 | MaiAditya | Add changelog entry for &#35;6902 |
| [`382bff3a`](https://github.com/pipecat-ai/pipecat/pull/6902/commits/382bff3a901b467475371ad409f4d5a4cb305c56) | 2026-11-20 | aconchillo | Clarify the &#35;6902 changelog entry |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>changelog/6902.fixed.md</code> | +1 | -0 |
| <code>src/pipecat/services/zoom&#95;ai/stt.py</code> | +4 | -0 |
| <code>tests/test&#95;zoom&#95;ai&#95;stt.py</code> | +29 | -0 |
