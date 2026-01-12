# Section 3: Monitoring & Optimization 練習問題

このドキュメントでは、Section 3に関する練習問題を提供します。

## 問題1: Max Session Bandwidth

**問題形式**: 多肢選択問題

Max Session Bandwidthの設定方法として正しいものはどれですか？

- A) Horizon Consoleで設定
- B) レジストリで設定
- C) GPOで設定
- D) UAGで設定

<details>
<summary>解答と解説</summary>

**正解**: B) レジストリで設定

**解説**: 
- Max Session Bandwidthは、レジストリで設定します
- セッションあたりの最大帯域幅を制限するために使用されます

</details>

---

## 問題2: Build-to-lossless

**問題形式**: 多肢選択問題

Build-to-losslessを使用すべき場合として正しいものはどれですか？

- A) 帯域幅が限られている場合
- B) 高品質な画像が必要な場合
- C) すべての場合
- D) 使用すべきでない

<details>
<summary>解答と解説</summary>

**正解**: B) 高品質な画像が必要な場合

**解説**: 
- Build-to-losslessは、高品質な画像が必要な場合に使用します
- 帯域幅を消費するため、必要な場合のみ使用すべきです

</details>

---

## 問題3: Login Monitor

**問題形式**: 多肢選択問題

Login Monitorの主な用途はどれですか？

- A) ゴールデンイメージの最適化
- B) ログイン時間の監視と最適化
- C) セッション数の監視
- D) リソース使用率の監視

<details>
<summary>解答と解説</summary>

**正解**: B) ログイン時間の監視と最適化

**解説**: 
- Login Monitorは、継続的なログイン性能の監視と最適化に使用されます
- 各段階の処理時間を分析して、ボトルネックを特定できます

</details>

---

## 問題4: プール容量計画

**問題形式**: 多肢選択問題

プール容量計画で監視すべき項目として正しいものはどれですか？

- A) 予測容量と実際の容量
- B) CPU使用率のみ
- C) メモリ使用率のみ
- D) ストレージ使用率のみ

<details>
<summary>解答と解説</summary>

**正解**: A) 予測容量と実際の容量

**解説**: 
- プール容量計画では、リソース制約（予測容量 vs 実際の容量）に基づいて監視します
- CPU、メモリ、ストレージ、ネットワークのすべてを考慮する必要があります

</details>

---

## まとめ

これらの練習問題は、Section 3の主要なトピックをカバーしています。各問題の解答と解説を読んで、理解を深めてください。

## 関連リソース

- [Section 3 実環境シナリオ](../00_Scenarios/Section3_Scenarios.md) - 実環境でのシナリオ例
- [重要ポイント](../00_Exam_Tips/Key_Points.md) - 試験でよく出題される項目
- [暗記用資料](../00_Exam_Tips/Memory_Aids.md) - 暗記すべき数値、設定値、制限値
