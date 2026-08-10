# Yasei-no-otoko

Game Programmer · Tokyo, Japan

From Unity and interactive experiences to AI products and GPU optimization
for AMD Radeon and ROCm, I document the code I can make public on GitHub,
together with reproduction steps and verification results.

> [!IMPORTANT]
> Code related to commercial games developed at Wildman Inc. is managed
> separately by the company and is not included in this public GitHub account
> or its commit history. Therefore, the history shown here is not a complete
> record of my career or the full scope of my implementation work on commercial
> projects.

## Current Focus

- Evaluating and optimizing generative AI workloads on AMD GPUs with ROCm,
  PyTorch, and Triton
- Building AI agents and tools around evidence, reproducibility, and local
  execution
- Creating interactive web experiences with TypeScript, Next.js, and Three.js
- Developing games and VR interactions with Unity and C#

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

| Period | Area | Public repositories |
| --- | --- | --- |
| 2012–2014 | HTML5 / JavaScript, games, and input interactions | [RGBWars](https://github.com/Yasei-no-otoko/RGBWars), [blastbuster-vr](https://github.com/Yasei-no-otoko/blastbuster-vr) |
| 2026 | Web / 3D products with integrated AI | [ModelDuel](https://github.com/Yasei-no-otoko/ModelDuel) |
| 2026 | AMD Radeon / ROCm, ComfyUI, and GPU optimization | [ComfyUI AMD Video Upscaler](https://github.com/Yasei-no-otoko/ComfyUI-AMD-Video-Upscaler), [ComfyUI RDNA35 Attention](https://github.com/Yasei-no-otoko/ComfyUI-RDNA35-Attention) |
| 2026 | Local AI and evidence-grounded agents | [KoushiKo Vault](https://github.com/Yasei-no-otoko/koushiko-vault) |

Wherever possible, each project's README documents its design decisions,
runtime requirements, testing procedures, and benchmark assumptions.

## Technical Areas

- Languages: `Python` · `TypeScript` · `JavaScript` · `C#`
- Product / Web: `Unity` · `React` · `Next.js` · `Three.js` · `FastAPI`
- GPU / Media: `PyTorch` · `ROCm` · `Triton` · `ComfyUI` · `FFmpeg / AMF`

[rdna35]: https://github.com/Yasei-no-otoko/ComfyUI-RDNA35-Attention
[amd-upscaler]: https://github.com/Yasei-no-otoko/ComfyUI-AMD-Video-Upscaler
