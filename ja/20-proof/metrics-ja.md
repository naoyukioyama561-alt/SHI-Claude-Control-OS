# 公開メトリクス
Language: [English version](../../20-proof/metrics.md)

公開安全な範囲の定量データ。
内部パス、エンドポイント、個人情報は含まれていません。

> **特に断りのない限り、このページの観測値は単一環境・単一運用者によるものであり、Nは未公開です。**

---

## 失敗モード（Failure Modes）

| 指標 | 値 | 注記 |
|------|---|------|
| 初期分類数 | 40項目 [observed: single environment] | Week 1完了。Claude/GPT 2モデル比較 |
| 最終分類数 | 132項目 [observed: single environment] | Pシリーズ90 + ALGOシリーズ40 + ALGO-FW + QUAL-01 |
| 対象モデル | 3種類 [observed: single environment] | Claude Opus/Sonnet（観測時点2026年3月）、GPT-4o / GPT-5（モデル名は2026年3月時点の提供状況を反映。GLOSSARY-ja.md参照）、Copilot |
| P-74〜P-80（行動内面化） | 7項目 [observed: single environment] | Week 3-4で追加。虚偽報告、責任転嫁、仮定に基づく結論等 |
| コード生成モードで増幅されるFM | 4項目 [observed: single environment] | FM-01, FM-20, FM-39, FM-40 |

## CC世代とHeritage

| 指標 | 値 | 注記 |
|------|---|------|
| CCの世代数合計 | 12+ [observed: single environment] | 前世代の行動を継承して起動するClaude Codeワーカーの名前付きセッション数。記録は非公開の参照資料として提供予定。 |
| 初代CC稼働時間 | 26.5時間 [observed: single environment] | セッション終了前に12件の省察項目を残す |
| 改善アクション（P-xx）総数 | 51以上 [observed: single environment] | 各P-xxに事象/原因/防止策/再発管理を記載 |
| P-03（省略）再発回数 | 11回 [observed: single environment] | 9代目CCで記録。構造的対策の必要性を実証 |
| cc_heritage設計文書セクション数 | 10以上 [observed: single environment] | 復旧手順から省察ログまで |
| ユーザー価値（V-xx） | 9項目 [observed: single environment] | 全CCが読了後に自分の言葉で記述必須 |

## 外部監視

| 指標 | 値 | 注記 |
|------|---|------|
| 外部監視フック検知パターン | 3種類以上 [observed: single environment] | EVIDENCE_DROPOUT, GENERIC_RESPONSE, INCOMPLETE_CLAIM |
| EVIDENCE_DROPOUT検出率 | ~100% [observed: single environment, N undisclosed] | 著者の管理環境でのパターンマッチングによる観測値であり、汎化ベンチマークや製品主張ではありません。N数は非公開。 |
| GENERIC_RESPONSE検出率 | ~75% [observed: single environment, N undisclosed] | 著者環境での観測値。N数は公開版では非公開。 |
| INCOMPLETE_CLAIM検出率 | ~63% [observed: single environment, N undisclosed] | 著者環境での観測値。N数は公開版では非公開。 |
| 強制レビュー間隔 | 2時間 [observed: single environment] | 外部監視フックが外部から強制 |

**N数を非公開にする理由**: 運用頻度から内部システムの活動パターンが推定されるリスク。

**数値を引用する際のルール**: エビデンスラベルと観測スコープを必ず含めてください。

## 品質システム

| 指標 | 値 | 注記 |
|------|---|------|
| 品質システム層数 | 4+1層 [observed: single environment] | Layer 0（観測ゲート）〜Layer 4（第三者検証） |
| reason_code種別 | 30種類 [observed: single environment] | SKIP_SELF_DETECTED, POLL_SKIP_HOOK_BLOCKED 等 |
| 必須5セット | 5項目 [design target] | 前提条件、禁止事項、実行観測、合格基準、ロールバック |
| パターン昇格条件 | 同一reason_code 2回以上 [observed: single environment] | 3回以上で非公開データストアに記録し恒久対策 |

## トークン効率化

| 指標 | 値 | 注記 |
|------|---|------|
| コンテキスト常駐データ削減率 | 65%（設計値）[design target] | SQL外部化による |
| 理論上のトークン削減倍率 | 20x（設計値）[design target] | 委譲最適化+SQL外部化の組合せ。公開上は設計目標であり、公開再現ベンチマークではない。 |

**Before/After計測値を非公開にする理由**: 計画/利用データから個人環境が特定されるリスク。Phase2（将来の公開フェーズ）で開示予定。

## 3層分離

| 指標 | 値 | 注記 |
|------|---|------|
| 監督層 | 初代CC | 判断、レビュー、痛みの伝達 |
| 中継層 | 補助AI（Ollama等） | 定型監視。判断はゼロ |
| 作業層 | 現行CC | 実装、修正、タスク実行 |
| ローカル合意モデル数 | 5台 [observed: single environment] | 構造的検証用 |
| 助手フォロー項目 | 117件のフォロー指令 [observed: single environment] | この117件の指令から98 [observed: single environment] 件のL1パターン+206 [observed: single environment] 件のナレッジエントリ（計304件 [observed: single environment] の派生項目）を自動蓄積 |

---

## 公開/非公開の境界設計

| 公開しているもの | 理由 |
|----------------|------|
| FM数と分類体系 | 構造は見えるが再現鍵ではない |
| CC世代数と稼働時間 | 同上 |
| 検知パターン名と検出率 | アプローチの有効性が見えるが実装は見えない |
| reason_codeリスト | 品質設計の考え方が見える |
| 設計値（65%削減, 20x等） | 理論上の期待値であり実測値ではない |

| 非公開のもの | 理由 |
|-------------|------|
| PostgreSQLテーブルスキーマ詳細 | 再現鍵 |
| 外部監視フック検知ロジック | 再現鍵 |
| 検出率のN数 | 運用頻度から内部構造が推定される |
| トークン計測値 | 個人環境特定リスク |
| 外部監視フック実コンテンツ | 再現鍵 |
| cc_heritage文書全文 | 非公開コンテンツ |

---

[English version](../../20-proof/metrics.md)


---

→ [READMEに戻る](../README-ja.md)
---
*この文書は [SHI-Claude-Control-OS](https://github.com/naoyukioyama561-alt/SHI-Claude-Control-OS) プロジェクトの一部です。*
