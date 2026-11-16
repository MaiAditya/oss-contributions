# huggingface/diffusers #15307: &#91;LoRA&#93; Only swap lora&#95;B in final&#95;layer scale/shift remaps (Flux Control, HunyuanVideo)

- **Status:** in review (opened 2026-11-16)
- **Pull request:** https://github.com/huggingface/diffusers/pull/15307
- **Issue:** https://github.com/huggingface/diffusers/issues/15305
- **Size:** +66 / -6 in 3 files, 2 commit(s)

## Problem

Converted Flux Control and HunyuanVideo LoRAs had the scale/shift halves of `final_layer.adaLN_modulation.1` swapped in `lora_A` too, which changed the LoRA delta.

## Fix

Swapped the halves only in `lora_B` (and the Flux Control `lora_B.bias`) in both converters, with a test for each.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`bad009db`](https://github.com/huggingface/diffusers/pull/15307/commits/bad009db69f0e6c65711ad6903e02f2ae9e76784) | 2026-11-16 | MaiAditya | &#91;LoRA&#93; Only swap lora&#95;B in final&#95;layer scale/shift remaps (Flux Control, HunyuanVideo) |
| [`30ebd63a`](https://github.com/huggingface/diffusers/pull/15307/commits/30ebd63ab7244e3f99717ab7a1fb83a565c22803) | 2026-11-16 | MaiAditya | Use minimal tensors in the Flux Control final layer LoRA test |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>src/diffusers/loaders/lora&#95;conversion&#95;utils.py</code> | +9 | -5 |
| <code>tests/models/transformers/test&#95;models&#95;transformer&#95;flux.py</code> | +38 | -0 |
| <code>tests/models/transformers/test&#95;models&#95;transformer&#95;hunyuan&#95;video.py</code> | +19 | -1 |
