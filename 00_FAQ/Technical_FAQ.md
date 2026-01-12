# 技術的なFAQ

このドキュメントでは、Horizon技術に関するよくある質問と回答を提供します。

## Connection Server

### Q1: Connection Serverは何台必要ですか？

**A**: CCU（同時接続ユーザー数）に基づいて決定します：
- 0-500 CCU: 1-2台
- 500-2,000 CCU: 2-3台
- 2,000-5,000 CCU: 3-5台
- 5,000以上: 5台以上

高可用性を確保するため、最小2台、推奨3-5台のConnection Serverを配置します。

### Q2: Connection Serverのレプリケーショングループとは？

**A**: 複数のConnection Serverを同じデータベースを共有するグループとして構成することです。これにより、高可用性と負荷分散を実現できます。すべてのConnection Serverは同じバージョンである必要があります。

### Q3: Connection Serverのポート番号は？

**A**: 
- **443**: HTTPS（管理コンソール、クライアント接続）
- **4001**: JMS（Connection Server間通信）

## UAG (Unified Access Gateway)

### Q4: UAGとConnection Serverの比率は？

**A**: ベストプラクティスとして、UAGとConnection Serverの1:1比率が推奨されます。ただし、環境によっては異なる比率も可能です。

### Q5: Multi-NICとSingle-NICの違いは？

**A**: 
- **Multi-NIC**: 外部ネットワークと内部ネットワークを物理的に分離。セキュリティ要件が高い環境で推奨
- **Single-NIC**: シンプルな構成。小規模環境やテスト環境で使用

### Q6: UAGのポート番号は？

**A**: 
- **443**: HTTPS（クライアント接続、管理）
- **4172**: PCoIPトンネル
- **22443**: Blast Protocolトンネル
- **9443**: 管理インターフェース

## Cloud Pod Architecture (CPA)

### Q7: CPAの初期化はどこで行いますか？

**A**: 最初のポッドで一度だけ実行します。Horizon Console → View Configuration → Cloud Pod Architecture → Initialize Cloud Pod Architecture

### Q8: グローバルLDAPとローカルLDAPの違いは？

**A**: 
- **グローバルLDAP**: フェデレーション全体で使用。グローバルエンタイトルメントの管理
- **ローカルLDAP**: 各ポッドで使用。ローカルエンタイトルメントの管理

### Q9: Home Siteとは？

**A**: ユーザーの物理的な位置に基づいて、最適なサイト（ポッド）に接続するための設定です。Imvutilコマンドで設定できます。

## App Volumes

### Q10: AppStackとWritable Volumeの違いは？

**A**: 
- **AppStack**: 読み取り専用。複数のユーザー/マシンで共有されるアプリケーション
- **Writable Volume**: 読み書き可能。ユーザー/マシンごとのデータと設定

### Q11: Application on Demandとは？

**A**: VM起動時にアプリケーションを動的にアタッチする機能です。大規模なアプリケーションや使用頻度の低いアプリケーションに適しています。

### Q12: App Volumes Managerは何台必要ですか？

**A**: 高可用性を確保するため、複数のManagerを登録することが推奨されます。通常は2-3台のManagerを配置します。

## DEM (Dynamic Environment Manager)

### Q13: DEMファイル共有の要件は？

**A**: 
- SMB 3.0以上
- 高可用性構成（DFS、クラスター）が推奨
- 適切なアクセス権限の設定

### Q14: Smart Policiesとは？

**A**: 条件付きポリシーです。特定の条件（ユーザーグループ、デバイスタイプなど）に基づいてポリシーを適用できます。

### Q15: 条件セット（モジュラーアプローチ）とは？

**A**: 再利用可能な条件セットを作成し、複数のポリシーで使用するアプローチです。管理の効率化と一貫性の向上に役立ちます。

## デスクトッププール

### Q16: 永続デスクトップと非永続デスクトップの違いは？

**A**: 
- **永続デスクトップ**: 専用割り当て、データと設定が保持される。Full Cloneを使用
- **非永続デスクトップ**: フローティング割り当て、セッション終了後に変更が破棄される。Instant Cloneを使用

### Q17: Instant Cloneの要件は？

**A**: 
- 親VMにHorizon Agentがインストールされている
- スナップショットが作成されている
- 親VMが電源オフ状態

### Q18: プロビジョニング時間を短縮するには？

**A**: 
- ゴールデンイメージの最適化（OSOT使用）
- 高速ストレージの使用
- 段階的なプロビジョニング設定
- ストレージIOPSの確保

## トラブルシューティング

### Q19: Boot Stormとは？

**A**: 多数のVMが同時に起動することによるストレージIOPSの急増です。対策として、段階的なVM起動を設定します。

### Q20: Logon Stormとは？

**A**: 多数のユーザーが同時にログオンすることによる認証サーバーやネットワークの負荷増加です。対策として、ログオン時間の分散や認証サーバーの最適化を行います。

### Q21: 接続障害のトラブルシューティング手順は？

**A**: 
1. ログファイルの確認（vdm.log、vdm-security.log）
2. ネットワーク接続の確認
3. DNS解決の確認
4. 認証の確認
5. 証明書の確認

### Q22: パフォーマンス問題の診断方法は？

**A**: 
- vSphere Clientでリソース使用率を確認
- Horizon Consoleでセッション情報を確認
- Windowsパフォーマンスモニターで詳細なメトリックを確認
- Login Monitorでログイン時間を分析

## セキュリティ

### Q23: MFAの実装方法は？

**A**: 
- **SAML**: SAML 2.0認証、Omnissa Access統合
- **RADIUS**: 既存のRADIUSサーバーを使用
- **RSA**: RSA SecurID
- **スマートカード**: 証明書ベース認証

### Q24: SSL証明書の更新手順は？

**A**: 
1. CSR（証明書署名要求）を生成
2. 証明書を申請
3. すべてのConnection Serverで同時に更新
4. 証明書チェーンを含む完全な証明書をインストール

### Q25: データ保護ポリシーの設定場所は？

**A**: 
- Horizon Console
- DEM/GPO

クリップボード、CDR、USBリダイレクションのポリシーを設定できます。

## アップグレード

### Q26: アップグレード順序は？

**A**: 
1. Cloud Pod Orchestrator（CPA環境の場合）
2. Connection Server
3. UAG
4. Horizon Agent
5. App Volumes Agent
6. DEM Agent

### Q27: アップグレード前の準備は？

**A**: 
- バックアップの取得
- テスト環境での検証
- メンテナンスウィンドウの確保
- 依存関係の確認

## スケーリング

### Q28: Connection Serverのスケーリング方法は？

**A**: 
- Replica Serverとして追加
- ロードバランサーに追加
- レプリケーションの確認

### Q29: App Volumesのスケーリング方法は？

**A**: 
- 追加App Volumes Managerのインストールと登録
- ストレージ容量の拡張
- レプリケーション設定の確認

### Q30: DEMのスケーリング方法は？

**A**: 
- 追加ファイル共有の設定
- Management Consoleの追加
- 負荷分散の設定

## 関連リソース

- [重要ポイント](../00_Exam_Tips/Key_Points.md) - 試験でよく出題される項目
- [実環境シナリオ](../00_Scenarios/README.md) - 実環境でのシナリオ例
- [ケーススタディ](../00_Case_Studies/README.md) - 実践的なケーススタディ
- [トラブルシューティング](../Section4_Troubleshooting/4.1_Complex_VDI_Issues.md) - トラブルシューティングガイド
