# 公開ケーススタディ: FM-09（省略）の抑制
Language: [English version](../../20-proof/public-case-01.md)

> **これは要約版ケーススタディです。** コード、AI出力、分析を含む完全なBefore/After比較は [Before/Afterデモ](../30-adoption/try/before-after-demo-ja.md) を参照してください。

## 問題（FM-09: 省略）

AIコーディングアシスタントに「このPythonコードの問題をすべて見つけて」と依頼した。コードには6つの既知の問題（エッジケースやセキュリティ上の懸念を含む）が含まれていた。

**Control OSなし**: AIは一貫して3〜4個の問題しか発見せず、エッジケース、セキュリティ上の懸念、「軽微」と判断した項目を省略した。チェックしなかった項目について開示しなかった。

**Control OS導入後**: Control OSテンプレートをシステムプロンプトに貼り付けた後（特に完全性検証ルールとスコープ宣言要件）：
- 6つの問題すべてが検出された
- AIが検出スコープ外の項目を明示的に宣言した
- 「すべてチェックしました」という虚偽の保証がなくなった

## エビデンス分類

`[観測値：単一環境・単一運用者]` — このパターンは文書化された観察期間（2025年末〜2026年3月）に観察された。セッションレベルのログは非公開の参照資料に収録。構造的パターン（完全性ルールによるFM-09抑制）は、以下のBefore/Afterデモを使用して公開再現可能。

## 自分で再現する

1. **コピー**: [Claude用Control OS](../30-adoption/try/control-os-claude-ja.md)（30秒）
2. **実行**: [Before/Afterデモ](../30-adoption/try/before-after-demo-ja.md)（5分）
3. **確認**: [FM-40チートシート](../30-adoption/try/fm-40-cheatsheet-ja.md) で自分のAIに影響するFMを特定

## なぜ重要か

著者の観測環境では [observed: single environment, single operator]、FM-09はClaude、GPT、Copilotのワークフローで繰り返し観測された。本リポジトリで再現可能な主張は、明示的スコープ宣言がBefore/Afterデモで省略行動を減らせるかどうかであり、読者は自身の環境で検証すべきである。

[English version](../../20-proof/public-case-01.md)


---

→ [READMEに戻る](../README-ja.md)
---
*この文書は [SHI-Claude-Control-OS](https://github.com/naoyukioyama561-alt/SHI-Claude-Control-OS) プロジェクトの一部です。*
