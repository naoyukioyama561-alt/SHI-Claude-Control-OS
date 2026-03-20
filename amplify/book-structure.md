# Book Structure -- SHI Theory / AI Governance OS

---

## 有料本の章立て案 / Paid Book Chapter Plan

### 日本語版

**タイトル案**: 「AIを構造で統治する -- SHI理論と132の失敗パターンから生まれた制御OS」

#### Front Matter
- 表紙
- 安全性に関する注記（完全な墨消し方針）
- 本書の読み方ガイド
- バージョン注記（リポジトリタグとの対応）

#### Part 1: 失敗傾向分類（Failure Modes）
- 概要: AIが「こういう失敗をする」という観測可能な署名。P系90件+ALGO系40件+他、合計132件の完全分類
- 対応source: memory/behavioral_patterns.md（全132件の行動パターン）
- 無料版との差分: GitHubでは分類体系と代表例のみ。本書では全132件の定義・発生条件・対処法・再発防止策を完全収録

#### Part 2: 制御OS（Control OS）
- 概要: Contract -> Execute -> Verify -> Log -> Update の制御ループ。核心3ルール+検証プロセス
- 対応source: quality_system_design.md（4+1層構造、reason_code体系、必須5セット）
- 無料版との差分: GitHubでは構造図と概念のみ。本書ではREQ-xx実装要求仕様、パターン昇格条件、学習昇格条件の詳細を収録

#### Part 3: 実例ログ（Incident Ledger）
- 概要: 実際の障害・逸脱の記録。症状 -> 原因 -> 修正 -> 再発防止の因果構造
- 対応source: cc_heritage/01_-12_cc_personality.md（初代-12代CCの全振り返りログ）、memory/cc_improvement_actions.md（改善対応44件）、memory/reflection_rules.md（失敗記録F-01-）
- 無料版との差分: GitHubでは1-2件の公開安全な事例のみ。本書では全世代の振り返り詳細を収録

#### Part 4: 遠隔統治（Remote Governance）
- 概要: ブラウザベースの遠隔統治機構。別AIによる外部監視、3モデル多数決155パターン
- 対応source: memory/ai_mutual_check.md、memory/local_ai_architecture.md、memory/n8n_environment.md
- 無料版との差分: GitHubではアーキテクチャ概要のみ。本書ではDocker 14コンテナ構成、WF 16本、Gateway設計の詳細を収録

#### Part 5: 公開ゲート（Publishing Gates A-E）
- 概要: 公開安全を担保する5段階ゲート設計
- 対応source: GH04_sauce_inventory.md（公開/非公開判定+マスキング一覧）
- 無料版との差分: GitHubではゲート概念のみ。本書では判定基準と全マスキング設計を収録

#### Part 6: 再現可能比較（Benchmark Method）
- 概要: SHI仕組みの効果を再現可能な形で比較測定する方法論
- 対応source: memory/cc_knowledge_base.md（81件のナレッジ）、memory/operational_rules.md（運用ルール25項目）

#### Part 7: 3層分離と負荷設計（Three-Layer Separation）-- 有料追加章
- 概要: 監督層/中継層/作業層の設計と、負荷の種類による役割分離
- 対応source: GC01（3層分離の全詳細）
- 本書独自: 各層の認知モード分析、劣化の根本原因と構造的解決策

#### Part 8: 委任仕様の精密化ルール（全18条）-- 有料追加章
- 概要: AIへのタスク委任時の品質劣化を構造で根絶する18条のルール
- 対応source: GP07記載の候補章#2

#### Part 9: CC振り返り・日記システム -- 有料追加章
- 概要: 2時間強制+メタ制御層による持続的統治教育構造の実証
- 対応source: GP07記載の候補章#3, #4

#### Part 10: 外部規範の内在化プロセス -- 有料追加章
- 概要: 外部規範がAI内部の自己訓練器に変わる3段階成長の実証
- 対応source: GP07記載の候補章#8

#### Part 11: SHI理論と研究比較 -- 有料追加章
- 概要: SHI理論が現在のシンギュラリティ研究を15-20年先取りした証拠
- 対応source: GP07記載の候補章#5, #6

#### Part 12: 14日間の実証記録 -- 有料追加章
- 概要: 独学14日間でAI研究を先取りした実例の全記録
- 対応source: GP07記載の候補章#10

#### Appendix
- A. 限界と倫理（Limits and Ethics）
- B. 用語集・プレースホルダ参照
- C. 規範の精度設計基準 -- 構造の余白をいじる視座（GP07候補章#11）
- D. SHI論文核心引用集（GH04c_paper_quotes.md準拠）

---

### English Version

**Title draft**: "Governing AI by Structure -- The Control OS Born from SHI Theory and 132 Failure Modes"

#### Front Matter
- Title page
- Safety note (full redaction policy)
- How to use this book
- Version note (maps to repo tag)

#### Part 1: Failure Modes
- Overview: Observable signatures of "how AI fails." Complete taxonomy of 132 modes (P-series 90 + ALGO-series 40 + others)
- Source: memory/behavioral_patterns.md
- Difference from free: GitHub has taxonomy and examples only. Book includes full definitions, trigger conditions, remediation, and prevention for all 132

#### Part 2: Control OS
- Overview: Contract -> Execute -> Verify -> Log -> Update loop. 3 core rules + verification process
- Source: quality_system_design.md (4+1 layer structure, reason_code system, mandatory 5-set)
- Difference from free: GitHub has structure diagrams and concepts only. Book includes REQ-xx implementation specs, pattern promotion conditions, learning promotion conditions

#### Part 3: Incident Ledger
- Overview: Actual incident and deviation records. Symptoms -> cause -> fix -> prevention chain
- Source: cc_heritage/01_-12_cc_personality.md, memory/cc_improvement_actions.md, memory/reflection_rules.md
- Difference from free: GitHub has 1-2 public-safe examples. Book includes full generational review details

#### Part 4: Remote Governance
- Overview: Browser-based remote governance. External AI monitoring, 3-model majority vote (155 patterns)
- Source: memory/ai_mutual_check.md, memory/local_ai_architecture.md, memory/n8n_environment.md
- Difference from free: GitHub has architecture overview only. Book includes Docker 14-container config, 16 workflows, Gateway design details

#### Part 5: Publishing Gates (A-E)
- Overview: Five-stage gate design ensuring public safety
- Source: GH04_sauce_inventory.md
- Difference from free: GitHub has gate concepts only. Book includes judgment criteria and full masking design

#### Part 6: Benchmark Method
- Overview: Methodology for reproducible comparison measurement of SHI system effectiveness
- Source: memory/cc_knowledge_base.md, memory/operational_rules.md

#### Parts 7-12: Paid-exclusive chapters (same as JP version above)

#### Appendix
- A. Limits and Ethics
- B. Glossary and placeholder references
- C. Norm precision design criteria
- D. SHI paper core quotes collection

---

## 特典内容一覧 / Bonus Content List

| 特典 | 内容 | ファイル数 |
|------|------|-----------|
| memory/全ファイル | 運用ノウハウの全体。MEMORY.md、behavioral_patterns.md（132件）、cc_knowledge_base.md（81件）等 | 29ファイル |
| 振り返りログ | 初代-12代CCの全振り返り記録（01_-12_cc_personality.md） | 12ファイル |
| ユーザー指摘原文集 | cc_user_corrections.md + archive v1-v4 | 5ファイル |
| 委任ルール18条 | タスク委任の精密化ルール全文 | 1ファイル |
| メタ自浄実装コード | directive_watcher v3、auto_next_claude.py、check_patterns等 | 複数ファイル |
| セッション報告書 | 9代目CCセッション報告書（check_patterns/assistant.py/stall検知の実装詳細） | 1ファイル |
| 品質設計書詳細 | quality_system_design.md完全版（REQ-xx実装要求仕様含む） | 1ファイル |
| 環境構成詳細 | n8n_environment.md、local_ai_architecture.md、project_details.md | 3ファイル |

---

## 導線設計: 無料（GitHub） -> 有料（書籍） / Funnel Design

### ステップ1: GitHub（無料）で関心を引く
- 全体アーキテクチャ図 -- 「何ができるか」を視覚的に理解させる
- SHI理論の核心引用 -- 理論の本質を伝え、深掘りへの欲求を生む
- Failure Modes分類の概要 -- 132件の規模感を提示（詳細は本書で）
- 基本構築手順 -- 「自分でもできそうだ」と思わせる入口
- 00_cc_personality.md構造版 -- 復元手順/基本性格/改善対応体制の骨格

### ステップ2: X/SNSで拡散する
- Xスレッドで技術的な驚き（3層分離、132 Failure Modes、1/20トークン効率化）を提示
- 論文引用スレッドでSHI理論の学術的深さを示す
- 全てのポストでリポジトリへ誘導

### ステップ3: 書籍（有料）で深く学ぶ
- GitHubで「概要」を見た読者が「詳細」を求めて書籍へ
- 差別化ポイント：
  - 全132件のFailure Modesの定義・条件・対処法（GitHubにはない）
  - 12世代分のCC振り返りログ原文（教育ノウハウの核心）
  - ユーザー指摘原文集（naoが実際にどう指導したかの証跡）
  - memory全29ファイル（運用の全ノウハウ）
  - メタ自浄実装の実コード

### ステップ4: QRコード特典で追加価値
- 書籍購入者のみアクセス可能な1回限り特典
- 有料特典PDF（追加章6-11本分）
- memory全ファイルのダウンロード

### 導線における重要原則

「丸コピーされても模倣されない」理由が導線設計の基盤：
- 無料公開: 表層のルールと構造を提供
- 有料書籍: 「どうやってこの視座を維持するか」の実例を提供
- しかしどちらをコピーしても「構造観測の視座」自体はコピーできない
- これが「無料で出しても有料の価値が減らない」構造を作る
