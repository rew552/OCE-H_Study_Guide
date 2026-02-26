# Appendix A1: Workspace ONE UEM 概要と Horizon 統合

> **本ファイルの位置づけ**: 本ファイルは Appendix（補足資料）である。試験ガイドの最小資格要件（Section 3.4）に「Has experience integrating Omnissa Horizon Suite with Omnissa Workspace ONE UEM」と記載されているが、試験セクション（4.1〜4.7）の objective には UEM を直接テストする項目はない。UAG のサイジング、デバイス管理、条件付きアクセスなどの文脈で前提知識として登場するため、ここに整理する。

---

## 1. Workspace ONE UEM とは

### 1.1 名称の変遷

| 時期 | 名称 |
|------|------|
| 〜2014 | AirWatch |
| 2014〜2023 | VMware Workspace ONE UEM |
| 2024〜 | **Omnissa Workspace ONE UEM** |

### 1.2 役割

Workspace ONE UEM は**統合エンドポイント管理（Unified Endpoint Management）**プラットフォームである。モバイル（iOS / Android）、デスクトップ（Windows / macOS / Linux）、IoT デバイスなど多様なエンドポイントを一元的に管理する。

### 1.3 主要機能

| 機能 | 説明 |
|------|------|
| **Device Enrollment** | デバイスの登録・認証。MDM プロファイルの配布 |
| **Compliance Policies** | デバイスの準拠状態を評価し、非準拠時のアクション（通知、隔離、ワイプ等）を実行 |
| **App Delivery** | 内部アプリ・パブリックアプリ・購入済みアプリの配信と管理 |
| **Profile Management** | Wi-Fi、VPN、メール、パスコードなどの設定プロファイルを配布 |
| **Sensors & Scripts** | エンドポイントのデータ収集（Sensors）と自動構成（Scripts） |
| **Assist** | リモートサポート（画面共有、リモートコマンド実行） |

---

## 2. Horizon との統合ポイント

以下に、試験セクションで UEM の知識が前提となる箇所を整理する。

### 2.1 UAG でのエッジサービス（Section 4.1.4 関連）

UAG は Horizon エッジサービスだけでなく、Workspace ONE UEM のエッジサービスもホストできる。

**UEM 関連のエッジサービス**:

| サービス | 役割 |
|---------|------|
| **VMware Tunnel** | デバイスからイントラネットリソースへのアプリ単位 VPN（Per-App VPN） |
| **Content Gateway** | 社内コンテンツリポジトリ（SharePoint, ファイルサーバー等）へのセキュアアクセス |
| **Secure Email Gateway (SEG)** | メール通信のセキュリティゲートウェイ |

**UAG サイジングと UEM サービスの関係**:

| UAG サイズ | vCPU | メモリ | Horizon 用途 | UEM 用途 |
|-----------|------|--------|-------------|---------|
| Standard | 2 | 4 GB | 最大 2,000 Horizon セッション | 最大 10,000 同時接続（モバイル） |
| Large | 4 | 16 GB | — | 50,000 超の同時接続。Tunnel + Content Gateway + SEG を同一アプライアンスで運用可能 |
| Extra Large | 8 | 32 GB | 最大 4,000 Horizon セッション（2412 以降） | Tunnel + Content Gateway + SEG を同一アプライアンスで運用可能 |

**分離の推奨**: 大規模環境では、Horizon エッジサービスと UEM エッジサービスを**別の UAG インスタンス**に分離することが推奨される。これにより、サービス間のリソース競合を回避し、障害の影響範囲を限定できる。

**Cascade Mode 対応**: Tunnel および Content Gateway はダブル DMZ 構成の Cascade Mode に対応している。

### 2.2 Enrollment Server / True SSO（Section 4.1.1, 4.7.2 関連）

UEM 管理デバイスから Horizon への証明書ベース認証と SSO を実現する構成:

- UEM がデバイスに**クライアント証明書**を配布
- デバイスは Horizon / Omnissa Access への認証時にこの証明書を提示
- Enrollment Server + Microsoft CA による **True SSO** と組み合わせることで、パスワード入力なしの完全な SSO を実現

### 2.3 条件付きアクセス（Section 4.5.1, 4.7.2 関連）

UEM のデバイスコンプライアンス情報を Horizon のアクセス制御に活用するフロー:

1. **UEM Compliance Engine** がデバイスのポリシー準拠状態を継続的に評価
2. コンプライアンス情報を **Omnissa Access**（条件付きアクセスエンジン）に連携
3. Omnissa Access がアクセスポリシーに基づき Horizon リソースへのアクセスを許可/拒否

**非準拠時の動作例**:
- OS バージョンが古い → Horizon へのアクセスを拒否
- 暗号化が無効 → アクセスを拒否し、準拠手順を案内
- デバイスが脱獄/root 化 → 即時アクセス拒否

### 2.4 App Volumes の物理エンドポイント配信（Section 4.2 関連）

App Volumes は VDI 環境だけでなく、物理エンドポイントへのアプリ配信もサポートする:

- **MSI Wrapping**: App Volumes パッケージ（VHD）を MSI インストーラーとしてラップ
- UEM のアプリ配信インフラ（App Catalog）を使用して、ラップされたパッケージを物理端末に配布
- 物理デスクトップと VDI でアプリ管理を統一

### 2.5 Horizon 管理デバイスへの UEM 統合（TechZone ガイドライン）

Omnissa TechZone のガイドラインでは、UEM を Horizon デスクトップ（Full Clone / Golden Image）に統合した場合、以下の管理機能が利用可能:

| 機能 | 説明 |
|------|------|
| OS Updates | Horizon デスクトップの OS パッチ管理 |
| Software Deployment | ソフトウェアの配信・インストール |
| Profiles & Baselines | セキュリティベースラインの適用 |
| Sensors | デバイス状態のデータ収集 |
| Scripts | 自動構成スクリプトの実行 |
| Intelligence | 使用状況・パフォーマンスの分析レポート |
| Assist | リモートサポート |

> **注意**: Instant Clone は再起動時にリセットされるため、UEM 管理との互換性に制限がある。Full Clone および長期稼働の Instant Clone（persistent）が主な対象である。

---

## 3. UEM の主要コンポーネント（Horizon 統合に関連するもの）

| コンポーネント | 役割 |
|--------------|------|
| **UEM Console** | Web ベースの管理コンソール。デバイス管理・ポリシー設定・アプリ配信を一元操作 |
| **Device Services** | デバイスの登録（Enrollment）・通信・コマンド配信を処理するサーバー |
| **Compliance Engine** | デバイスのポリシー準拠状態をリアルタイムに評価。非準拠時のアクション（通知、隔離、ワイプ）をトリガー |
| **App Catalog** | 社内アプリ・パブリックアプリの配信ポータル |
| **VMware Tunnel** | Per-App VPN を提供するゲートウェイサービス。UAG 上で動作 |
| **Content Gateway** | 社内コンテンツリポジトリへのプロキシ。UAG 上で動作 |

---

## 4. UAG での UEM サービスの位置づけ

### 4.1 サービス共存と分離の判断

| 構成 | 説明 | 推奨シナリオ |
|------|------|------------|
| **共存** | 1 つの UAG で Horizon + UEM サービスを同時ホスト | 小規模環境、PoC |
| **分離** | Horizon 用 UAG セットと UEM 用 UAG セットを分離 | **大規模環境（推奨）** |

**分離を推奨する理由**:
- Horizon と UEM でリソース要件が異なる（Horizon: Standard、UEM: Large / Extra Large）
- 障害ドメインの分離（UEM サービスの問題が Horizon セッションに影響しない）
- 独立したメンテナンスウィンドウの確保

### 4.2 UAG サイジング再掲（サービス別推奨）

| サービス用途 | 推奨サイズ | vCPU | メモリ | 備考 |
|------------|----------|------|--------|------|
| Horizon エッジサービス | Standard | 2 | 4 GB | 最大 2,000 セッション |
| Horizon エッジサービス（大規模） | Extra Large | 8 | 32 GB | 最大 4,000 セッション（2412 以降） |
| UEM サービス（Tunnel, CGW, SEG） | Large | 4 | 16 GB | 50,000 超の同時接続 |
| UEM サービス（大規模） | Extra Large | 8 | 32 GB | Tunnel + CGW + SEG 同時運用 |

---

## 5. Horizon 統合時の認証フロー

### 5.1 UEM 管理デバイスから Horizon への認証フロー

```
UEM 管理デバイス
    │
    ▼
[1] UEM Compliance Engine: デバイスのポリシー準拠を確認
    │
    ▼
[2] Omnissa Access: 条件付きアクセスポリシーを評価
    │  ├─ デバイスコンプライアンス（UEM 連携）
    │  ├─ ネットワーク範囲
    │  └─ 認証強度
    │
    ▼
[3] SAML 認証: Access が IdP として SAML アサーションを発行
    │
    ▼
[4] Connection Server: SAML アサーションを検証しセッションを確立
    │
    ▼
[5] True SSO（任意）: Enrollment Server が短期証明書を発行し Windows ログイン
    │
    ▼
[6] Horizon Agent: デスクトップ / アプリセッション開始
```

### 5.2 関連する試験セクション

| フローのステップ | 関連セクション | 関連トピック |
|---------------|-------------|-------------|
| [1] UEM コンプライアンス | — | Appendix（本ファイル） |
| [2] 条件付きアクセス | 4.7.2 | Omnissa Access Integration |
| [3] SAML 認証 | 4.5.1, 4.7.2 | MFA, Access Integration |
| [4] Connection Server | 4.1.1 | Connection Servers |
| [5] True SSO | 4.1.1, 4.7.2 | Enrollment Servers, Access Integration |
| [6] Horizon Agent | 4.2 | Desktop Pools |

---

## 参考リソース

| リソース | URL |
|---------|-----|
| Omnissa Docs — Workspace ONE UEM | https://docs.omnissa.com/ |
| TechZone — WS1 UEM Integration with Horizon | https://techzone.omnissa.com/resource/omnissa-workspace-one-unified-endpoint-management-integration-horizon |
| TechZone — Configuring Content Gateway Edge Service | https://techzone.omnissa.com/configuring-edge-services-vmware-unified-access-gateway-vmware-workspace-one-operational-tutorial |
