# templates/ -- 自環境への導入キット

これらのテンプレートは、SHI Control OS の方法論を自身のAIワークフローに適用するためのものです。

## 利用可能なテンプレート

| テンプレート | 用途 | 使うタイミング |
|-------------|------|---------------|
| [verification-skip-checklist.md](verification-skip-checklist.md) | 検証スキップの防止 | AIが根拠なく「完了」と報告する場合 |
| [failure-naming-template.md](failure-naming-template.md) | AI障害の構造的な命名・分類 | 繰り返し発生するAI障害を観察し、追跡したい場合 |
| [three-layer-starter.md](three-layer-starter.md) | 三層ロール分離の開始 | 判断・監視・実行を分離したい場合 |
| [delegation-spec-template.md](delegation-spec-template.md) | 委任境界の仕様定義 | サブエージェントやヘルパーAIにタスクを委任する場合 |

## 使い方

1. テンプレートをプロジェクトにコピーする
2. 自環境に合わせて空欄を埋める
3. CLAUDE.md またはシステムプロンプトからテンプレートを参照する
4. 対象の障害モードが抑制されているか観察する

これらのテンプレートは単体で利用できるよう設計されています。本リポジトリの他のファイルは不要です。

---

> [30-adoption/](../../../README-ja.md) に戻る | [README](../../../README-ja.md)
