# 成果No.3: 外部監視・メタ統治

![★★★★](https://img.shields.io/badge/evidence-★★★★-green) ![Free](https://img.shields.io/badge/availability-Free-blue) ![Difficulty 5/10](https://img.shields.io/badge/difficulty-5%2F10-informational)

## 何が観測されたか

AIの自己申告に依存しない**完全な外部監視・メタ統治システム**：

- **[infrastructure health monitor]**: 監視対象AIから独立したインフラレベル監視
- **[external monitoring hook]**: 別AIインスタンスによるAIレベル行動監視
- **Gemini外部監視**: 構造的に異なるAIによるクロスモデル検証
- **規範強制**: ルールは自己遵守ではなく外部から強制

## 観測から確認されたこと

- **自己監視は根本的に失敗しやすい** -- エラーを起こすのと同じアルゴリズム傾向が、エラー検知の盲点も作る
- 著者の単一観測環境に限れば、構造的に分離した監視は自己申告のみより高い検知を示した：
  - EVIDENCE_DROPOUT: ~100% [単一環境、N未公開]
  - GENERIC_RESPONSE: 75% [単一環境、N未公開]
  - INCOMPLETE_CLAIM: 63% [単一環境、N未公開]
- 3層分離（監督・中継・作業）により、負荷を**量**ではなく**種類**で分けることで監視を持続可能にした

## 考え方のポイント

設計上の核心原則：**このフレームワークでは、構造的に分離した監視者を使うことで検知が改善された**。監視を増やすことではなく、監視者が被監視プロセスと**異なるアルゴリズム的盲点**を持つことが重要。

品質保証に自己申告を頼るAIシステムには、構造的な盲点がある可能性がある。

→ 詳細ドキュメント: [`10-framework/ja/04-three-layer.md`](../../../10-framework/ja/04-three-layer.md)

---

> Phase1は完全な役割表を提供。Phase2は[external monitoring hook]コード抜粋とブロックフック実装を提供。書籍には理論整理・検証設計・再現手順を収録。

> **注記**: Phase 1 / Phase 2 は将来の公開フェーズであり、価格帯ではありません。[SCOPE-MATRIX-ja.md](../../../SCOPE-MATRIX-ja.md) を参照。
