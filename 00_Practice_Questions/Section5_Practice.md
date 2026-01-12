# Section 5: Security & Compliance 練習問題

このドキュメントでは、Section 5に関する練習問題を提供します。

## 問題1: SSL証明書の更新

**問題形式**: 多肢選択問題

Connection ServerのSSL証明書を更新する際の正しい手順はどれですか？

- A) 1台ずつ順次更新
- B) すべてのConnection Serverで同時に更新
- C) プライマリのみ更新
- D) レプリカのみ更新

<details>
<summary>解答と解説</summary>

**正解**: B) すべてのConnection Serverで同時に更新

**解説**: 
- 証明書の更新時は、すべてのConnection Serverで同時に更新する必要があります
- 更新前にバックアップを取得してください

</details>

---

## 問題2: MFAの実装方法

**問題形式**: 複数選択問題

Horizon環境で実装できるMFA方式をすべて選択してください。

- A) SAML
- B) RADIUS
- C) RSA
- D) スマートカード

<details>
<summary>解答と解説</summary>

**正解**: A) SAML, B) RADIUS, C) RSA, D) スマートカード

**解説**: 
- Horizon環境では、SAML、RADIUS、RSA、スマートカードのすべてのMFA方式を実装できます
- 環境に応じて適切な方式を選択します

</details>

---

## 問題3: データ保護ポリシー

**問題形式**: 多肢選択問題

クリップボードポリシーの設定場所として正しいものはどれですか？

- A) Horizon Consoleのみ
- B) DEM/GPOのみ
- C) Horizon ConsoleとDEM/GPO
- D) vCenter Serverのみ

<details>
<summary>解答と解説</summary>

**正解**: C) Horizon ConsoleとDEM/GPO

**解説**: 
- クリップボード、CDR、USBリダイレクションのポリシーは、Horizon ConsoleとDEM/GPOの両方で設定できます
- 環境に応じて適切な方法を選択します

</details>

---

## 問題4: USBリダイレクション

**問題形式**: 多肢選択問題

USBリダイレクションの制御方法として正しいものはどれですか？

- A) 無効化のみ
- B) 有効化のみ
- C) 無効化、有効化、ホワイトリスト、ブラックリスト
- D) ホワイトリストのみ

<details>
<summary>解答と解説</summary>

**正解**: C) 無効化、有効化、ホワイトリスト、ブラックリスト

**解説**: 
- USBリダイレクションは、無効化、有効化、ホワイトリスト、ブラックリストのすべての制御方法が使用できます
- セキュリティ要件に応じて適切な方法を選択します

</details>

---

## まとめ

これらの練習問題は、Section 5の主要なトピックをカバーしています。各問題の解答と解説を読んで、理解を深めてください。

## 関連リソース

- [Section 5 実環境シナリオ](../00_Scenarios/Section5_Scenarios.md) - 実環境でのシナリオ例
- [重要ポイント](../00_Exam_Tips/Key_Points.md) - 試験でよく出題される項目
- [暗記用資料](../00_Exam_Tips/Memory_Aids.md) - 暗記すべき数値、設定値、制限値
