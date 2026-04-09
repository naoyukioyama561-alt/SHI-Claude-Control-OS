# 10-framework/ — AI統治の構造的条件（日本語版）
Language: [English version](../../10-framework/README.md)

## 読む前に

[30-adoption/try/](../../30-adoption/try/) はもう試しましたか？
まだなら先に試してください。体感なしに読んでも「読んだ」で止まります。

> 「読んだ」と「理解した」と「身についた」は別物。
> — 成果No.12 師弟レビュー機構より

## 読む順番と検証ゲート

各ステップに**検証ゲート**があります。
ゲートの問いに自分の言葉で答えられなければ、理解していません。読み直してください。

---

### ステップ1: 失敗傾向の分類（Failure Modes）

[01-failure-modes-ja.md](01-failure-modes-ja.md) | [en版](../../10-framework/01-failure-modes.md)

AIが「こういう失敗をする」40パターンの体系的分類。
Claude、GPT、Copilotそれぞれの影響度付き。

**検証ゲート**:
- [ ] あなたのAIで最も頻繁に発火するFMを3つ、番号で言えるか
- [ ] その3つが発火する条件を、自分の作業に当てはめて説明できるか
- [ ] try/ で制御OSを貼った後、その3つが抑制されたか観測したか

---

### ステップ2: 制御OS（Control OS）

[02-control-os-ja.md](02-control-os-ja.md) | [en版](../../10-framework/02-control-os.md)

失敗傾向を発火させないための運用規約。
制御ループ（契約→実行→検証→ログ→更新）が核心。

**検証ゲート**:
- [ ] 制御ループの5ステップを、自分の作業に当てはめて説明できるか
- [ ] 「ハード禁止」の中で、自分のAIが最もよく違反するものはどれか
- [ ] 今日のシステムプロンプトに、何を1行追加するか

---

### ステップ3: 実例ログ形式

[03-incident-ledger-ja.md](03-incident-ledger-ja.md) | [en版](../../10-framework/03-incident-ledger.md)

失敗を「共有できる学習単位」として蓄積する台帳の形式。

**検証ゲート**:
- [ ] 自分のAIで最近起きた失敗を、この形式で1件書けるか
- [ ] その1件のFM番号を特定し、制御OSのどのルールで防げたか言えるか

---

### ステップ4: 3層分離

[04-three-layer-ja.md](04-three-layer-ja.md) | [en版](../../10-framework/04-three-layer.md)

監督・中継・作業 — 負荷を「量」ではなく「種類」で分離する構造。

**検証ゲート**:
- [ ] 「負荷の種類で分ける」と「負荷の量を減らす」の違いを説明できるか
- [ ] 自分の環境で3層のうちどの層が欠けているか特定できるか
- [ ] 「監視AIは被監視AIと別でなければならない」理由を説明できるか

---

### ステップ5: 品質システム

[05-quality-system-ja.md](05-quality-system-ja.md) | [en版](../../10-framework/05-quality-system.md)

4+1層アーキテクチャ、reason_code体系、必須5セット。

**検証ゲート**:
- [ ] 5セットを自分の直近タスクに適用して書けるか
- [ ] reason_codeのうち、自分のAIで最もよく発生するものはどれか
- [ ] 4+1層のうち、自分の環境に存在しない層はどれか

---

### ステップ6: 研究比較マップ

[06-research-comparison-ja.md](06-research-comparison-ja.md) | [en版](../../10-framework/06-research-comparison.md)

本アプローチが2026年の研究・商用レベルとどう比較されるか。

**検証ゲート**:
- [ ] 研究コミュニティの未解決問題のうち、自分のセットアップが対応しているのはどれか
- [ ] 自分のセットアップが最も弱い領域はどこか

---

### ステップ7: SHI理論引用集

[07-shi-citations-ja.md](07-shi-citations-ja.md) | [en版](../../10-framework/07-shi-citations.md)

本フレームワークの基盤となるSHI理論論文からの主要引用。

**検証ゲート**:
- [ ] SHI理論の命題P1-P3とリポジトリ構造の関係を説明できるか

---

## 全ステップ完了後

→ **Next**: [20-proof/](../../20-proof/) — 実証データを確認する

→ See also: [40-heritage/](../../40-heritage/) — AI人格継承の構造を理解する | [30-adoption/try/](../../30-adoption/try/) — 自分のAIに制御ループを回す


---

→ [READMEに戻る](../README-ja.md)
---
*この文書は [SHI-Claude-Control-OS](https://github.com/naoyukioyama561-alt/SHI-Claude-Control-OS) プロジェクトの一部です。*
