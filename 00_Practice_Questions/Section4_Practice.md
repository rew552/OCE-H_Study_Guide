# Section 4: Troubleshooting 練習問題

このドキュメントでは、Section 4に関する練習問題を提供します。

## 問題1: Boot Storm

**問題形式**: 多肢選択問題

Boot Stormの主な原因はどれですか？

- A) CPU使用率の増加
- B) メモリ使用率の増加
- C) ストレージIOPSの急増
- D) ネットワーク帯域幅の増加

<details>
<summary>解答と解説</summary>

**正解**: C) ストレージIOPSの急増

**解説**: 
- Boot Stormは、多数のVMが同時に起動することによるストレージIOPSの急増です
- 対策として、段階的なVM起動を設定します

</details>

---

## 問題2: 接続障害のトラブルシューティング

**問題形式**: リスト構築問題

接続障害のトラブルシューティング手順を正しい順序で並べてください。

1. 認証の確認
2. ログファイルの確認
3. ネットワーク接続の確認
4. 証明書の確認

<details>
<summary>解答と解説</summary>

**正解**: 2 → 3 → 1 → 4

**解説**: 
1. ログファイルの確認（vdm.log、vdm-security.log）
2. ネットワーク接続の確認
3. 認証の確認
4. 証明書の確認

</details>

---

## 問題3: GPUボトルネック

**問題形式**: 多肢選択問題

小さすぎるGPUプロファイルが使用された場合の症状として正しいものはどれですか？

- A) CPU使用率の増加
- B) メモリ使用率の増加
- C) グラフィックパフォーマンスの低下
- D) ネットワーク帯域幅の増加

<details>
<summary>解答と解説</summary>

**正解**: C) グラフィックパフォーマンスの低下

**解説**: 
- 小さすぎるGPUプロファイルが使用された場合、グラフィックパフォーマンスが低下します
- VMレベルでのグラフィックドライバー問題を特定する必要があります

</details>

---

## 問題4: Instant Cloneデバッグモード

**問題形式**: 多肢選択問題

Instant Cloneデバッグモードを有効化する方法はどれですか？

- A) Horizon Consoleで設定
- B) レジストリで設定
- C) GPOで設定
- D) vCenter Serverで設定

<details>
<summary>解答と解説</summary>

**正解**: B) レジストリで設定

**解説**: 
- Instant Cloneデバッグモードは、レジストリで有効化します
- 有効化後、`vdm-instantclone.log`で詳細なログを確認できます

</details>

---

## まとめ

これらの練習問題は、Section 4の主要なトピックをカバーしています。各問題の解答と解説を読んで、理解を深めてください。

## 関連リソース

- [Section 4 実環境シナリオ](../00_Scenarios/Section4_Scenarios.md) - 実環境でのシナリオ例
- [重要ポイント](../00_Exam_Tips/Key_Points.md) - 試験でよく出題される項目
- [トラブルシューティングガイド](../Section4_Troubleshooting/4.1_Complex_VDI_Issues.md) - 詳細なトラブルシューティングガイド
