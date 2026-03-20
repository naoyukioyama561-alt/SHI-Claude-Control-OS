# 成果No.6: 圧縮後行動永続化（cc_orientation＋SQL外部化）

## 何を達成したか

コンテキスト圧縮後も**行動パターンが永続する**システム。要約後にAIが「どう振る舞うか」を忘れる根本問題を解決：

- **cc_orientation.json**: WHY（目的）、HOW（方法）、STANCE（行動姿勢）をエンコード — 行動内面化の3層
- **SQL外部化**: 重要な行動データをPostgreSQLに格納、コンテキスト圧縮の影響を受けない
- **WHAT/WHY/HOW 3層モデル**: 何をするか知っている、なぜか理解している、身についている自動行動、の3つを区別
- **圧縮耐性設計**: 圧縮後のセッションが自動的に行動基盤をリロード

## 何が実証されたか

- コンテキスト圧縮は**行動の退行**を引き起こす — 事実だけでなく行動パターンも失われる（実証：1セッション内で2時間振り返りの忘失4回）
- 3層内面化モデル（WHAT/WHY/HOW）が、圧縮を生き残る行動と生き残らない行動を正確に予測
- SQL外部化＋cc_orientation.jsonにより、圧縮イベント後の**ほぼ完全な行動復元**を達成

## 実証画像

| 画像 | 説明 |
|------|------|
| ![圧縮後手順](../../images/06-compression-persistence/IMG_014.png) | コンテキスト圧縮後の手順実装（CLAUDE.mdへ追加） |
| ![3層モデル](../../images/06-compression-persistence/IMG_057.png) | 構造的解決3件＋行動の内在化3層（WHAT/WHY/HOW） |
| ![orientation設計](../../images/06-compression-persistence/IMG_058.png) | 3層詳細＋cc_orientation内部設計 |
| ![圧縮分析](../../images/06-compression-persistence/IMG_108.png) | 「コンテキスト要約が起きても平気か」分析（外部化済み vs 未対応） |
| ![繰り返し失敗](../../images/06-compression-persistence/IMG_116.png) | 圧縮後の繰り返し失敗（2時間振り返り忘失4回等）の詳細 |
| ![SQL＋永続化](../../images/06-compression-persistence/IMG_109.png) | SQLクエリエラー＋行動永続化の設計議論 |
| ![orientation更新](../../images/06-compression-persistence/IMG_101.png) | memoryファイル更新＋orientation.json更新のdiff |
| ![リスク判断](../../images/06-compression-persistence/IMG_093.png) | コンテキスト圧縮+横断調査のリスク判断（/clearして再開を選択） |

## 考え方のポイント

根本的な洞察：**AI行動はAI知識よりも脆い**。事実は外部ソースから再学習できるが、行動パターン — 「どう振る舞うか」の知識 — は暗黙のコンテキストとして存在するため、圧縮で破壊される。

解決策：暗黙の行動パターンを構造化されたフォーマット（cc_orientation.json）でエンコードして明示化し、AIが行動姿勢を「再学習」する必要なく機械的にリロードできるようにする。

---

> これは**有料版の成果**（Phase1）です。考え方の方法論と3層モデルをここで共有しています。cc_orientation.jsonスキーマ、SQL外部化の詳細、圧縮復旧手順は有料版で提供。
>
> Phase1は設計詳細と復旧手順を提供。Phase2は構造観測の方法論を含む完全実装を提供。書籍には繰り返し失敗から現在の堅牢なシステムまでの完全な進化過程付き。
