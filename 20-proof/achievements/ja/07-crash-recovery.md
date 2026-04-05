# 成果No.7: クラッシュ対策 -- 自動検知＋3レベル復元

![★★★★](https://img.shields.io/badge/evidence-★★★★-green) ![Free (summary)](https://img.shields.io/badge/availability-Free%20%28summary%29-blue) ![Difficulty 5/10](https://img.shields.io/badge/difficulty-5%2F10-informational)

## 何が観測されたか

Claude Codeのクラッシュ時に作業が失われないことを保証する**クラッシュ自動検知＋3レベル即時復元システム**：

- **Level 1 -- [recovery checkpoint file]**: クラッシュ前の本質的な状態をキャプチャする軽量ファイルベース復旧
- **Level 2 -- [behavior orientation file]**: 運用コンテキストを復元する次セッション自動ブートストラップ
- **Level 3 -- [infrastructure health monitor]**: クラッシュを独立して検知し復旧をトリガーするインフラレベル監視

## 観測から確認されたこと

- Claude Codeのクラッシュは**稀なエッジケースではない** -- 通常の運用上の現実（3.8MB超のJSONLファイル、コンテキスト圧力、メモリ枯渇）
- 構造化されたクラッシュ復旧がなければ、クラッシュ後のセッションはゼロからスタートし、蓄積されたコンテキストと進行中の作業が数時間分失われることが観測された
- 3レベルアプローチにより個別レベルが失敗しても復旧を保証：[recovery checkpoint file]が破損しても[behavior orientation file]が機能し、両方失敗しても[infrastructure health monitor]が外部から捕捉

## 考え方のポイント

重要な気づき：**クラッシュ復旧とはクラッシュを防ぐことではなく、クラッシュを生存可能にすること**。長時間稼働のAI運用では、クラッシュは起きうる。問題は、中断地点から再開できるか、ゼロからやり直さなければならないか。

3レベル設計は多層防御の原則に従う：各レベルが独立しているため、単一障害点で復旧が妨げられない。

---

> このページは**公開版の概要ページ**です。考え方の方法論をここで共有し、クラッシュ検知スクリプト、復旧フロー実装、外部監視連携の詳細はPhase1で提供します。
