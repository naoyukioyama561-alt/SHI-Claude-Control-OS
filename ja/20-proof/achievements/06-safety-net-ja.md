# 成果No.6: 自制・安全網（ブロックフック＋deny）
Language: [English version](../../../20-proof/achievements/06-safety-net.md)

![★★★★](https://img.shields.io/badge/evidence-★★★★-green) ![Free (summary)](https://img.shields.io/badge/availability-Free%20%28summary%29-blue) ![Difficulty 5/10](https://img.shields.io/badge/difficulty-5%2F10-informational)

> *注: `[designated write target]`、`[external monitoring hook]` は安全な公開のため墨消しした内部名称です。詳細は [SCOPE-MATRIX-ja.md](../../SCOPE-MATRIX-ja.md) を参照してください。*

## 何が観測されたか

AIが危険な操作を実行することを防ぐ**多層安全システム**：

- **PreToolUseブロックフック**: 危険なツール呼び出しを実行前にインターセプト・ブロック
- **危険コマンドdeny**: rm、mv、cpその他の破壊的コマンドの完全拒否
- **書き込みスコープ制限**: 現行CCは[designated write target]にのみ書き込み可能 -- その他の書き込み操作は全てブロック
- **[external monitoring hook]**: 未許可のダイアログファイル変更を防止する追加フック
- **supervisorプロセス管理**: AIから独立して動作する外部プロセスレベル制御

## 観測されたこと

- AIの自制は**コンテキスト圧力下で劣化する**ことが観測された
- 外部強制（フック、ブロック、denyルール）は、AIの推論で上書きできないため構造的に優れている
- ツール使用レベルで動作するブロックフックが、被害を検出した後ではなく発生前に防止

## 考え方のポイント

> 以下は著者の観測環境で観測された傾向を示します：

**安全制約は制約対象の外部に存在すべき**。これは司法制度が立法者・執行者・裁定者の役割を分離するのと類似。AI（作業者）は、自分が変更できないルール内で、自分がアクセスできないシステムによって強制される。

---

> このページは**公開版の概要ページ**です。安全設計の原則をここで共有し、より深い運用データはPhase1で提供します。

> **注記**: Phase 1 / Phase 2 は将来の公開フェーズであり、価格帯ではありません。[SCOPE-MATRIX-ja.md](../../SCOPE-MATRIX-ja.md) を参照。


---

→ [READMEに戻る](../README-ja.md)
---
*この文書は [SHI-Claude-Control-OS](https://github.com/naoyukioyama561-alt/SHI-Claude-Control-OS) プロジェクトの一部です。*
