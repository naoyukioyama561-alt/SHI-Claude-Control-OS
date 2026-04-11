# 20-proof/ -- 実証レベルの定義と証拠（日本語版）
Language: [English version](../../20-proof/README.md)

## ★の意味

本リポジトリの★評価は**読者が公開リポジトリの情報だけでどこまで検証できるか**で定義しています。

| レベル | 定義 | 読者にできること |
|--------|------|----------------|
| ★★★★★ | 設計思想が完全に公開されており、読者が自環境で構築可能 | 30-adoption/try/ で体験 → 10-framework/ で理解 → 自環境で構築 |
| ★★★★ | 設計思想は公開済みだが、定量データはPhase1/Phase2で提供 | 考え方は検証可能。数値はPhase1/Phase2 |
| ★★★ | 概念と一部の証拠画像のみ。詳細設計・定量データはPhase1/Phase2 | 概念の妥当性のみ判断可能 |

### ★5（3項目）: No.1, No.2, No.12
公開リポジトリだけで設計思想を理解し、自分のAIに適用できます。

### ★4（8項目）: No.3, 4, 5, 6, 7, 8, 9, 13
設計思想は理解できるが、定量データはPhase1/Phase2で提供。

### ★3（4項目）: No.10, 11, 14, 15
概念は公開しているが、詳細設計と定量データの両方がPhase1/Phase2。

## 公開版 / 非公開版の範囲

各成果の範囲分けの詳細は [成果一覧](../../20-proof/achievements/README.md) を参照（英語版テーブル、EN/JA両リンク付き）。なお、**15件すべてに本リポジトリ内の公開ページがあります**。下表の区分は「より深い詳細がどのティアにあるか」を示します。

| レベル | 目的 | 含まれるもの |
|--------|------|------------|
| **公開版** | 体験＋方法論 | 30-adoption/try/の制御OS＋10-framework/の構造解説＋FM40件 [observed: single environment] 概要＋15件 [observed: single environment] の公開成果ページ（6件 [observed: single environment] 詳細＋9件 [observed: single environment] 概要）＋代表SVG図 |
| **Phase1** | 作り方の考え方 | 設計書10件 [observed: single environment]＋FM60件 [observed: single environment] 詳細＋図＋サンプル会話＋reason_code表 |
| **Phase2** | 構造観測の方法 | 全ファイル＋全画像＋FM132件 [observed: single environment] 全＋実証ログ＋ソース抜粋 |
| **書籍** | SHI理論でのAI統治 | 全7章 [observed: single environment]＋再現手順（具体的な鍵は一切なし） |

> **Phase 1 / Phase 2 は将来の公開フェーズであり、価格帯ではありません。** 15件すべての成果ページは今すぐ本リポジトリで公開されています。

## 注記
- 本評価は著者自身によるものです。独立した第三者検証は今後の課題です
- ★3の成果は「実証が弱い」のではなく「公開情報での検証可能性が低い」を意味します

## ファイル一覧
| ファイル | 内容 |
|---------|------|
| [achievements/](achievements/) | 各成果の詳細ドキュメント（日本語） |
| [timeline-ja.md](timeline-ja.md) | 開発の時系列事実（日本語） |
| [metrics-ja.md](metrics-ja.md) | 公開可能な定量データ（日本語） |

---

→ **次**: [30-adoption/try/](../30-adoption/try/) — 自分で試す

→ 関連: [10-framework/](../10-framework/) — なぜ効くか理解する | [READMEに戻る](../README-ja.md)

*この文書は [SHI-Claude-Control-OS](https://github.com/naoyukioyama561-alt/SHI-Claude-Control-OS) プロジェクトの一部です。*
