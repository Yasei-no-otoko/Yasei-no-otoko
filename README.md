# 野生の男 / Yasei-no-otoko

Game Programmer · Tokyo / Japan

Unity / インタラクティブ表現から、AI プロダクト、
AMD Radeon / ROCm 向けの GPU 最適化まで。
公開できるコードと、その再現手順・検証結果を GitHub に残しています。

> [!IMPORTANT]
> 株式会社ワイルドマンの商業ゲーム関連コードは会社側で別管理しているため、
> この公開 GitHub とコミットログには掲載されていません。
> したがって、ここで見える履歴は個人の全職歴や商業案件の実装範囲を
> 網羅するものではありません。

## 現在のフォーカス

- AMD GPU / ROCm / PyTorch / Triton を使った生成 AI ワークロードの検証と最適化
- 根拠・再現性・ローカル実行を重視した AI エージェントとツール
- TypeScript / Next.js / Three.js によるインタラクティブな Web 体験
- Unity / C# によるゲームと VR インタラクション

## 代表的な公開プロジェクト

以下は、このアカウントのオリジナル公開リポジトリから選んだものです。

- [KoushiKo Vault](https://github.com/Yasei-no-otoko/koushiko-vault) —
  文書ページや動画タイムコードに基づく回答と証拠リールを生成する、
  ローカルファーストのメディア調査エージェント
- [ComfyUI RDNA35 Attention][rdna35] —
  PyTorch ROCm / Triton を用いた、RDNA 3.5 向け ComfyUI attention の
  実装・ベンチマーク研究
- [ComfyUI AMD Video Upscaler][amd-upscaler] —
  AMD AMF と FFmpeg の `sr_amf` を利用する ComfyUI 動画アップスケールノード
- [ModelDuel](https://github.com/Yasei-no-otoko/ModelDuel) —
  2 つのモデルの予測を同じ条件で比較し、証拠から理解を更新する学習体験

## 公開コードの歩み

| 時期 | 領域 | 公開コード |
| --- | --- | --- |
| 2012–2014 | HTML5 / JavaScript、ゲーム、入力インタラクション | [RGBWars](https://github.com/Yasei-no-otoko/RGBWars)、[Momo](https://github.com/Yasei-no-otoko/Momo)、[blastbuster-vr](https://github.com/Yasei-no-otoko/blastbuster-vr) |
| 2016–2017 | Unity / C#、制作支援 | [HNestedPrefab](https://github.com/Yasei-no-otoko/HNestedPrefab) |
| 2026 | AI を組み込んだ Web / 3D プロダクト | [ModelDuel](https://github.com/Yasei-no-otoko/ModelDuel) |
| 2026 | AMD Radeon / ROCm、ComfyUI、GPU 最適化 | [ComfyUI AMD Video Upscaler](https://github.com/Yasei-no-otoko/ComfyUI-AMD-Video-Upscaler)、[ComfyUI RDNA35 Attention](https://github.com/Yasei-no-otoko/ComfyUI-RDNA35-Attention) |
| 2026 | ローカル AI と根拠ベースのエージェント | [KoushiKo Vault](https://github.com/Yasei-no-otoko/koushiko-vault) |

各プロジェクトの README には、設計上の判断、動作条件、テスト方法、ベンチマークの前提をできる限り記録しています。

## 技術領域

- Languages: `Python` · `TypeScript` · `JavaScript` · `C#`
- Product / Web: `Unity` · `React` · `Next.js` · `Three.js` · `FastAPI`
- GPU / Media: `PyTorch` · `ROCm` · `Triton` · `ComfyUI` · `FFmpeg / AMF`

[rdna35]: https://github.com/Yasei-no-otoko/ComfyUI-RDNA35-Attention
[amd-upscaler]: https://github.com/Yasei-no-otoko/ComfyUI-AMD-Video-Upscaler
