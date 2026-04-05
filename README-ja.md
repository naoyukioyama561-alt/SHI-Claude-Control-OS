# SHI-Claude-Control-OS

[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE) [![SSRN Preprint](https://img.shields.io/badge/SSRN-6299258-blue.svg)](https://ssrn.com/abstract=6299258)

*昨日AIにコードレビューを頼んだ。今日も同じミスをする。ルールを説明し直す。「理解しました」と言って、1時間後に破る。心当たりはありませんか？*

**あなたのAIは、昨日やらかした失敗を今日もう覚えていない。このプロジェクトは、それに構造的に対処する。**
AIが同じミスを繰り返す、文脈を失う、理解したと言って守らない——そんな経験がある人へ。

> **これは何か**: 構造的ガバナンス手法 + コピペ用テンプレート + 検証ガイド——AIの繰り返し失敗を減らすためのもの。
> **無料で得られるもの**: 40の失敗モード分類、3つのAIモデル用Control OSテンプレート、Before/Afterデモ、検証プロトコル。
> **最初の30秒**: 1. [Control OSをコピー](30-adoption/ja/try/control-os-claude.md) → 2. [Before/Afterテストを実行](30-adoption/ja/try/before-after-demo.md) → 3. [主張をPROVE-ITで確認](PROVE-IT-ja.md)

> **無料版だけで試行・検証・反証が完結します。** インストール不要——コピーして貼り付けてテストするだけ。

### 今すぐ確認できる実際の動き
**[公開安全なインタラクティブデモを開く（GitHub Pages）](https://naoyukioyama561-alt.github.io/SHI-Claude-Control-OS/demo/jp/index.html)**
- 日本語版デモ: [こちらをクリック](https://naoyukioyama561-alt.github.io/SHI-Claude-Control-OS/demo/jp/index.html)
- 英語版デモ: [こちらをクリック](https://naoyukioyama561-alt.github.io/SHI-Claude-Control-OS/demo/en/index.html)

*このデモはあなたの個人環境とは**完全に独立**した静的ページです。ボタン・検索・フィルタなど実際に操作できます。*

---

## いま、あなたのAIの中で起きていること

| | 構造制御なし | Control OS導入後 |
|---|---|---|
| 同じバグ、また発生 | AIは謝る。明日また同じことをする | 失敗モードとして分類され、構造的にブロック |
| 月曜朝：新セッション | 金曜の積み上げがゼロ | 継承システムが「痛み」をセッションを超えて保持 |
| 「ルールは理解しました」 | 同じ作業サイクル内で違反する | 外部監視が出荷前に違反を検知 |
| 負荷がかかると | コンテキスト増加とともに品質が静かに劣化 | 4+1層品質システムが基準を維持 |
| しばらく離れて戻ると | 文脈の継続性が失われている | 後継AIがルールだけでなく「判断」を継承 |

<p align="center">
  <img src="images/diagrams/before-after-comparison.svg" alt="Before/After: 構造的統治あり・なしのAI行動比較" width="720">
</p>

---

## 今すぐ試す（30秒）

Control OSをAIのシステムプロンプトにコピペしてください。[Before/Afterテスト](30-adoption/ja/try/before-after-demo.md)を実行してください。違いを確認してください。

| あなたのAI | Control OSテンプレート | テスト所要時間 |
|---------|-------------------|--------------|
| Claude Code / Claude | [control-os-claude](30-adoption/ja/try/control-os-claude.md) | 30秒 |
| ChatGPT（GPT-4o / GPT-5） | [control-os-gpt](30-adoption/ja/try/control-os-gpt.md) | 30秒 |
| GitHub Copilot | [control-os-copilot](30-adoption/ja/try/control-os-copilot.md) | 30秒 |

[FM-40チートシート](30-adoption/ja/try/fm-40-cheatsheet.md)も確認してください -- どのAIアシスタントでも今日から観察できる40の失敗モードです。

---

<details>
<summary><strong>エビデンスラベルと用語</strong> — 本リポジトリの数値・用語の読み方</summary>

**エビデンスラベル**: `[観測値：単一環境]` = 単一環境で計測。`[設計目標]` = 設計上の目標、ベンチマークではない。`[例示値]` = 説明用、データではない。詳細は [GLOSSARY-ja.md](GLOSSARY-ja.md) を参照。

**用語**: 3層分離（役割分担）≠ 4+1品質システム（品質管理スタック）≠ 5層ループ（統治サイクル）。同じシステムの別次元。詳細は [GLOSSARY-ja.md](GLOSSARY-ja.md) を参照。

主要な主張には検証経路を付しています。検証手順は [PROVE-IT-ja.md](PROVE-IT-ja.md) に記載。
</details>

> **概念マップ**（この6つを覚えれば読める）:
> FM = 失敗の名前 | 制御OS = その場の抑制 | 3層分離 = 役割分担 | 4+1 = 品質管理 | 5層ループ = 統治サイクル | SHI = 理論的基盤

## リポジトリマップ

各層に1つの認知仕事だけを与えています。今の目的に合う層を選んでください。

```
いまここ
  |
  |-- 「試したい」               --> 30-adoption/ja/try/     （30秒）
  |-- 「証拠を見たい」            --> PROVE-IT-ja.md          （15分）
  |-- 「なぜ効くのか知りたい」     --> 10-framework/ja/           （30分）
  |-- 「実績データが見たい」       --> 20-proof/ja/               （じっくり）
  |-- 「自分の環境で作りたい」     --> 30-adoption/ja/templates/ （あなたの環境で）
  |
  さらに深く:
  |-- 継承と哲学                 --> 40-heritage/
  |-- スコープとエディション       --> 50-boundary/ [EN]
  |-- 詳細なスコープ表            --> SCOPE-MATRIX-ja.md
```

| 層 | 1つの認知仕事 | 中身 |
|-------|------------------|-------------------|
| **10-framework/** | 方法論を理解する | 失敗モード分類体系、Control OS設計、3層分離、品質システム、SHI理論 |
| **20-proof/** | 主張を検証する | 実証付き15の成果、ヒーロー画像、メトリクス、タイムライン |
| **30-adoption/** | 自分で使う | コピペ用Control OS、FM-40チートシート、Before/Afterデモ、移植テンプレート |
| **40-heritage/** | 哲学を知る | このプロジェクトが存在する理由、CC継承構造 |
| **50-boundary/** | 範囲を把握する | 無料/有料エディション定義、Avoidance OS |

---

## 背景にある研究

この方法論は**SHI（Structural Hierarchical Intelligence：構造的階層知能）理論**に基づいています。AIの失敗をランダムなノイズではなく、観察可能で、分類可能で、構造的に予防可能な現象として扱います。約1か月の集中的な観察 [観測値：単一環境・単一運用者・N未公開] から132の失敗モード [観測値：単一環境・単一運用者・N未公開] を分類し、統治アーキテクチャとして体系化しました。

> Oyama, N. (2025). *Structural Hierarchical Intelligence for AI Governance*. SSRN: [https://ssrn.com/abstract=6299258](https://ssrn.com/abstract=6299258)

---

## クイックリンク

- [START-HERE](START-HERE-ja.md) -- 3分でわかるオリエンテーション
- [PROVE-IT](PROVE-IT-ja.md) -- すべての主張を自分で検証
- [インタラクティブ・ダッシュボード](docs/dashboard.html)（ファイルをダウンロードしてブラウザで開く、またはGitHub Pagesを有効化）-- タイムライン + レイヤーシミュレーター
- [SCOPE-MATRIX](SCOPE-MATRIX-ja.md) -- 無料版と有料版の詳細な範囲分け
- [CITATION](CITATION.cff) -- 引用方法
- [GLOSSARY-ja](GLOSSARY-ja.md) -- 用語集
- [CONTRIBUTING-ja](CONTRIBUTING-ja.md) -- 観測報告の出し方。あなたの観測がFM分類や検証導線の改訂に直接つながります

---

![Dashboard](images/diagrams/dashboard-overview.svg)


→ [実例を見る](20-proof/public-case-01-ja.md)

> [なぜ作ったのか →](40-heritage/ja/why-i-am-doing-this.md)

---

<sub>

**ライセンス**: [MIT](LICENSE) -- 自由に使用・改変・再配布できます。

⭐ 役に立ったらStarをお願いします — AI統治への構造的アプローチを求めている人に届きます。
[![Star this repo](https://img.shields.io/github/stars/naoyukioyama561-alt/SHI-Claude-Control-OS?style=social)](https://github.com/naoyukioyama561-alt/SHI-Claude-Control-OS)

**免責事項**: 本リポジトリに記載されたすべての効果は著者の環境で観察されたものです。AIモデル、利用コンテキスト、設定によって結果は異なる場合があります。結論を出す前に、すべての主張をご自身の環境で検証してください。本プロジェクトは方法論を提供するものであり、結果を保証するものではありません。本リポジトリの内容は専門的助言を構成しません。

**Language**: [English version](README.md)

</sub>
