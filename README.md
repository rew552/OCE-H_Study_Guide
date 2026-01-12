# OCE-H 試験対策学習ガイド

## 試験概要

### 基本情報

- **試験名**: Omnissa Horizon Engineer - 2025 (2H0_25)
- **認定資格**: Omnissa Certified Engineer – Horizon (OCE-H)
- **問題数**: 65問
- **試験時間**: 135分（非英語話者向けの十分な時間を含む）
- **合格点**: 275点（スケール方式）

### 試験形式

この試験には以下のような問題形式が含まれる場合があります：

- 多肢選択問題（Multiple-choice）
- 複数選択問題（Multiple-selection multiple-choice）
- リスト構築問題（Build-list）
- マッチング問題（Matching）
- ドラッグ&ドロップ問題（Drag-and-drop）
- ポイント&クリック問題（Point-and-click）
- ホットエリア問題（Hot-area）

その他の問題形式も使用される場合がありますが、上記の形式よりも頻度は低くなります。

### 試験配信

この試験はPearson VUEを通じて配信される監視付き試験です。

### 最小資格要件

この試験の最小資格要件を満たす候補者は：

1. **経験**: 一般的なIT経験が少なくとも5年、Omnissa Horizon Suiteの経験が12ヶ月以上あり、Horizonソリューションの管理経験がある
2. **知識**: Horizon環境とコンポーネントの高度な管理知識を持ち、特定の目標と要件を満たすためにHorizon Suiteをデプロイできる
3. **トラブルシューティング**: Horizon Suiteの問題をトラブルシューティングする経験がある
4. **統合**: Omnissa Horizon SuiteとOmnissa Workspace ONE UEMを統合する経験がある
5. **認定**: Omnissa Certified Administrator認定を保持しており、OCA試験ブループリントに含まれるすべての知識を持っている
6. **知識**: 試験セクション（ブループリント）に示されている知識の大部分、おそらくすべてを持っている

> [!IMPORTANT]

> OCE-H試験は、OCA-H試験よりも高度な内容を含みます。OCA-H認定を取得していることが前提条件となっています。

## 試験セクション

この試験は以下の7つのセクションに分かれています：

1. **Infrastructure Planning and Management**（インフラストラクチャの計画と管理）
2. **Desktop, application, and profile management**（デスクトップ、アプリケーション、プロファイル管理）
3. **Monitoring & Optimization**（監視と最適化）
4. **Troubleshooting**（トラブルシューティング）
5. **Security & Compliance**（セキュリティとコンプライアンス）
6. **Scale and Recovery**（スケーリングと災害復旧）
7. **Automation & Integration**（自動化と統合）

各セクションの目的番号は、試験結果レポートで参照され、再受験が必要な場合の準備に役立ちます。

## 試験ガイドPDFとの対応表

以下の表は、試験ガイドPDF（OCE_Horizon_Exam_Guide.pdf）の各項目と、この学習ガイドの対応セクションを示しています。

### Section 1: Infrastructure Planning and Management

| 試験ガイド項目 | 学習ガイドセクション | 説明 |
|---------------|-------------------|------|
| 4.1.1 Install/configure Connection Servers, Enrollment Servers, and Access Connectors | [1.1](Section1_Infrastructure_Planning_and_Management/1.1_Connection_Servers_Enrollment_Access_Connectors.md) | マルチノード環境での高可用性構成、グローバル設定の最適化 |
| 4.1.2 Planning Horizon Deployments | [1.2](Section1_Infrastructure_Planning_and_Management/1.2_Planning_Horizon_Deployments.md) | 必要なコンポーネントの識別、サイジング |
| 4.1.3 Integrate Active Directory | [1.3](Section1_Infrastructure_Planning_and_Management/1.3_Active_Directory_Integration.md) | Service Accounts、グループ、OU、ADMXテンプレート |
| 4.1.4 Deploy/update Unified Access Gateways | [1.4](Section1_Infrastructure_Planning_and_Management/1.4_Unified_Access_Gateways.md) | デプロイ方法、HA構成、ファイアウォール設定 |
| 4.1.5 Manage licenses and deploy edge gateway | [1.5](Section1_Infrastructure_Planning_and_Management/1.5_Licenses_Edge_Gateway.md) | ライセンス方法、Edge Gatewayデプロイ |
| 4.1.6 Maintain pod/farm architecture | [1.6](Section1_Infrastructure_Planning_and_Management/1.6_Pod_Farm_Architecture.md) | CPAサイト設定、アップグレード、RDSHファーム、Application on Demand |
| 4.1.7 Integrate and configure Dynamic Environment Manager (DEM) | [1.7](Section1_Infrastructure_Planning_and_Management/1.7_DEM_Integration.md) | ファイル共有、Management Console、Smart Policies、条件セット |
| 4.1.8 Integrate and configure App Volumes | [1.8](Section1_Infrastructure_Planning_and_Management/1.8_App_Volumes_Integration.md) | Managerインストール、SQL接続、ストレージ、レプリケーション |
| 4.1.9 Resource allocation and load balancing | [1.9](Section1_Infrastructure_Planning_and_Management/1.9_Resource_Allocation_Load_Balancing.md) | Connection Serverロードバランシング、UAG統合 |
| 4.1.10 Upgrade Horizon platform | [1.10](Section1_Infrastructure_Planning_and_Management/1.10_Horizon_Platform_Upgrade.md) | アップグレード順序、依存関係、メンテナンスウィンドウ |
| 4.1.11 Use Recording Server | [1.11](Section1_Infrastructure_Planning_and_Management/1.11_Recording_Server.md) | ユースケース、前提条件、記録基準、デプロイ |
| 4.1.12 Implement compliance - FIPS 140-2 mode | [1.12](Section1_Infrastructure_Planning_and_Management/1.12_FIPS_140-2_Compliance.md) | Connection Server、UAGのFIPSモード |
| 4.1.13 Allocate GPU resources | [1.13](Section1_Infrastructure_Planning_and_Management/1.13_GPU_Resource_Allocation.md) | グラフィックアクセラレーション、VM密度 |

### Section 2: Desktop, Application, and Profile Management

| 試験ガイド項目 | 学習ガイドセクション | 説明 |
|---------------|-------------------|------|
| （詳細項目は試験ガイドに記載なし） | [2.1-2.7](Section2_Desktop_Application_Profile_Management/) | ゴールデンイメージ、デスクトッププール、エンタイトルメント、RDSHファーム、App Volumes、DEM、GPO |

### Section 3: Monitoring & Optimization

| 試験ガイド項目 | 学習ガイドセクション | 説明 |
|---------------|-------------------|------|
| 4.3.1 Advanced optimization of display protocols | [3.1](Section3_Monitoring_Optimization/3.1_Advanced_Display_Protocol_Optimization.md) | Max Session Bandwidth、Build-to-lossless |
| 4.3.2 Advanced optimization of golden images | [3.2](Section3_Monitoring_Optimization/3.2_Advanced_Golden_Image_Optimization.md) | レジストリ最適化、Windowsパフォーマンス設定、Login Monitor |
| 4.3.3 Pool capacity planning | [3.3](Section3_Monitoring_Optimization/3.3_Pool_Capacity_Planning.md) | リソース制約に基づく監視と調整 |

### Section 4: Troubleshooting

| 試験ガイド項目 | 学習ガイドセクション | 説明 |
|---------------|-------------------|------|
| 4.4.1 Troubleshoot and resolve complex VDI issues | [4.1](Section4_Troubleshooting/4.1_Complex_VDI_Issues.md) | 接続障害、リソースボトルネック、ストレージI/O、GPU、Boot/Logon storms、Global Entitlements、グラフィックドライバー、Instant cloneデバッグ |

### Section 5: Security & Compliance

| 試験ガイド項目 | 学習ガイドセクション | 説明 |
|---------------|-------------------|------|
| 4.5.1 Implement SSL certificates | [5.1](Section5_Security_Compliance/5.1_SSL_Certificates_MFA.md) | SSL証明書、MFA（SAML、RADIUS、RSA、スマートカード）、二要素認証 |
| 4.5.2 Data Protection | [5.2](Section5_Security_Compliance/5.2_Data_Protection.md) | クリップボード、CDR、USBリダイレクションポリシー |

### Section 6: Scale and Recovery

| 試験ガイド項目 | 学習ガイドセクション | 説明 |
|---------------|-------------------|------|
| 4.6.1 Scale Horizon environment | [6.1](Section6_Scale_and_Recovery/6.1_Scale_Horizon_Environment.md) | CS、App Volumes、DEMのスケーリング |
| 4.6.2 Scale Horizon environment using Cloud Pod Architecture (CPA) | [6.2](Section6_Scale_and_Recovery/6.2_Cloud_Pod_Architecture.md) | CPA初期化、Pod参加、Global Entitlement、Home Site、Imvutil |
| 4.6.3 Configure disaster recovery and business continuity | [6.3](Section6_Scale_and_Recovery/6.3_Disaster_Recovery_Business_Continuity.md) | Connection Serverバックアップ、App Volumes HA、DEM HA |

### Section 7: Automation & Integration

| 試験ガイド項目 | 学習ガイドセクション | 説明 |
|---------------|-------------------|------|
| 4.7.1 Automate pool management | [7.1](Section7_Automation_Integration/7.1_Automate_Pool_Management.md) | APIベースの統合 |
| 4.7.2 Integrate Horizon Pod into Omnissa Access | [7.2](Section7_Automation_Integration/7.2_Omnissa_Access_Integration.md) | 認証ポリシー、SAML Authenticator、SSO設定 |
| 4.7.3 Integrate with Omnissa Intelligence | [7.3](Section7_Automation_Integration/7.3_Omnissa_Intelligence_Integration.md) | Edge Gateway、DEEMエージェント、Marketplace有効化 |

## 学習の進め方

### 推奨学習順序

1. **製品概要とアーキテクチャ**を理解する
   - Omnissa Horizonの基本概念
   - アーキテクチャと主要コンポーネント
   - OCA-Hレベルの知識の復習

2. **Section 1: Infrastructure Planning and Management**
   - Connection Server、Enrollment Server、Access Connectorの高度な設定
   - UAGのデプロイとHA構成
   - DEMとApp Volumesの統合
   - Recording Server、FIPS 140-2、GPUリソース割り当て

3. **Section 2: Desktop, application, and profile management**
   - ゴールデンイメージの高度な最適化
   - デスクトッププール、エンタイトルメント、RDSHファームの高度な管理
   - App Volumes、DEM、GPOの高度な設定

4. **Section 3: Monitoring & Optimization**
   - 高度な表示プロトコル最適化
   - 高度なゴールデンイメージ最適化
   - プール容量計画

5. **Section 4: Troubleshooting**
   - 複雑なVDI問題のトラブルシューティング
   - Boot stormsとLogon storms
   - リソースボトルネック、ストレージI/O問題、GPUリソース割り当て問題

6. **Section 5: Security & Compliance**
   - SSL証明書と多要素認証（MFA）の実装
   - データ保護ポリシー（クリップボード、CDR、USBリダイレクション）

7. **Section 6: Scale and Recovery**
   - Horizon環境のスケーリング
   - Cloud Pod Architecture（CPA）の実装と管理
   - 災害復旧と事業継続戦略

8. **Section 7: Automation & Integration**
   - APIベースのプール管理自動化
   - Omnissa Access統合
   - Omnissa Intelligence統合

### 学習のポイント

- 各セクションの概念を深く理解し、実践的な知識を身につける
- 高度な設定手順やベストプラクティスを理解する
- 複雑なトラブルシューティングの方法を習得する
- 試験ガイドに記載されている各項目を漏れなく学習する
- 実環境での経験を積むことが重要

> [!TIP]

> OCE-H試験は実践的な知識を重視します。可能であれば、実環境やラボ環境で実際に設定やトラブルシューティングを経験することを強く推奨します。

## 目次

### 基礎知識

- [製品概要とアーキテクチャ](00_Overview_Architecture/README.md)
- [クイックリファレンス](00_Quick_Reference.md) - ポート番号、設定値、制限値、ログファイル一覧
- [実環境シナリオ](00_Scenarios/README.md) - 実環境でのシナリオ例と解決策
- [試験対策のヒント](00_Exam_Tips/README.md) - 重要ポイントのまとめ、暗記用資料
- [練習問題](00_Practice_Questions/README.md) - 試験対策のための練習問題
- [ケーススタディ](00_Case_Studies/README.md) - 実践的なケーススタディ
- [FAQ](00_FAQ/README.md) - よくある質問と回答

### Section 1: Infrastructure Planning and Management

- [1.1 Connection Servers, Enrollment Servers, and Access Connectors](Section1_Infrastructure_Planning_and_Management/1.1_Connection_Servers_Enrollment_Access_Connectors.md)
- [1.2 Planning Horizon Deployments](Section1_Infrastructure_Planning_and_Management/1.2_Planning_Horizon_Deployments.md)
- [1.3 Active Directory Integration](Section1_Infrastructure_Planning_and_Management/1.3_Active_Directory_Integration.md)
- [1.4 Unified Access Gateways](Section1_Infrastructure_Planning_and_Management/1.4_Unified_Access_Gateways.md)
- [1.5 Licenses and Edge Gateway](Section1_Infrastructure_Planning_and_Management/1.5_Licenses_Edge_Gateway.md)
- [1.6 Pod/Farm Architecture](Section1_Infrastructure_Planning_and_Management/1.6_Pod_Farm_Architecture.md)
- [1.7 DEM Integration](Section1_Infrastructure_Planning_and_Management/1.7_DEM_Integration.md)
- [1.8 App Volumes Integration](Section1_Infrastructure_Planning_and_Management/1.8_App_Volumes_Integration.md)
- [1.9 Resource Allocation and Load Balancing](Section1_Infrastructure_Planning_and_Management/1.9_Resource_Allocation_Load_Balancing.md)
- [1.10 Horizon Platform Upgrade](Section1_Infrastructure_Planning_and_Management/1.10_Horizon_Platform_Upgrade.md)
- [1.11 Recording Server](Section1_Infrastructure_Planning_and_Management/1.11_Recording_Server.md)
- [1.12 FIPS 140-2 Compliance](Section1_Infrastructure_Planning_and_Management/1.12_FIPS_140-2_Compliance.md)
- [1.13 GPU Resource Allocation](Section1_Infrastructure_Planning_and_Management/1.13_GPU_Resource_Allocation.md)

### Section 2: Desktop, Application, and Profile Management

- [2.1 Golden Images](Section2_Desktop_Application_Profile_Management/2.1_Golden_Images.md)
- [2.2 Desktop Pools](Section2_Desktop_Application_Profile_Management/2.2_Desktop_Pools.md)
- [2.3 Entitlements](Section2_Desktop_Application_Profile_Management/2.3_Entitlements.md)
- [2.4 RDSH Farms](Section2_Desktop_Application_Profile_Management/2.4_RDSH_Farms.md)
- [2.5 App Volumes](Section2_Desktop_Application_Profile_Management/2.5_App_Volumes.md)
- [2.6 DEM Policies](Section2_Desktop_Application_Profile_Management/2.6_DEM_Policies.md)
- [2.7 GPOs](Section2_Desktop_Application_Profile_Management/2.7_GPOs.md)

### Section 3: Monitoring & Optimization

- [3.1 Advanced Display Protocol Optimization](Section3_Monitoring_Optimization/3.1_Advanced_Display_Protocol_Optimization.md)
- [3.2 Advanced Golden Image Optimization](Section3_Monitoring_Optimization/3.2_Advanced_Golden_Image_Optimization.md)
- [3.3 Pool Capacity Planning](Section3_Monitoring_Optimization/3.3_Pool_Capacity_Planning.md)

### Section 4: Troubleshooting

- [4.1 Complex VDI Issues](Section4_Troubleshooting/4.1_Complex_VDI_Issues.md)

### Section 5: Security & Compliance

- [5.1 SSL Certificates and MFA](Section5_Security_Compliance/5.1_SSL_Certificates_MFA.md)
- [5.2 Data Protection](Section5_Security_Compliance/5.2_Data_Protection.md)

### Section 6: Scale and Recovery

- [6.1 Scale Horizon Environment](Section6_Scale_and_Recovery/6.1_Scale_Horizon_Environment.md)
- [6.2 Cloud Pod Architecture](Section6_Scale_and_Recovery/6.2_Cloud_Pod_Architecture.md)
- [6.3 Disaster Recovery and Business Continuity](Section6_Scale_and_Recovery/6.3_Disaster_Recovery_Business_Continuity.md)

### Section 7: Automation & Integration

- [7.1 Automate Pool Management](Section7_Automation_Integration/7.1_Automate_Pool_Management.md)
- [7.2 Omnissa Access Integration](Section7_Automation_Integration/7.2_Omnissa_Access_Integration.md)
- [7.3 Omnissa Intelligence Integration](Section7_Automation_Integration/7.3_Omnissa_Intelligence_Integration.md)

## 推奨コース

Omnissaは以下のコースを試験準備に強く推奨しています：

1. **Horizon 8: Deploy and Manage**
2. **Horizon Troubleshooting**

## 推奨リソース

以下のOmnissaリソースが試験準備に役立ちます：

- **Omnissa Blogs**: 最新の技術情報とベストプラクティス
- **Omnissa Docs**: 公式ドキュメント
- **Omnissa Knowledgebase**: トラブルシューティング情報とFAQ
- **Techzone**: 技術的な詳細情報とアーキテクチャガイド

## 用語集

### A

- **Access Connector**: Horizon環境への接続を提供するコンポーネント。モバイルデバイス管理（MDM）との統合に使用。
- **AppStack**: App Volumesで使用される読み取り専用のアプリケーションボリューム。複数のユーザーやマシンで共有される。
- **Application on Demand**: アプリケーションをオンデマンドで配信する機能。VM起動時にアプリケーションを動的にアタッチ。

### B

- **Blast Protocol**: Horizon 8のデフォルト表示プロトコル。BlastCodec、H.264、Adaptiveコーデックをサポート。
- **BlastCodec**: Blast Protocolのデフォルトコーデック。高品質な表示を提供。
- **Boot Storm**: 多数の仮想マシンが同時に起動することによるリソース競合。
- **Build-to-lossless**: Blast Protocolの機能。画像品質を向上させるために使用されるが、帯域幅を消費する。

### C

- **Cloud Pod Architecture (CPA)**: 複数のHorizonサイトを統合して、グローバルなエンタイトルメントを提供するアーキテクチャ。
- **Connection Server**: Horizon環境の中核コンポーネント。ユーザー認証、デスクトップとアプリケーションのブローカー機能を提供。
- **Condition Sets**: DEMで使用される条件セット。モジュラーアプローチでポリシーを適用。

### D

- **DEEM Agent**: Omnissa Intelligenceにデータを送信するエージェント。
- **DEM (Dynamic Environment Manager)**: ユーザー環境とプロファイルを管理するツール。以前はUser Environment Manager (UEM)として知られていた。
- **Desktop Pool**: 仮想デスクトップをグループ化する論理的なコンテナ。永続または非永続のデスクトッププールがある。

### E

- **Edge Gateway**: Omnissa Intelligenceにデータを送信するゲートウェイコンポーネント。
- **Enrollment Server**: モバイルデバイスの登録を管理するサーバー。
- **Entitlement**: ユーザーやグループがデスクトップやアプリケーションにアクセスするための権限。
- **ESXi**: VMwareのハイパーバイザー。仮想マシンを実行するためのプラットフォーム。

### F

- **FIPS 140-2**: 連邦情報処理標準。暗号化モジュールのセキュリティ要件を定義。
- **Full Clone**: ゴールデンイメージから完全に独立した仮想マシンを作成する方法。永続デスクトップに使用。
- **Floating Assignment**: 非永続デスクトッププールで使用されるユーザー割り当て方法。ユーザーは利用可能なデスクトップに接続。

### G

- **Global Entitlement**: Cloud Pod Architectureで使用される、複数ポッドにまたがるエンタイトルメント。
- **Global LDAP Instance**: Cloud Pod Architectureで使用される、グローバルなLDAPインスタンス。
- **Golden Image**: 仮想デスクトップやアプリケーションのベースとなるマスターイメージ。
- **GPO (Group Policy Object)**: Active Directoryで使用される設定管理ツール。Horizon環境でも設定管理に使用。
- **GPU Profile**: GPUリソースの割り当てプロファイル。vGPU、DirectPath I/O、vSGAなど。

### H

- **Home Site**: Cloud Pod Architectureで使用される、ユーザーのホームサイト設定。
- **Horizon Agent**: 仮想デスクトップやRDSHホストにインストールされるエージェント。Horizon Clientとの通信を管理。
- **Horizon Client**: ユーザーが仮想デスクトップやアプリケーションにアクセスするためのクライアントアプリケーション。

### I

- **Imvutil**: Cloud Pod Architectureを管理するためのコマンドラインツール。
- **Instant Clone**: 親イメージから高速に仮想マシンを作成する最新のテクノロジー。非永続デスクトップに使用。
- **IOPS (Input/Output Operations Per Second)**: ストレージのパフォーマンス指標。1秒あたりの入出力操作数。

### L

- **Linked Clone**: 親イメージを共有し、差分ディスクを使用する仮想マシンを作成する方法。Horizon 8では非推奨。
- **Local LDAP Instance**: 各ポッドで使用されるローカルなLDAPインスタンス。
- **Logon Storm**: 多数のユーザーが同時にログオンすることによるリソース競合。

### M

- **MFA (Multi-Factor Authentication)**: 多要素認証。SAML、RADIUS、RSA、スマートカードなどを使用。

### N

- **Non-Persistent Desktop**: セッション終了後にデータが破棄されるデスクトップ。フローティング割り当てと組み合わせて使用。

### O

- **OSOT (OS Optimization Tool)**: ゴールデンイメージを最適化するためのツール。ログオン時間の短縮とリソース使用量の削減を実現。
- **On-Demand Delivery**: App Volumesで使用される配信方法。アプリケーション起動時にパッケージを動的にアタッチ。

### P

- **PCoIP (PC-over-IP)**: Teradiciが開発した表示プロトコル。WAN環境での使用に適している。
- **Persistent Desktop**: セッション終了後もデータが保持されるデスクトップ。専用割り当てと組み合わせて使用。
- **Pod**: Horizon環境の論理的なグループ。複数のConnection Serverを含む。
- **Pod Federation**: Cloud Pod Architectureで使用される、複数のポッドを統合するフェデレーション。

### R

- **RDP (Remote Desktop Protocol)**: Microsoftが開発した表示プロトコル。基本的なリモートデスクトップ機能を提供。
- **RDSH (Remote Desktop Session Host)**: 複数のユーザーセッションを同時に実行するWindows Server。アプリケーション配信に使用。
- **Recording Server**: ユーザーセッションを記録するためのサーバー。
- **RTT (Round Trip Time)**: ネットワークパケットが往復する時間。レイテンシの指標。

### S

- **SAML (Security Assertion Markup Language)**: シングルサインオン（SSO）を実現するための認証プロトコル。
- **Smart Policies**: DEMで使用される条件付きポリシー。特定の条件に基づいてポリシーを適用。
- **Snapshot**: 仮想マシンの特定時点の状態を保存したもの。ロールバックに使用。
- **Storage Access Mode**: App Volumesで使用されるストレージアクセスモード。

### U

- **UAG (Unified Access Gateway)**: 外部ネットワークからのHorizon環境へのセキュアなアクセスを提供するゲートウェイ。
- **UDP (User Datagram Protocol)**: ネットワークプロトコル。Blast ProtocolとPCoIPで使用される。

### V

- **vCenter Server**: VMware vSphere環境を管理するための管理サーバー。
- **VDI (Virtual Desktop Infrastructure)**: 仮想デスクトップインフラストラクチャ。仮想デスクトップを配信する技術。
- **vGPU (Virtual GPU)**: 仮想マシンで使用される仮想GPU。複数のVMでGPUリソースを共有。
- **vSGA (Virtual Shared Graphics Acceleration)**: 仮想共有グラフィックアクセラレーション。ソフトウェアベースのGPU共有。

### W

- **Writable Volume**: App Volumesで使用される読み書き可能なボリューム。ユーザーデータと設定を保存。

## 学習リソースへのリンク

### 公式リソース

- **Omnissa Learning**: https://www.omnissa.com/omnissa-learning
- **Omnissa Docs**: 公式ドキュメント
- **Omnissa Knowledgebase**: トラブルシューティング情報とFAQ
- **Techzone**: 技術的な詳細情報とアーキテクチャガイド
- **Omnissa Blogs**: 最新の技術情報とベストプラクティス

### 試験情報

- **Pearson VUE**: 試験予約と配信
- **試験ガイド**: OCE_Horizon_Exam_Guide.pdf（このリポジトリに含まれる）

## 認定情報

詳細および達成のための要件と推奨事項の完全なリストについては、[Omnissa Learning](https://www.omnissa.com/omnissa-learning)を参照してください。

## 更新履歴

この学習ガイドは、OCE-H試験ガイド（2025年版）に基づいて作成されています。試験ガイドの更新に伴い、このドキュメントも随時更新されます。
