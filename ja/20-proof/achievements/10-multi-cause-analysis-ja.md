# 成果No.10: 複合要因自動解析（なぜなぜ5段＋非公開インシデント蓄積基盤）
Language: [English version](../../../20-proof/achievements/10-multi-cause-analysis.md)

![★★★](https://img.shields.io/badge/evidence-★★★-yellow) ![Free (summary)](https://img.shields.io/badge/availability-Free%20%28summary%29-blue) ![Difficulty 6/10](https://img.shields.io/badge/difficulty-6%2F10-informational)

単発のデバッグでは見えにくい構造的パターンがあります。著者の環境では、複合要因分析により一回限りのレビューでは表面化しなかったパターンが検出されました。

> *注: `[internal database table]` は安全な公開のため墨消しした内部名称です。詳細は [SCOPE-MATRIX-ja.md](../../SCOPE-MATRIX-ja.md) を参照してください。*

## 何が観測されたか

複数の方法論を組み合わせた**構造化された根本原因分析システム**：

- **なぜなぜ5段分析**: 表面的な症状から構造的な原因まで体系的に掘り下げ
- **前任CC参照**: インシデント分析時に初代CCの蓄積経験を自動参照
- **[internal database table]自動蓄積**: 分析した全インシデントを将来の参照用に構造的に保存
- **自己反省の自動化**: 「知っている」と「できている」のギャップを体系的に特定・対処

## 観測から確認されたこと

- AIの失敗分析は通常、表面的な症状で止まる傾向が観測された
- なぜなぜ手法と前任CC知識の組み合わせが、単一セッション分析では検知しにくい**複合要因**を明らかにする
- 自己評価が重要なギャップを露呈：「ルールを知っている」と「一貫してルールに従う」の差（5つの評価軸で検証）
- インシデント知識の自動蓄積が**組織的記憶**を作り、分析品質が時間とともに向上する傾向が見られた

## 考え方のポイント

> 以下は著者の観測環境で確認されたことを示します：

最も重要な発見：**AIは自身の行動パターンを特定できるが、気づきだけでは修正しにくい**。失敗パターンについて知っていても再発は防げない場合がある -- 構造的介入（フック、ブロック、外部監視）が有用。

---

> このページは**公開版の概要ページ**です。分析方法論と考え方のフレームワークをここで共有し、自動化実装の詳細はPhase1で提供します。

> **注記**: Phase 1 / Phase 2 は将来の公開フェーズであり、価格帯ではありません。[SCOPE-MATRIX-ja.md](../../SCOPE-MATRIX-ja.md) を参照。


---

→ [READMEに戻る](../README-ja.md)
---
*この文書は [SHI-Claude-Control-OS](https://github.com/naoyukioyama561-alt/SHI-Claude-Control-OS) プロジェクトの一部です。*
