# 成果No.7: クラッシュ対策 -- 自動検知＋3レベル復元
Language: [English version](../../../20-proof/achievements/07-crash-recovery.md)

![★★★★](https://img.shields.io/badge/evidence-★★★★-green) ![Free (summary)](https://img.shields.io/badge/availability-Free%20%28summary%29-blue) ![Difficulty 5/10](https://img.shields.io/badge/difficulty-5%2F10-informational)

## 何が観測されたか

著者の環境で観測された、Claude Codeクラッシュ時の作業継続を支援する**クラッシュ自動検知＋3レベル復元設計**：

*注: `[recovery checkpoint file]`、`[behavior orientation file]` 等は安全な公開のため墨消し済み。スコープ詳細は [SCOPE-MATRIX-ja.md](../../SCOPE-MATRIX-ja.md) を参照。*

- **Level 1 -- [recovery checkpoint file]**: クラッシュ前の本質的な状態をキャプチャする軽量ファイルベース復旧
- **Level 2 -- [behavior orientation file]**: 運用コンテキストを復元する次セッション自動ブートストラップ
- **Level 3 -- [infrastructure health monitor]**: クラッシュを独立して検知し復旧をトリガーするインフラレベル監視

## 観測から確認されたこと

- Claude Codeのクラッシュは**稀なエッジケースではない** -- 通常の運用上の現実（3.8MB超のJSONLファイル、コンテキスト圧力、メモリ枯渇）
- 構造化されたクラッシュ復旧がなければ、クラッシュ後のセッションはゼロからスタートし、蓄積されたコンテキストと進行中の作業が数時間分失われることが観測された
- 3レベルアプローチは個別レベルが失敗しても復旧を可能にする設計：[recovery checkpoint file]が破損しても[behavior orientation file]が機能し、両方失敗しても[infrastructure health monitor]が外部から捕捉する設計

## 考え方のポイント

> 以下は著者の観測環境で確認されたことを示します：

重要な気づき：**クラッシュ復旧とはクラッシュを防ぐことではなく、クラッシュを生存可能にすること**。長時間稼働のAI運用では、クラッシュは起きうる。問題は、中断地点から再開できるか、ゼロからやり直さなければならないか。

3レベル設計は多層防御の原則に従う：各レベルが独立しているため、単一障害点で復旧が妨げられない。

---

> このページは**公開版の概要ページ**です。考え方の方法論をここで共有し、クラッシュ検知スクリプト、復旧フロー実装、外部監視連携の詳細はPhase1で提供します。

> **注記**: Phase 1 / Phase 2 は将来の公開フェーズであり、価格帯ではありません。[SCOPE-MATRIX-ja.md](../../SCOPE-MATRIX-ja.md) を参照。


---

→ [READMEに戻る](../README-ja.md)
---
*この文書は [SHI-Claude-Control-OS](https://github.com/naoyukioyama561-alt/SHI-Claude-Control-OS) プロジェクトの一部です。*
