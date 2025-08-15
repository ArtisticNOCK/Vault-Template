

> このMarkdownは、**CursorのAgentモード**で呼び出されると、そのまま手順として実行される想定です。  
> 目的：`stock/07_Articles/<最新日付>/` にある全Markdownを走査し、**①タイトル ②記事ページリンク ③元記事のURL ④要約**を表にまとめて、`stock/08_OnePageSummary/<同じ日付>.md` に出力します。  
> 実行前後に**件数カウント**と**完全性チェック**を行い、不整合があればエラーとして報告します。

---

## 前提ディレクトリ

- ルート: `stock/`
- 入力: `stock/07_Articles/<YYYY-MM-DD>/*.md`
- 出力: `stock/08_OnePageSummary/<YYYY-MM-DD>.md`

---

## 可変パラメータ

- `USE_LATEST_DATE`: `true` / `false`  
  - `true` … `07_Articles` 配下から**最新日付**フォルダを自動検出  
  - `false` … `TARGET_DATE` を使用
- `TARGET_DATE`: `"2025-08-15"` のような `YYYY-MM-DD` 文字列（`USE_LATEST_DATE=false` のとき有効）
- `SUMMARY_MAX_LINES`: 要約をまとめる最大行数（既定: `3`）

> 実運用では以下の既定値でOK：  
> `USE_LATEST_DATE = true` / `SUMMARY_MAX_LINES = 3`

---

## 取り出しルール（ファイル解析）

各記事Markdownから次を抽出します。**存在しない場合はフォールバック**します。

1. **タイトル**
   - 最初に出現するH1（`# `）行を採用。
   - なければ、ファイル名（拡張子抜き）をタイトルに。

2. **記事ページリンク（Obsidian内部リンク）**
   - 表示は常に固定文言「記事ページ」。
   - Markdownリンク形式で  
     `[記事ページ](07_Articles/<YYYY-MM-DD>/<ファイル名>.md)`  
     を生成（Vault相対パス）。

3. **元記事のURL**
   - 表示は常に固定文言「元記事のURL」。
   - YAMLフロントマターの `source:` または `url:` を優先。
   - 見つからなければ本文内の最初の `http(s)://`。
   - それもなければ `—`。

4. **要約**
   - セクション見出し「① 概要」「概要」「要約」の直下を優先。
   - 箇条書きがあれば**先頭から `SUMMARY_MAX_LINES` 行**。
   - なければ冒頭から**改行区切りで `SUMMARY_MAX_LINES` 行**。
   - 行頭の記号を除去し、改行は `<br>` に変換。

---

## 完全性チェック

- 入力記事数 = 表の行数（ヘッダ除く）で一致。
- タイトル欠落はファイル名で補完。
- 「記事ページ」列のリンクが全行に存在する。
- 抽出不可があれば警告として該当ファイル名を列挙。

---

## 出力フォーマット（08_OnePageSummary）

`stock/08_OnePageSummary/<YYYY-MM-DD>.md` に以下のMarkdownを保存：

```md
# One Page Summary — <YYYY-MM-DD>

- 生成日時: <YYYY-MM-DD HH:mm>
- 入力記事数: <N> 件

| Title | 記事ページ | 元記事のURL | Summary |
|---|---|---|---|
| <タイトル> | [記事ページ](07_Articles/<YYYY-MM-DD>/<ファイル名>.md) | [元記事のURL](<URL or —>) | <要約（最大<SUMMARY_MAX_LINES>行、改行は `<br>` に変換）> |
| ... | ... | ... | ... |

---

## 完全性チェック
- 表行数（ヘッダ除く）: <M> 行
- 一致判定: <OK/NG>
- 警告: 
  - <問題があれば列挙、なければ「なし」>
