# Section 2: Desktop, Application, and Profile Management 練習問題

このドキュメントでは、Section 2に関する練習問題を提供します。

## 問題1: ゴールデンイメージの最適化

**問題形式**: 多肢選択問題

ゴールデンイメージの最適化に使用されるツールはどれですか？

- A) OSOT
- B) Login Monitor
- C) vSphere Client
- D) Horizon Console

<details>
<summary>解答と解説</summary>

**正解**: A) OSOT

**解説**: 
- OSOT (OS Optimization Tool) は、ゴールデンイメージを最適化するためのツールです
- Login Monitorは、ログイン時間を監視するツールです

</details>

---

## 問題2: デスクトッププールの種類

**問題形式**: 多肢選択問題

非永続デスクトッププールで推奨されるクローン方式はどれですか？

- A) Full Clone
- B) Linked Clone
- C) Instant Clone
- D) Template Clone

<details>
<summary>解答と解説</summary>

**正解**: C) Instant Clone

**解説**: 
- 非永続デスクトッププールでは、Instant Cloneが推奨されます
- Instant Cloneは、Horizon 8で推奨される最新のテクノロジーです
- Linked CloneはHorizon 8では非推奨です

</details>

---

## 問題3: Global Entitlements

**問題形式**: 多肢選択問題

Global Entitlementsはどの環境で使用できますか？

- A) 単一ポッド環境
- B) Cloud Pod Architecture環境
- C) すべての環境
- D) レプリケーショングループ環境

<details>
<summary>解答と解説</summary>

**正解**: B) Cloud Pod Architecture環境

**解説**: 
- Global Entitlementsは、Cloud Pod Architecture環境でのみ使用できます
- 複数のポッドにまたがるエンタイトルメントを提供します

</details>

---

## 問題4: AppStackとWritable Volume

**問題形式**: 複数選択問題

AppStackとWritable Volumeの違いとして正しいものをすべて選択してください。

- A) AppStackは読み取り専用、Writable Volumeは読み書き可能
- B) AppStackは複数のユーザー/マシンで共有、Writable Volumeはユーザー/マシンごと
- C) AppStackはアプリケーション、Writable Volumeはデータと設定
- D) AppStackは永続的、Writable Volumeは一時的

<details>
<summary>解答と解説</summary>

**正解**: A) AppStackは読み取り専用、Writable Volumeは読み書き可能, B) AppStackは複数のユーザー/マシンで共有、Writable Volumeはユーザー/マシンごと, C) AppStackはアプリケーション、Writable Volumeはデータと設定

**解説**: 
- AppStack: 読み取り専用、複数のユーザー/マシンで共有されるアプリケーション
- Writable Volume: 読み書き可能、ユーザー/マシンごとのデータと設定

</details>

---

## 問題5: DEM Smart Policies

**問題形式**: 多肢選択問題

DEM Smart Policiesの特徴として正しいものはどれですか？

- A) 条件付きポリシー
- B) すべてのユーザーに適用されるポリシー
- C) コンピューターのみに適用されるポリシー
- D) ユーザーのみに適用されるポリシー

<details>
<summary>解答と解説</summary>

**正解**: A) 条件付きポリシー

**解説**: 
- Smart Policiesは、条件付きポリシーです
- 特定の条件（ユーザーグループ、デバイスタイプなど）に基づいてポリシーを適用できます

</details>

---

## 問題6: RDSHファームのロードバランシング

**問題形式**: 多肢選択問題

RDSHファームのロードバランシングオプションとして正しいものはどれですか？

- A) セッションベースのみ
- B) リソースベースのみ
- C) セッションベースとリソースベース
- D) ラウンドロビンのみ

<details>
<summary>解答と解説</summary>

**正解**: C) セッションベースとリソースベース

**解説**: 
- RDSHファームでは、セッションベースとリソースベースのロードバランシングオプションが使用できます
- 環境に応じて適切なオプションを選択します

</details>

---

## 問題7: GPOの適用順序

**問題形式**: リスト構築問題

GPOの適用順序を正しく並べてください。

1. OU
2. ドメイン
3. ローカル
4. サイト

<details>
<summary>解答と解説</summary>

**正解**: 3 → 4 → 2 → 1

**解説**: 
- ローカル → サイト → ドメイン → OU
- この順序でGPOが適用され、後の順序のGPOが前の順序のGPOを上書きします

</details>

---

## 問題8: Application on Demand

**問題形式**: 多肢選択問題

Application on Demandの特徴として正しいものはどれですか？

- A) VM起動時にアプリケーションを動的にアタッチ
- B) すべてのVMに常にアタッチ
- C) ユーザーが手動でアタッチ
- D) スケジュールに基づいてアタッチ

<details>
<summary>解答と解説</summary>

**正解**: A) VM起動時にアプリケーションを動的にアタッチ

**解説**: 
- Application on Demandは、VM起動時にアプリケーションを動的にアタッチする機能です
- 大規模なアプリケーションや使用頻度の低いアプリケーションに適しています

</details>

---

## まとめ

これらの練習問題は、Section 2の主要なトピックをカバーしています。各問題の解答と解説を読んで、理解を深めてください。

## 関連リソース

- [Section 2 実環境シナリオ](../00_Scenarios/Section2_Scenarios.md) - 実環境でのシナリオ例
- [重要ポイント](../00_Exam_Tips/Key_Points.md) - 試験でよく出題される項目
- [暗記用資料](../00_Exam_Tips/Memory_Aids.md) - 暗記すべき数値、設定値、制限値
