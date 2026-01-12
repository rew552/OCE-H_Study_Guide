# 重要ポイントのまとめ

このドキュメントでは、OCE-H試験でよく出題される重要ポイントをまとめています。

## Section 1: Infrastructure Planning and Management

### Connection Server

- **高可用性**: 最小2台、推奨3-5台のConnection Server
- **ロードバランシング**: セッションアフィニティを有効化
- **ポート**: 443（HTTPS）、4001（JMS）
- **レプリケーション**: すべてのConnection Serverは同じバージョンである必要がある

### UAG

- **比率**: UAGとConnection Serverの1:1比率（ベストプラクティス）
- **ポート**: 443（HTTPS）、4172（PCoIP）、22443（Blast）
- **HA構成**: サードパーティロードバランサーまたはUAG HA
- **デプロイ方法**: Multi-NIC、PowerShell script、UI

### App Volumes

- **Manager**: 複数のManagerを登録して高可用性を実現
- **データベース**: SQL ServerまたはOracle
- **ストレージ**: NFS、SMB/CIFS、vSphereデータストア
- **レプリケーション**: パートナーとのレプリケーション設定

### DEM

- **ファイル共有**: SMB 3.0以上、高可用性構成（DFS推奨）
- **Management Console**: NoADモードもサポート
- **Smart Policies**: 条件セット（モジュラーアプローチ）
- **ADMXテンプレート**: インポートしてGPOで管理

### CPA

- **初期化**: 最初のポッドで一度だけ実行
- **グローバルLDAP**: フェデレーション全体で使用
- **ローカルLDAP**: 各ポッドで使用
- **Home Site**: ユーザーの位置に基づく設定

### アップグレード順序

1. Cloud Pod Orchestrator（CPA環境の場合）
2. Connection Server
3. UAG
4. Horizon Agent
5. App Volumes Agent
6. DEM Agent

### Recording Server

- **ユースケース**: コンプライアンス、セキュリティ監査、トレーニング
- **記録基準**: ローカルセッション、リモートセッション、グループベース

### FIPS 140-2

- **Connection Server**: FIPSモードでインストール
- **UAG**: FIPSモードでインストール
- **注意**: すべてのコンポーネントでFIPSモードを有効化する必要がある

### GPU

- **vGPU**: 複数のVMでGPUリソースを共有
- **DirectPath I/O**: 物理GPUを直接割り当て
- **vSGA**: ソフトウェアベースのGPU共有
- **VM密度**: GPUプロファイルに応じて調整

---

## Section 2: Desktop, Application, and Profile Management

### ゴールデンイメージ

- **OSOT**: OS Optimization Toolを使用して最適化
- **サービス**: 不要なサービスを無効化
- **レジストリ**: パフォーマンス関連のレジストリ設定
- **バージョン管理**: スナップショットでバージョン管理

### デスクトッププール

- **永続**: Full Clone、専用割り当て
- **非永続**: Instant Clone、フローティング割り当て
- **プロビジョニング**: Instant Cloneが推奨（Horizon 8）

### エンタイトルメント

- **ローカル**: 単一ポッド内でのエンタイトルメント
- **グローバル**: CPA環境で複数ポッドにまたがるエンタイトルメント
- **優先順位**: エンタイトルメントの優先順位を設定可能

### RDSHファーム

- **ロードバランシング**: セッションベース、リソースベース
- **セッション制限**: ホストあたりのセッション数を制限
- **ログイン性能**: ホスト側とネットワークの最適化

### App Volumes

- **AppStack**: 読み取り専用、複数のユーザー/マシンで共有
- **Writable Volume**: 読み書き可能、ユーザー/マシンごと
- **Application on Demand**: VM起動時に動的にアタッチ

### DEM

- **Smart Policies**: 条件付きポリシー
- **条件セット**: モジュラーアプローチで再利用可能
- **フォルダリダイレクション**: 大きなファイルをネットワーク共有にリダイレクト

### GPO

- **ADMXテンプレート**: Horizon用ADMXテンプレートをインポート
- **適用順序**: ローカル → サイト → ドメイン → OU
- **強制適用**: 子OUのGPOで上書きできない

---

## Section 3: Monitoring & Optimization

### 表示プロトコル最適化

- **Max Session Bandwidth**: レジストリで設定、セッションあたりの最大帯域幅を制限
- **Build-to-lossless**: 高品質な画像が必要な場合に使用、帯域幅を消費
- **Blast Protocol**: デフォルトプロトコル、BlastCodec、H.264、Adaptiveコーデック

### ゴールデンイメージ最適化

- **ローカルGPO**: レジストリ経由でパフォーマンス関連メトリックを設定
- **Windowsパフォーマンス設定**: ログインと継続的なパフォーマンスに影響
- **Login Monitor**: 継続的なログイン性能の監視と最適化

### プール容量計画

- **監視**: リソース制約（予測容量 vs 実際の容量）を監視
- **調整**: プール設定を調整
- **ボトルネック**: CPU、メモリ、ディスク、ネットワークのボトルネックを特定

---

## Section 4: Troubleshooting

### Boot StormとLogon Storm

- **Boot Storm**: 多数のVMが同時に起動、ストレージIOPSが急増
- **Logon Storm**: 多数のユーザーが同時にログオン、認証サーバーの負荷
- **対策**: 段階的な起動、ストレージの最適化、ログオン時間の分散

### ボトルネックの特定

- **CPU**: ゲスト内のCPU使用率が90%以上
- **メモリ**: ゲスト内のメモリ使用率が95%以上
- **GPU**: 小さすぎるGPUプロファイルが使用された場合

### Global Entitlements

- **依存関係**: 初期設定（プロトコル設定など）の依存関係
- **トラブルシューティング**: Imvutilコマンドで状態確認
- **プロトコル設定**: 各ポッドで同じ設定である必要がある

### グラフィックドライバー

- **GPU**: vGPUドライバーの確認と更新
- **Non-GPU**: ソフトウェアレンダリングのドライバー
- **VMレベル**: VMレベルでのドライバー問題を特定

### Instant Cloneデバッグ

- **有効化**: レジストリでInstant Cloneデバッグモードを有効化
- **ログ**: `vdm-instantclone.log`で詳細なログを確認

---

## Section 5: Security & Compliance

### SSL証明書

- **生成**: CSRを生成して申請
- **更新**: すべてのConnection Serverで同時に更新
- **証明書チェーン**: 中間証明書を含む完全なチェーン

### MFA

- **SAML**: SAML 2.0認証、Omnissa Access統合
- **RADIUS**: RADIUS認証、既存のRADIUSサーバーを使用
- **RSA**: RSA SecurID
- **スマートカード**: 証明書ベース認証
- **二要素認証**: CSとUAGを使用（証明書、SAML、RADIUS）

### データ保護

- **クリップボード**: 無効化、有効化、一方向（Client to Server、Server to Client）
- **CDR**: 無効化、有効化、読み取り専用
- **USBリダイレクション**: 無効化、有効化、ホワイトリスト、ブラックリスト
- **設定場所**: Horizon Console、DEM/GPO

---

## Section 6: Scale and Recovery

### スケーリング

- **Connection Server**: CCUに基づいてサイジング
- **App Volumes**: Managerの追加と登録
- **DEM**: ファイル共有の追加、Management Consoleの追加

### CPA

- **初期化**: 最初のポッドで一度だけ実行
- **Pod参加**: Horizon ConsoleでPodをフェデレーションに参加
- **Global Entitlement**: プールをGlobal Entitlementに追加
- **Home Site**: Imvutilコマンドで設定
- **Imvutil**: CPA環境の変更とメンテナンス

### 災害復旧

- **Connection Server**: 設定のエクスポート、データベースのバックアップ
- **App Volumes**: HAオプション（複数Manager、高可用性データベース）
- **DEM**: HAオプション（複数ファイル共有、Management Consoleの冗長化）

---

## Section 7: Automation & Integration

### プール管理の自動化

- **API**: REST APIを使用
- **認証**: OAuth 2.0または基本認証
- **機能**: プールの作成、更新、削除

### Omnissa Access統合

- **認証ポリシー**: Omnissa Accessで実装
- **SAML Authenticator**: Horizon Consoleで設定
- **SSO**: Connection Server設定でSSOを有効化
- **Horizon設定**: Omnissa Accessコンソールで設定

### Omnissa Intelligence統合

- **Edge Gateway**: デプロイしてSubscription接続
- **DEEMエージェント**: Horizon Agent VMにインストール
- **有効化**: connect.Omnissa.com → Intelligence → Marketplace → Solutions → Experience Management → Virtual Desktop & Appsタイルを有効化

---

## 暗記すべき数値

### ポート番号

- **Connection Server**: 443（HTTPS）、4001（JMS）
- **UAG**: 443（HTTPS）、4172（PCoIP）、22443（Blast）、9443（管理）
- **Horizon Agent**: 4172（PCoIP）、22443（Blast）、3389（RDP）

### サイジング

- **Connection Server**: 2,000 CCU/Connection Server（目安）
- **UAG**: 2,000 CCU/UAG（目安）、1:1比率でConnection Serverと統合
- **RDSH**: 50-100セッション/ホスト（標準的なオフィス作業）

### タイムアウト

- **アイドルタイムアウト**: 30分（標準環境）、15分（セキュリティ重視）
- **最大セッション時間**: 8時間（標準環境）、4時間（セキュリティ重視）

---

## 試験でよく出題される項目

1. **Connection Serverの高可用性構成**: レプリケーショングループ、ロードバランシング
2. **UAGのデプロイ**: Multi-NIC vs Single-NIC、PowerShell vs UI
3. **CPA**: 初期化、Pod参加、Global Entitlement、Home Site
4. **App Volumes**: Managerの追加、レプリケーション、Storage Access Mode
5. **DEM**: ファイル共有、Smart Policies、条件セット
6. **アップグレード順序**: 依存関係と順序
7. **トラブルシューティング**: Boot Storm、Logon Storm、ボトルネック
8. **MFA**: SAML、RADIUS、RSA、スマートカード
9. **データ保護**: クリップボード、CDR、USBリダイレクション
10. **Omnissa統合**: Access、Intelligence

---

## まとめ

これらの重要ポイントを理解し、暗記することで、OCE-H試験の準備が整います。実環境での経験と組み合わせることで、より深い理解が得られます。
