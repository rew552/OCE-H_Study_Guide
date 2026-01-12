# Section 7: Automation & Integration 練習問題

このドキュメントでは、Section 7に関する練習問題を提供します。

## 問題1: REST API認証

**問題形式**: 多肢選択問題

Horizon REST APIの認証方法として正しいものはどれですか？

- A) OAuth 2.0のみ
- B) 基本認証のみ
- C) OAuth 2.0または基本認証
- D) SAML認証のみ

<details>
<summary>解答と解説</summary>

**正解**: C) OAuth 2.0または基本認証

**解説**: 
- Horizon REST APIの認証方法は、OAuth 2.0または基本認証です
- 環境に応じて適切な方法を選択します

</details>

---

## 問題2: Omnissa Access統合

**問題形式**: 多肢選択問題

Omnissa Access統合で設定する項目として正しいものはどれですか？

- A) 認証ポリシーのみ
- B) SAML Authenticatorのみ
- C) 認証ポリシーとSAML Authenticator
- D) SSO設定のみ

<details>
<summary>解答と解説</summary>

**正解**: C) 認証ポリシーとSAML Authenticator

**解説**: 
- Omnissa Access統合では、認証ポリシーとSAML Authenticatorを設定します
- Omnissa Accessで認証ポリシーを実装し、Horizon ConsoleでSAML Authenticatorを設定します

</details>

---

## 問題3: Omnissa Intelligence統合

**問題形式**: リスト構築問題

Omnissa Intelligence統合の正しい手順を順番に並べてください。

1. Edge Gatewayをデプロイ
2. DEEMエージェントをインストール
3. Virtual Desktop & Appsタイルを有効化
4. Subscription接続を設定

<details>
<summary>解答と解説</summary>

**正解**: 1 → 4 → 2 → 3

**解説**: 
1. Edge Gatewayをデプロイ
2. Subscription接続を設定
3. DEEMエージェントをインストール
4. connect.Omnissa.com → Intelligence → Marketplace → Solutions → Experience Management → Virtual Desktop & Appsタイルを有効化

</details>

---

## 問題4: APIベースの自動化

**問題形式**: 多肢選択問題

APIベースのプール管理自動化で実装すべき項目として正しいものはどれですか？

- A) エラーハンドリングのみ
- B) リトライロジックのみ
- C) エラーハンドリングとリトライロジック
- D) ログ記録のみ

<details>
<summary>解答と解説</summary>

**正解**: C) エラーハンドリングとリトライロジック

**解説**: 
- APIベースの自動化では、適切なエラーハンドリングとリトライロジックを実装する必要があります
- これにより、信頼性の高い自動化を実現できます

</details>

---

## まとめ

これらの練習問題は、Section 7の主要なトピックをカバーしています。各問題の解答と解説を読んで、理解を深めてください。

## 関連リソース

- [Section 7 実環境シナリオ](../00_Scenarios/Section7_Scenarios.md) - 実環境でのシナリオ例
- [重要ポイント](../00_Exam_Tips/Key_Points.md) - 試験でよく出題される項目
- [暗記用資料](../00_Exam_Tips/Memory_Aids.md) - 暗記すべき数値、設定値、制限値
