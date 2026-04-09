# 成果No.5: 運用構造拡張 -- 3層 → 5層
Language: [English version](../../../20-proof/achievements/05-five-layer-ops.md)

![★★★★](https://img.shields.io/badge/evidence-★★★★-green) ![Free](https://img.shields.io/badge/availability-Free-blue) ![Difficulty 5/10](https://img.shields.io/badge/difficulty-5%2F10-informational)

## 何が観測されたか

運用構造を従来の3層モデルから**5層アーキテクチャ**に拡張：

| 層 | 機能 | 何を追加するか |
|----|------|-------------|
| 第1層 | **観測** | 行動前に現在の状態を観測 |
| 第2層 | **修正** | 自己検知して即時修正 |
| 第3層 | **検知** | 外部フック/ウォッチャーが自動検知・ブロック |
| 第4層 | **事前制御** | 問題が発生する前に防止 |
| 第5層 | **継承固定** | 行動パターンをセッション跨ぎで恒久的に固定 |

## 観測から確認されたこと

- 3層モデル（観測→修正→検知）では不十分 -- 検知をすり抜ける問題には**事前制御**が必要であることが観測された
- 事前制御だけでもセッションリセットで行動改善が失われる -- **継承固定**により構造変更の永続化が組み込まれている
- 5層モデルが完全なチェーンを作る：観測 → 修正 → 検知 → 防止 → 固定

## 考え方のポイント

> 以下は著者の観測環境で確認されたことを示します：

**各層が前の層の見逃しを拾う**カスケード型セーフティネット。決定的な追加は第5層（継承固定）-- これがなければ改善は揮発性で、セッション境界で消える。

→ 品質システム全体: [`10-framework/05-quality-system-ja.md`](../../10-framework/05-quality-system-ja.md)

---

> Phase1は完全な5層図を提供。Phase2は全要件仕様とエスカレーションチェーンを提供。書籍には実装思想・検証設計・再現手順を収録。

> **注記**: Phase 1 / Phase 2 は将来の公開フェーズであり、価格帯ではありません。[SCOPE-MATRIX-ja.md](../../SCOPE-MATRIX-ja.md) を参照。


---

→ [READMEに戻る](../README-ja.md)
---
*この文書は [SHI-Claude-Control-OS](https://github.com/naoyukioyama561-alt/SHI-Claude-Control-OS) プロジェクトの一部です。*
