---
title: "Google、AI学習に必要なデータを最大1万分の1に削減可能な新手法を発表"
source: "https://ledge.ai/articles/google_ai_data_reduction_method"
author:
  - "[[Ledge.ai]]"
published:
created: 2025-08-21
description: "AI・人工知能関連のニュースやトレンドを高頻度で配信！最新ニュースやインタビュー、イベントレポートなどAIに関するさまざまな情報を独自の切り口で掲載"
tags:
  - "clippings"
---
[Top](https://ledge.ai/) \> \> Google、AI学習に必要なデータを最大1万分の1に削減可能な新手法を発表

学術＆研究

2025 / 8 / 19 \[TUE\]

![Google、AI学習に必要なデータを最大1万分の1に削減可能な新手法を発表のサムネイル画像](https://storage.googleapis.com/ledge-ai-prd-public-bucket/media/Achieving_10_000x_training_data_reduction_fc90dd6f52/Achieving_10_000x_training_data_reduction_fc90dd6f52.jpg)[Google](https://ledge.ai/search?q=Google)

[

論文

](https://ledge.ai/search?q=%E8%AB%96%E6%96%87)

画像の出典： [Google Research](https://research.google/blog/achieving-10000x-training-data-reduction-with-high-fidelity-labels/)

Googleは2025年8月７日、自社の研究ブログで、AIモデルの学習に必要なトレーニングデータ量を最大で1万分の1に削減しながら、モデル品質を維持できる新しい学習手法を [発表](https://research.google/blog/achieving-10000x-training-data-reduction-with-high-fidelity-labels/) した。従来の膨大なデータ収集とラベリングに依存するアプローチに比べ、効率的かつ高精度なラベル付けを活用する点が特徴となる。

## 新手法の概要

Google Researchが公開した今回の手法は、まず大規模言語モデル（LLM）を用いてデータをクラスタリングし、モデルが誤りやすい境界事例を抽出する。その後、専門家が少数のデータに高精度なラベルを付与し、ファインチューニングに利用する仕組みだ。

**■ LLMによる事前ラベリング→クラスタリング→境界ペア抽出→専門家ラベル→反復学習の流れ（①〜④）** ![CurationStrategies1_ProcessFinal.width-1250.png](https://storage.googleapis.com/ledge-ai-prd-public-bucket/media/Curation_Strategies1_Process_Final_width_1250_c73b951bad/Curation_Strategies1_Process_Final_width_1250_c73b951bad.png)

画像の出典： [Google Research](https://research.google/blog/achieving-10000x-training-data-reduction-with-high-fidelity-labels/)

## 実験結果

通常10万件規模のラベルが必要とされるケースにおいて、この手法では250〜450件の専門家ラベルで同等以上の成果を得られることが示された。実験にはGoogleの軽量モデル「Gemini Nano-1（1.8Bパラメータ）」と「Gemini Nano-2（3.25Bパラメータ）」が用いられ、特にNano-2ではモデルと専門家ラベルの一致度を示す指標「Cohen’s Kappa」が55〜65％向上した。

**■ Cohen’s Kappaとサンプル数の関係。キュレーション（緑）が従来（赤破線）を広く上回り、特に3.25Bモデルで効果が顕著** ![CurationStrategies4_Results.width-1250.png](https://storage.googleapis.com/ledge-ai-prd-public-bucket/media/Curation_Strategies4_Results_width_1250_6dca7b850b/Curation_Strategies4_Results_width_1250_6dca7b850b.png)

画像の出典： [Google Research](https://research.google/blog/achieving-10000x-training-data-reduction-with-high-fidelity-labels/)

## 意義と応用可能性

この成果により、AIの開発に伴うデータ収集やアノテーションのコストを大幅に削減できる可能性がある。特に医療や広告など、専門知識が求められる領域での利用価値が高いとされる。また、AI開発の持続可能性を高め、より幅広い分野での応用を後押しすることが期待される。

Googleは今後も効率的なAIトレーニング手法の研究を続け、より少ないデータで高品質なモデルを構築できる仕組みの標準化を目指すとしている。

[関連記事：2028年、AIモデルの学習データ枯渇が現実に？ Natureが示す現状と課題](https://ledge.ai/articles/ai_data_crisis_2028)

[関連記事：枯渇するAIトレーニングデータ：データ収集の新たな課題とその影響 MIT主導の調査団体が発表](https://ledge.ai/articles/dpi_consent_in_crisis_paper)

[関連記事：Wikipedia、Kaggleと提携しAI学習用構造化データセットを公開](https://ledge.ai/articles/wikipedia_kaggle_ai_dataset)

[関連記事：NVIDIA、LLMの訓練に必要なデータセットを生成するモデル「Nemotron-4 340B」を発表 商用利用可](https://ledge.ai/articles/nvidia_nemotron_4_340)

[関連記事：Google、「Gemini」に新機能「Gems」と画像生成AI「Imagen 3」を追加](https://ledge.ai/articles/google_gemini_update_gems_and_imagen3)

関連するタグ[Google](https://ledge.ai/search?q=Google)

[

論文

](https://ledge.ai/search?q=%E8%AB%96%E6%96%87)

![mailmagazine_250819](https://storage.googleapis.com/ledge-ai-prd-public-bucket/media/250_300_2_281c243244/250_300_2_281c243244.png)

![](https://storage.googleapis.com/ledge-ai-prd-public-bucket/media/C7_P6_S_Gks_400x400_c0281f2ebf/C7_P6_S_Gks_400x400_c0281f2ebf.jpeg) Ledge.ai 編集部

Ledge.ai編集部です。最新のAI関連技術、テクノロジー、AIのビジネス活用事例などの情報を毎日発信しています。