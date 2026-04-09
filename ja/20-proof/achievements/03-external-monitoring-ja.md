# 成果No.3: 外部監視・メタ統治
Language: [English version](../../../20-proof/achievements/03-external-monitoring.md)

![★★★★](https://img.shields.io/badge/evidence-★★★★-green) ![Free](https://img.shields.io/badge/availability-Free-blue) ![Difficulty 5/10](https://img.shields.io/badge/difficulty-5%2F10-informational)

## 何が観測されたか

AIの自己申告に依存しない**完全な外部監視・メタ統治システム**：

*注: `[external monitoring hook]`、`[internal database table]` 等は安全な公開のため墨消し済み。スコープ詳細は [SCOPE-MATRIX-ja.md](../../SCOPE-MATRIX-ja.md) を参照。*

- **[infrastructure health monitor]**: 監視対象AIから独立したインフラレベル監視
- **[external monitoring hook]**: 別AIインスタンスによるAIレベル行動監視
- **Gemini外部監視**: 構造的に異なるAIによるクロスモデル検証
- **規範強制**: ルールは自己遵守ではなく外部から強制

## 観測から確認されたこと

- **著者の観測環境では、自己監視だけでは見落としが生じやすかった** -- エラーを起こすのと同じアルゴリズム傾向が、エラー検知の盲点も作る傾向が観測された
- 著者の単一観測環境に限れば、構造的に分離した監視は自己申告のみより高い検知を示した：
  - EVIDENCE_DROPOUT: ~100% [observed: 単一環境, N未公開]
  - GENERIC_RESPONSE: ~75% [observed: 単一環境, N未公開]
  - INCOMPLETE_CLAIM: ~63% [observed: 単一環境, N未公開]
- 3層分離（監督・中継・作業）により、負荷を**量**ではなく**種類**で分けることで監視を持続可能にした

## 考え方のポイント

設計上の核心原則：**著者の観測環境では、構造的に分離した監視者を使うことで検知が改善された**。監視を増やすことではなく、監視者が被監視プロセスと**異なるアルゴリズム的盲点**を持つことが重要。

品質保証に自己申告を頼るAIシステムには、構造的な盲点がある可能性がある。

→ 詳細ドキュメント: [`10-framework/04-three-layer-ja.md`](../../10-framework/04-three-layer-ja.md)

---

> Phase1は完全な役割表を提供。Phase2は[external monitoring hook]コード抜粋とブロックフック実装を提供。書籍には理論整理・検証設計・再現手順を収録。

> **注記**: Phase 1 / Phase 2 は将来の公開フェーズであり、価格帯ではありません。[SCOPE-MATRIX-ja.md](../../SCOPE-MATRIX-ja.md) を参照。


---

→ [READMEに戻る](../README-ja.md)
---
*この文書は [SHI-Claude-Control-OS](https://github.com/naoyukioyama561-alt/SHI-Claude-Control-OS) プロジェクトの一部です。*
