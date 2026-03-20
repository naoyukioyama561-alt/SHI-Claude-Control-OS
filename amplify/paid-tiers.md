# Paid Tiers Design -- SHI Theory / AI Governance OS

---

## 有料特典の段階設計 / Paid Bonus Tier Design

### Tier 1: Kindle版 / 電子書籍版（基本）

**価格帯**: 後日決定
**形式**: Kindle (mobi/KFX) / EPUB

**含まれるもの**:

| 内容 | 詳細 |
|------|------|
| Part 1: Failure Modes完全版 | 132件全ての定義・発生条件・対処法・再発防止策 |
| Part 2: Control OS詳細 | REQ-xx実装要求仕様、パターン昇格条件、学習昇格条件 |
| Part 3: Incident Ledger | 複数世代の振り返り事例（代表的なもの） |
| Part 4: Remote Governance | アーキテクチャ詳細、Docker構成概要、WF設計 |
| Part 5: Publishing Gates | 5段階ゲート判定基準 |
| Part 6: Benchmark Method | 再現可能比較の方法論 |
| Appendix | 限界と倫理、用語集、SHI論文核心引用 |

**含まれないもの（Tier 2以降）**:
- memory/全ファイルのダウンロード
- 振り返りログ原文（01_-12_cc_personality.md）
- ユーザー指摘原文集
- メタ自浄実装コード
- 有料追加章（Part 7-12）

---

### Tier 2: QRコード1回限り特典（書籍購入者限定）

**提供方法**: 書籍内に印刷されたQRコードから1回限りアクセス
**形式**: ダウンロード可能なZIPファイル（PDF + ファイル群）

**含まれるもの（Tier 1に加えて）**:

| 区分 | 内容 | ファイル数 |
|------|------|-----------|
| 有料追加章PDF | Part 7-12の全文 | 6章分 |
| memory全ファイル | 全29ファイル（マスキング済み） | 29 |
| 振り返りログ原文 | 01_-12_cc_personality.md（初代-12代CCの全世代記録） | 12 |
| ユーザー指摘原文集 | cc_user_corrections.md + archive v1-v4 | 5 |
| セッション報告書 | 9代目CCセッション報告書 | 1 |
| 品質設計書完全版 | quality_system_design.md（REQ-xx含む全657行） | 1 |

#### 有料追加章の詳細（QRコード特典PDF）

| 章 | タイトル | 概要 |
|----|---------|------|
| Part 7 | 3層分離と負荷設計 | 監督層/中継層/作業層の設計思想。各層の認知モード分析、劣化の構造的原因と解決策 |
| Part 8 | 委任仕様の精密化ルール（全18条） | AIへのタスク委任で品質劣化を防ぐ18条のルール全文と適用事例 |
| Part 9 | CC振り返り・日記システム | 2時間強制+メタ制御層。持続的統治教育構造の実証データ |
| Part 10 | 外部規範の内在化プロセス | 外部規範 -> AI内部の自己訓練器への変容を3段階で実証 |
| Part 11 | SHI理論と研究比較 | シンギュラリティ研究を15-20年先取りした証拠。比較表付き |
| Part 12 | 14日間の実証記録 | 独学14日間でAI研究を先取りした全プロセスの記録 |

---

## Kindle版/電子書籍版の違い / Format Differences

| 項目 | Kindle版 | EPUB版（汎用電子書籍） |
|------|----------|----------------------|
| 配信プラットフォーム | Amazon Kindle | 直接配布 or 他プラットフォーム |
| DRM | Kindle DRM適用 | DRMなし（or 独自保護） |
| QRコード特典 | 対応（書籍内にQR印刷） | 対応（書籍内にQR印刷） |
| フォーマット | mobi / KFX | EPUB |
| 日英対応 | 日本語版・英語版を別冊として提供 | 同上 |
| 図表の表示 | Kindle形式に最適化 | 汎用リーダー対応 |
| 本文内容 | 同一（Part 1-6 + Appendix） | 同一 |
| 価格 | 同一価格帯を想定 | 同一価格帯を想定 |

### 共通仕様

- 書籍本文はリポジトリタグ vX.Y.Z のスナップショットから生成
- Public-safe維持: 秘密情報・認証情報・内部IPは全てマスキング済み
- 結合原稿: dist/book/JA_MANUSCRIPT_<TAG>.md / dist/book/EN_MANUSCRIPT_<TAG>.md から生成
- 図表は assets/images/ 配下の公開安全版を使用

---

## QRコード1回限り特典の詳細設計 / QR Code One-Time Bonus Design

### 仕組み

1. 書籍内の指定ページにユニークなQRコードを印刷
2. QRコードはワンタイムURL（1回アクセスで無効化）にリンク
3. アクセス先でZIPファイルをダウンロード
4. ダウンロード完了後、URLは無効化される

### ZIPファイルの構成

```
shi-paid-bonus/
  README_BONUS.md          -- 特典の使い方ガイド
  chapters/
    part07_three_layer.md   -- Part 7: 3層分離と負荷設計
    part08_delegation.md    -- Part 8: 委任仕様18条
    part09_reflection.md    -- Part 9: 振り返り・日記システム
    part10_internalization.md -- Part 10: 外部規範の内在化
    part11_research_compare.md -- Part 11: SHI理論と研究比較
    part12_14days.md        -- Part 12: 14日間の実証記録
  memory/
    (全29ファイル、マスキング済み)
  cc_heritage/
    01_cc_personality.md - 12_cc_personality.md
    cc_user_corrections.md
    cc_user_corrections_archive_v1.md - v4.md
    session_report_9th_cc.md
  quality/
    quality_system_design_full.md  -- 完全版（657行）
```

### マスキング方針（特典ファイル）

特典として配布するファイルにも以下のマスキングを適用：

| 種別 | 出現箇所数 | 置換先 |
|------|-----------|--------|
| IPアドレス（192.168.x.x系） | 30+ | `<INTERNAL_IP>` |
| VMホスト名 | 10+ | `<VM_HOST>` |
| パスワード | 8 | `<PASSWORD>` |
| メールアドレス | 1 | `<EMAIL>` |
| プロジェクトパス | 15+ | `<PROJECT_DIR>` |
| ホームパス | 3 | `<HOME>` |
| APIキーファイルパス | 3 | `<API_KEY_FILE>` |
| ローカル管理者名 | 1 | `<LOCAL_ADMIN_USER>` |

### 不正コピー対策

- QRコードは1回限りの使い切り設計
- ダウンロードURLの有効期限設定（24時間以内）
- ZIPファイル内にユニークな識別子を埋め込み（トレーサビリティ用）

---

## 無料 -> 有料の段階整理 / Free to Paid Tier Summary

| 段階 | 入手方法 | 内容 |
|------|----------|------|
| 無料（GitHub） | リポジトリから直接 | 外観+再現可能な道筋。アーキテクチャ図、SHI理論核心、基本構築手順、FM分類概要、00_cc_personality構造版 |
| 有料Tier 1（書籍） | Kindle/EPUB購入 | Part 1-6完全版。132 FM全件、Control OS詳細、Incident Ledger複数事例、Remote Governance詳細、Gates判定基準、Benchmark方法論 |
| 有料Tier 2（QR特典） | 書籍内QRコードから1回限りダウンロード | Tier 1 + 追加章6本 + memory全29ファイル + 振り返りログ12ファイル + 指摘原文集5ファイル + 品質設計書完全版 |

### 各段階の差別化ポイント

**無料（GitHub）が提供するもの**: 「何が起きているか」の全体像
**有料Tier 1（書籍）が提供するもの**: 「どう実装するか」の詳細
**有料Tier 2（QR特典）が提供するもの**: 「どうやってこの視座を維持するか」の実例

この3段階は「丸コピーされても模倣されない」原則に基づく。無料で構造を公開しても、それを生み出した構造観測の視座はコピーできない。有料特典はその視座の維持方法（振り返りログ、メタ監視の実装、ユーザー指摘原文）を提供することで差別化する。
