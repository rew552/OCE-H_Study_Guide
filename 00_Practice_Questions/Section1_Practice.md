# Section 1: Infrastructure Planning and Management 練習問題

このドキュメントでは、Section 1に関する練習問題を提供します。

## 問題1: Connection Serverの高可用性構成

**問題形式**: 多肢選択問題

200 CCUの環境で、高可用性を確保しつつコストを最小限に抑える場合、Connection Serverは何台必要ですか？

- A) 1台
- B) 2台
- C) 3台
- D) 5台

<details>
<summary>解答と解説</summary>

**正解**: B) 2台

**解説**: 
- 200 CCUの環境では、2台のConnection Serverで十分です
- 高可用性を確保するため、最小2台が必要です
- 3台目はコストに見合わないため、200 CCUでは不要です
- 計算式: (200 / 2,000) + 1 = 1.1 → 2台（高可用性用に+1）

</details>

---

## 問題2: UAGとConnection Serverの比率

**問題形式**: 多肢選択問題

UAGとConnection Serverの推奨比率はどれですか？

- A) 1:2
- B) 1:1
- C) 2:1
- D) 3:1

<details>
<summary>解答と解説</summary>

**正解**: B) 1:1

**解説**: 
- ベストプラクティスとして、UAGとConnection Serverの1:1比率が推奨されます
- これにより、最適なパフォーマンスと可用性を実現できます

</details>

---

## 問題3: Connection Serverのポート番号

**問題形式**: 複数選択問題

Connection Serverで使用されるポート番号をすべて選択してください。

- A) 443
- B) 4001
- C) 4172
- D) 22443

<details>
<summary>解答と解説</summary>

**正解**: A) 443, B) 4001

**解説**: 
- **443**: HTTPS（管理コンソール、クライアント接続）
- **4001**: JMS（Connection Server間通信）
- 4172と22443はUAGで使用されるポート番号です

</details>

---

## 問題4: CPAの初期化

**問題形式**: 多肢選択問題

Cloud Pod Architectureの初期化はどこで実行しますか？

- A) すべてのポッドで実行
- B) 最初のポッドで一度だけ実行
- C) 各ポッドで個別に実行
- D) 最後のポッドで実行

<details>
<summary>解答と解説</summary>

**正解**: B) 最初のポッドで一度だけ実行

**解説**: 
- CPAの初期化は、最初のポッドで一度だけ実行します
- その後、他のポッドをフェデレーションに参加させます

</details>

---

## 問題5: App Volumes Managerの追加

**問題形式**: リスト構築問題

App Volumes Managerを追加する際の正しい手順を順番に並べてください。

1. 既存のManagerを指定
2. 追加Managerでのインストール
3. 登録を実行
4. 設定の同期

<details>
<summary>解答と解説</summary>

**正解**: 2 → 1 → 3 → 4

**解説**: 
1. 追加Managerでのインストール（同じインストーラーを使用）
2. 既存のManagerを指定
3. 登録を実行
4. 設定の同期

</details>

---

## 問題6: DEMファイル共有の要件

**問題形式**: 多肢選択問題

DEMファイル共有の要件として正しいものはどれですか？

- A) SMB 2.0以上
- B) SMB 3.0以上
- C) NFS 3.0以上
- D) NFS 4.0以上

<details>
<summary>解答と解説</summary>

**正解**: B) SMB 3.0以上

**解説**: 
- DEMファイル共有には、SMB 3.0以上が必要です
- 高可用性構成（DFS、クラスター）が推奨されます

</details>

---

## 問題7: アップグレード順序

**問題形式**: リスト構築問題

Horizonコンポーネントのアップグレード順序を正しく並べてください。

1. Connection Server
2. UAG
3. Horizon Agent
4. Cloud Pod Orchestrator（CPA環境の場合）

<details>
<summary>解答と解説</summary>

**正解**: 4 → 1 → 2 → 3

**解説**: 
1. Cloud Pod Orchestrator（CPA環境の場合）
2. Connection Server
3. UAG
4. Horizon Agent

依存関係を考慮して、この順序でアップグレードする必要があります。

</details>

---

## 問題8: FIPS 140-2モード

**問題形式**: 複数選択問題

FIPS 140-2コンプライアンス要件に対応するために、FIPSモードを有効化する必要があるコンポーネントをすべて選択してください。

- A) Connection Server
- B) UAG
- C) Horizon Agent
- D) vCenter Server

<details>
<summary>解答と解説</summary>

**正解**: A) Connection Server, B) UAG

**解説**: 
- Connection ServerとUAGでFIPSモードを有効化する必要があります
- すべてのコンポーネントでFIPSモードを有効化する必要がありますが、Horizon環境では主にConnection ServerとUAGが対象です

</details>

---

## 問題9: GPUプロファイルの選択

**問題形式**: 多肢選択問題

CAD/CAMアプリケーション用に100 CCUのGPUリソースが必要な場合、NVIDIA GRID GPU（各GPU: 16GB VRAM）を4台搭載したサーバーが4台ある場合、適切なvGPUプロファイルはどれですか？

- A) 2GB profile
- B) 4GB profile
- C) 8GB profile
- D) 16GB profile

<details>
<summary>解答と解説</summary>

**正解**: B) 4GB profile

**解説**: 
- 16個のGPU（4サーバー × 4 GPU）で、100 CCUをサポート
- 4GB profileを使用すると、16 GPU × 4 vGPU/GPU = 64 vGPU（100 CCUには十分）
- CAD/CAMアプリケーションの要件を考慮すると、4GB profileが適切です

</details>

---

## 問題10: Recording Serverのユースケース

**問題形式**: 複数選択問題

Recording Serverのユースケースとして正しいものをすべて選択してください。

- A) コンプライアンス
- B) セキュリティ監査
- C) トレーニング
- D) パフォーマンス監視

<details>
<summary>解答と解説</summary>

**正解**: A) コンプライアンス, B) セキュリティ監査, C) トレーニング

**解説**: 
- Recording Serverは、コンプライアンス、セキュリティ監査、トレーニングの目的で使用されます
- パフォーマンス監視は、Recording Serverの主な用途ではありません

</details>

---

## まとめ

これらの練習問題は、Section 1の主要なトピックをカバーしています。各問題の解答と解説を読んで、理解を深めてください。

## 関連リソース

- [Section 1 実環境シナリオ](../00_Scenarios/Section1_Scenarios.md) - 実環境でのシナリオ例
- [重要ポイント](../00_Exam_Tips/Key_Points.md) - 試験でよく出題される項目
- [暗記用資料](../00_Exam_Tips/Memory_Aids.md) - 暗記すべき数値、設定値、制限値
