# Yasei-no-otoko

**Haruto Watanabe · GPU & AI Inference Performance · XR / Game Engineering**  
Founder & Hands-on Technical Lead, Wildman Inc. · Tokyo, Japan

I build and optimize systems across real-time graphics, AI inference, and
AMD Radeon / ROCm, with 15+ years of software development and XR work from
Oculus Rift DK1 through Apple Vision Pro. My public work connects
application-level bottlenecks to runtime behavior, numerical correctness,
and measurable end-to-end results.

**Recent results:** three merged PRs in [ROCmFPX][rocmfpx]; **20–50% faster
end-to-end processing** across my measured Qwen Image 2.1 and MiniMax H3
workflows using ROCmFPX; and MiniMax H3 **audio-VAE processing reduced from
approximately 5.0 s to 0.3 s** for a 5-second video workload.

> [!IMPORTANT]
> Code related to commercial games developed at Wildman Inc. is managed
> separately by the company and is not included in this public GitHub account
> or its commit history. Therefore, the history shown here is not a complete
> record of my career or the full scope of my implementation work on commercial
> projects.

## Selected Inference Results — September 2026

| Scope | Measured result | Interpretation |
| --- | --- | --- |
| Qwen Image 2.1 and MiniMax H3 workflows using ROCmFPX | **20–50% faster E2E processing** across measured workflows | Workload-specific application results; the reported speedup is not a universal hardware or model claim. |
| MiniMax H3 audio VAE for a 5-second video workload | **~5.0 s → ~0.3 s** | **~16.7× stage speedup / ~94% less processing time**, calculated from the rounded timings. This is the audio-VAE stage, not total video-generation time. |

These are my local measurements for the tested configurations. They are
separate from the PR-specific correctness and compatibility validations below;
the three merged PRs are not presented as individually causing all of these
performance gains. The E2E range is reported as a speed improvement, not as
a 20–50% reduction in elapsed time.

Related public update: [ROCmFPX / generative-AI performance work][performance-update].

## Merged Contributions to ROCmFPX

All three PRs below were submitted from this account and merged into
`charlie12345/ROCmFPX` on **September 24, 2026 (JST)**.

| PR | Contribution | Validation recorded in the PR |
| --- | --- | --- |
| [#114 — Preserve probability tails in entropy-bound decoding][pr114] | Use double-precision accumulation for normalization, CDF, and entropy to avoid losing small positive probability tails in a 262,144-token vocabulary. | Analytic entropy, vocabulary-order stability, confidence boundaries, tail sampling, ties, and underflow regression coverage. This is a numerical-correctness fix, not a speed claim. |
| [#115 — Stop truncating valid repeated output before EOG][pr115] | Replace repetition-based truncation with end-of-generation-token handling so valid repeated digits and JSON-array content are not cut prematurely. | 14 model-free regression cases, including a 33-token fixture previously cut to 10 tokens. Prevents postprocessing corruption; does not guarantee valid model-generated JSON. |
| [#116 — Support Qwen3VL hidden-state checkpoints][pr116] | Enable pruned text encoders used by MiniMax H3 through optional hidden-state-only metadata while preserving ordinary Qwen3VL behavior and the public C ABI; include an upstream reduction-race fix. | On Windows / Radeon 8060S (`gfx1151`): **220/220** SOFT_MAX/GROUP_NORM tests; **280/280** bitwise-identical softmax repetitions; **30/30** bitwise-identical real-H3 hidden-state encodes. |

**Development provenance:** these PRs used OpenAI Codex for investigation,
implementation, tests, and/or validation, as disclosed in each PR. The
reduction-race fix in #116 is an unchanged backport of
[ggml-org/llama.cpp commit `9bd4c09`][reduction-fix], with its original
authorship preserved. The validation results above are the recorded PR
results, not claims of broader model-quality or hosted-CI coverage.

## Current Focus

- End-to-end generative-AI optimization on AMD GPUs: ROCmFPX, ROCm/HIP,
  PyTorch, Triton, low-precision inference, text encoders, and VAE stages
- Numerical correctness, reproducible benchmarks, regression testing, and
  clearly scoped performance claims
- AI agents and tools built around evidence, reproducibility, and local execution
- Interactive web experiences with TypeScript, Next.js, and Three.js
- Games and VR interactions with Unity, Unreal Engine, C++, and C#

## Selected Public Projects

The following projects were selected from this account's original public
repositories.

- [KoushiKo Vault](https://github.com/Yasei-no-otoko/koushiko-vault) —
  A local-first media investigation agent that produces answers grounded in
  document pages and video timecodes, together with an evidence reel
- [ComfyUI RDNA35 Attention][rdna35] —
  Implementation and benchmarking research for ComfyUI attention on RDNA 3.5
  using PyTorch ROCm and Triton
- [ComfyUI AMD Video Upscaler][amd-upscaler] —
  A ComfyUI video upscaling node powered by AMD AMF and FFmpeg's `sr_amf`
- [ModelDuel](https://github.com/Yasei-no-otoko/ModelDuel) —
  A learning experience that compares predictions from two models under the
  same conditions and uses evidence to refine understanding

## Public Code Timeline

| Period | Area | Public repositories / contributions |
| --- | --- | --- |
| 2012–2014 | HTML5 / JavaScript, games, and input interactions | [RGBWars](https://github.com/Yasei-no-otoko/RGBWars), [blastbuster-vr](https://github.com/Yasei-no-otoko/blastbuster-vr) |
| 2026 | Web / 3D products with integrated AI | [ModelDuel](https://github.com/Yasei-no-otoko/ModelDuel) |
| 2026 | AMD Radeon / ROCm, ComfyUI, and GPU optimization | [ComfyUI AMD Video Upscaler][amd-upscaler], [ComfyUI RDNA35 Attention][rdna35] |
| 2026 | Local AI and evidence-grounded agents | [KoushiKo Vault](https://github.com/Yasei-no-otoko/koushiko-vault) |
| September 2026 | Merged inference-runtime correctness and model-compatibility contributions | ROCmFPX [#114][pr114], [#115][pr115], [#116][pr116] |

Wherever possible, each project's README documents its design decisions,
runtime requirements, testing procedures, and benchmark assumptions.

## Technical Areas

- Languages: `C++` · `Rust` · `Python` · `TypeScript` · `JavaScript` · `C#`
- Product / Web: `Unity` · `Unreal Engine` · `React` · `Next.js` · `Three.js` · `FastAPI`
- GPU / Media: `ROCmFPX` · `ROCm / HIP` · `PyTorch` · `Triton` · `ComfyUI` · `FFmpeg / AMF`
- Engineering: end-to-end profiling · numerical correctness · regression tests · AI-assisted development

[rocmfpx]: https://github.com/charlie12345/ROCmFPX
[pr114]: https://github.com/charlie12345/ROCmFPX/pull/114
[pr115]: https://github.com/charlie12345/ROCmFPX/pull/115
[pr116]: https://github.com/charlie12345/ROCmFPX/pull/116
[reduction-fix]: https://github.com/ggml-org/llama.cpp/commit/9bd4c09ea571a9020f30eeef169b552625b5b5a4
[performance-update]: https://x.com/yasei_no_otoko/status/2102392974118445084
[rdna35]: https://github.com/Yasei-no-otoko/ComfyUI-RDNA35-Attention
[amd-upscaler]: https://github.com/Yasei-no-otoko/ComfyUI-AMD-Video-Upscaler
