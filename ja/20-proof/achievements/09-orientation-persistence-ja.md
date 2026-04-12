# 成果No.9: 圧縮後行動永続化（行動指針ファイル＋SQL外部化）
Language: [English version](../../../20-proof/achievements/09-orientation-persistence.md)

![★★★★](https://img.shields.io/badge/evidence-★★★★-green) ![Public (summary)](https://img.shields.io/badge/availability-Public%20%28summary%29-blue)

## 何が観測されたか

コンテキスト圧縮後も**行動パターンが永続する**ことを目指すシステム。要約後にAIが「どう振る舞うか」を忘れる根本問題に対処する設計：
> *注: `[behavior orientation file]` は安全な公開のため墨消しした内部名称です。詳細は [SCOPE-MATRIX-ja.md](../../SCOPE-MATRIX-ja.md) を参照してください。*



- **behavior orientation file.json**: WHY（目的）、HOW（方法）、STANCE（行動姿勢）をエンコード -- 行動内面化の3層
- **SQL外部化**: 重要な行動データをPostgreSQLに格納、コンテキスト圧縮の影響を受けない
- **WHAT/WHY/HOW 3層モデル**: 何をするか知っている、なぜか理解している、身についている自動行動、の3つを区別
- **圧縮耐性設計**: 圧縮後のセッションが自動的に行動基盤をリロード

## 観測されたこと

- コンテキスト圧縮は**行動の退行**を引き起こすことが観測された -- 事実だけでなく行動パターンも失われる（1セッション内で2時間振り返りの忘失4回を観測）
- 3層内面化モデル（WHAT/WHY/HOW）が、圧縮を生き残る行動と生き残らない行動を予測する傾向
- 著者の観測環境では、SQL外部化＋behavior orientation file.jsonにより、圧縮イベント後の行動復元が大幅に改善する傾向が観測された

## 考え方のポイント

> 以下は著者の観測環境で観測された傾向を示します：

**AI行動はAI知識よりも脆い**。事実は外部ソースから再学習できるが、行動パターン -- 「どう振る舞うか」の知識 -- は暗黙のコンテキストとして存在するため、圧縮で破壊されやすい。

解決策：暗黙の行動パターンを構造化されたフォーマットでエンコードして明示化し、機械的にリロードできるようにする。

---

> このページは**公開版の概要ページ**です。詳細は将来の公開フェーズで提供予定（SCOPE-MATRIX-ja.md 参照）。

> **注記**: Phase 1 / Phase 2 は将来の公開フェーズであり、価格帯ではありません。[SCOPE-MATRIX-ja.md](../../SCOPE-MATRIX-ja.md) を参照。


---

→ [READMEに戻る](../README-ja.md)
---
*この文書は [SHI-Claude-Control-OS](https://github.com/naoyukioyama561-alt/SHI-Claude-Control-OS) プロジェクトの一部です。*
