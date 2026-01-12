# Section 6: Scale and Recovery 練習問題

このドキュメントでは、Section 6に関する練習問題を提供します。

## 問題1: Connection Serverのスケーリング

**問題形式**: 多肢選択問題

Connection Serverをスケーリングする際の正しい方法はどれですか？

- A) 新しいConnection ServerをStandaloneとしてインストール
- B) 新しいConnection ServerをReplicaとして追加
- C) 既存のConnection Serverをアップグレード
- D) 既存のConnection Serverを再インストール

<details>
<summary>解答と解説</summary>

**正解**: B) 新しいConnection ServerをReplicaとして追加

**解説**: 
- Connection Serverをスケーリングする際は、Replica Serverとして追加します
- ロードバランサーに追加して、負荷分散を設定します

</details>

---

## 問題2: CPAの初期化

**問題形式**: 多肢選択問題

Cloud Pod Architectureの初期化で設定する項目として正しいものはどれですか？

- A) フェデレーション名のみ
- B) フェデレーション名とグローバルLDAPインスタンス
- C) フェデレーション名とローカルLDAPインスタンス
- D) ローカルLDAPインスタンスのみ

<details>
<summary>解答と解説</summary>

**正解**: B) フェデレーション名とグローバルLDAPインスタンス

**解説**: 
- CPAの初期化では、フェデレーション名とグローバルLDAPインスタンスを設定します
- グローバルLDAPインスタンスは、フェデレーション全体で使用されます

</details>

---

## 問題3: Home Site戦略

**問題形式**: 多肢選択問題

Home Site戦略の実装方法として正しいものはどれですか？

- A) Horizon Consoleでのみ設定
- B) Imvutilコマンドでのみ設定
- C) Horizon ConsoleとImvutilコマンドの両方
- D) GPOで設定

<details>
<summary>解答と解説</summary>

**正解**: C) Horizon ConsoleとImvutilコマンドの両方

**解説**: 
- Home Site戦略は、Horizon ConsoleとImvutilコマンドの両方で設定できます
- ユーザーの位置に基づいて、最適なサイトに接続するように設定します

</details>

---

## 問題4: 災害復旧

**問題形式**: 多肢選択問題

Connection Serverのバックアップ対象として正しいものはどれですか？

- A) 設定のみ
- B) データベースのみ
- C) 設定とデータベース
- D) ログファイルのみ

<details>
<summary>解答と解説</summary>

**正解**: C) 設定とデータベース

**解説**: 
- Connection Serverのバックアップ対象は、設定とデータベースです
- 設定のエクスポートとデータベースのバックアップを実施します

</details>

---

## まとめ

これらの練習問題は、Section 6の主要なトピックをカバーしています。各問題の解答と解説を読んで、理解を深めてください。

## 関連リソース

- [Section 6 実環境シナリオ](../00_Scenarios/Section6_Scenarios.md) - 実環境でのシナリオ例
- [重要ポイント](../00_Exam_Tips/Key_Points.md) - 試験でよく出題される項目
- [暗記用資料](../00_Exam_Tips/Memory_Aids.md) - 暗記すべき数値、設定値、制限値
