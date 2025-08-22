---
title: "「Excel」に「COPILOT」関数が導入へ、AIを数式へ簡単に組み込める／Windows/Mac向けベータ版で展開開始"
source: "https://forest.watch.impress.co.jp/docs/news/2039711.html"
author:
  - "[[株式会社インプレス]]"
published: 2025-08-19
created: 2025-08-22
description: "米Microsoftは8月19日（現地時間）、デスクトップ版「Microsoft Excel」に「COPILOT」関数を導入する方針を明らかにした。「Excel」スプレッドシートに自然言語のプロンプト（指令文）を入力し、必要に応じてセル値を参照すれば、「Copilot」がAIを用いて即座に結果を返してくれる。大規模言語モデル（LLM）へのアクセスが手軽になり、テキストの分析やコンテンツの生成をその場で依頼できるようになって便利だ。"
tags:
  - "clippings"
---
2025年8月19日 07:35

[![](https://asset.watch.impress.co.jp/img/wf/docs/2039/711/image_top_l.png)](https://forest.watch.impress.co.jp/img/wf/docs/2039/711/html/image_top.png.html)

デスクトップ版「Microsoft Excel」に「COPILOT」関数を導入へ

- [窓の杜から  
	ダウンロード](https://forest.watch.impress.co.jp/library/software/microsof365/)

　米Microsoftは8月19日（現地時間）、デスクトップ版「Microsoft Excel」に「COPILOT」関数を導入する方針を明らかにした。「Excel」スプレッドシートに自然言語のプロンプト（指令文）を入力し、必要に応じてセル値を参照すれば、「Copilot」がAIを用いて即座に結果を返してくれる。大規模言語モデル（LLM）へのアクセスが手軽になり、テキストの分析やコンテンツの生成をその場で依頼できるようになって便利だ。

　「COPILOT」関数は、「Excel Labs」でテストされていた「LABS.GENERATIVEAI」関数の後継だ。

　この新しい関数は「Excel」の計算エンジンに組み込まれており、スプレッドシートのデータが変更されれば、結果も自動でアップデートされる。わざわざスクリプトを再実行したり、アドオンを更新する必要はなくなる。

　また、既存の「Excel」関数との組み合わせも可能。数式内でAIを呼び出すのはもちろん、他の数式の結果をプロンプトの一部として使用することもできる。複数の結果をグリッド全体にスピルする動的配列として返すことも可能だ。

　「COPILOT」関数のシグネチャー（書式）は以下の通り。テキストの要約、サンプルデータの生成、コンテンツの分類、テキストの生成などに用いることができる。

```
=COPILOT(prompt_part1, [context1], [prompt_part2], [context2], ...)
```

　一方で、厳密な数値計算には向いていない。合計や平均を求めるといった処理には、専用の「Excel」関数を活用すべきだ。

[![](https://asset.watch.impress.co.jp/img/wf/docs/2039/711/image2_l.png)](https://forest.watch.impress.co.jp/img/wf/docs/2039/711/html/image2.png.html)

参照したセルのデータを、指定したカテゴリーに分類するプロンプトを数式に組み込む

[![](https://asset.watch.impress.co.jp/img/wf/docs/2039/711/image3_l.png)](https://forest.watch.impress.co.jp/img/wf/docs/2039/711/html/image3.png.html)

結果。AIによる応答は結果が不定である点には注意したい。厳密な計算は専用の「Excel」関数を活用すべきだ

　また、「COPILOT」関数はすでにAIモデルが知っている知識（2024年6月以前の情報）や、引数で与えられたデータ範囲にしかアクセスできない。リアルタイムのWeb情報や他のブックやファイルのデータ、業務情報などは利用できないので注意したい。もっとも、この問題はいずれ解決される見込みだ。

## 要件と展開状況

　「COPILOT」関数の利用には「Microsoft 365 Copilot」ライセンスが必要で、まずは以下のBetaチャネル製品に展開される。

- Windows：バージョン 2509（ビルド 19212.20000）以降
- Mac：バージョン 16.101（ビルド 25081334）以降

　「Excel for the web」への展開も、間もなく「Frontier」プログラムを通じて行われる予定だ。

　なお、「COPILOT」関数で送られたデータがAIモデルのトレーニングや改善に利用されることはないとのこと。入力された情報の機密は保たれ、要求された出力を生成するためだけに用いられる。

　利用制限は今のところ10分ごとに100回まで、1時間当たり300回まで。この制限は将来的に緩和される見込みだ。

Amazonで購入

- [![](https://images-na.ssl-images-amazon.com/images/P/B0DFP8T4N5.09._SCTZZZZZZZ_PE.jpg)](https://www.amazon.co.jp/s?k=Microsoft+Excel?tag=impresswatch-18-22&ref=nosim)
	[「Microsoft Excel」関連商品](https://www.amazon.co.jp/s?k=Microsoft+Excel&tag=impresswatch-18-22&ref=nosim) [Amazonで購入](https://www.amazon.co.jp/s?k=Microsoft+Excel&tag=impresswatch-18-22&ref=nosim)

**窓の杜をフォローして最新記事をチェック！**