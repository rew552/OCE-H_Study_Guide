# A2: Omnissa 製品ポートフォリオ / Omnissa Product Portfolio

## 概要 / Overview

Omnissa は 2024 年に Broadcom による VMware 買収に伴い、VMware の EUC（End-User Computing）事業部門が独立して設立された企業である。旧 VMware Workspace ONE および VMware Horizon 製品群を継承し、「Digital Work」をミッションとして掲げている。

Omnissa は以下の領域をカバーする製品・サービスを提供する：

- **仮想デスクトップ・アプリ配信**（VDI / DaaS）
- **統合エンドポイント管理**（Unified Endpoint Management）
- **デジタル従業員エクスペリエンス**（Digital Employee Experience）
- **プラットフォーム共通サービス**（ID 管理・分析・自動化・エッジセキュリティ）

---

## カテゴリ 1: Horizon（仮想デスクトップ・アプリ配信）

OCE-H 試験の直接的な対象。

| 製品名 | 説明 |
|--------|------|
| **Horizon 8** | オンプレミスの仮想デスクトップ・アプリ配信基盤。Connection Server を中核とし、Instant Clone / Full Clone デスクトッププール、RDSH ファーム（Published Desktop / App）を提供。Blast Extreme / PCoIP プロトコルをサポート |
| **Horizon Cloud Service** | DaaS（Desktop as a Service）として Horizon をクラウドで提供。Horizon Control Plane による管理。Azure / AWS / GCP 上で動作可能 |
| **Horizon Accelerator** | Horizon デプロイメントのマネージドサービス。Omnissa が監視・運用・最適化を代行 |
| **App Volumes** | アプリケーションをレイヤー化して配信・管理。Application / Package / Program の 3 層構造。Classic（ログイン時アタッチ）と On Demand（起動時アタッチ）の 2 方式。Writable Volume でユーザーデータ保持 |
| **Dynamic Environment Manager (DEM)** | ユーザープロファイル・環境設定・ポリシーの管理。DirectFlex によるログオン/ログオフ時の設定適用。Smart Policies による条件付きポリシー。Condition Sets のモジュラーアプローチ |

---

## カテゴリ 2: Workspace ONE（統合エンドポイント管理）

OCE-H 試験の直接的な出題対象ではないが、前提知識として資格要件に含まれる。

| 製品名 | 説明 |
|--------|------|
| **Workspace ONE UEM** | 統合エンドポイント管理（旧 AirWatch）。モバイル / デスクトップ / IoT デバイスの登録・管理・コンプライアンスポリシー・アプリ配信 |
| **Workspace ONE Intelligent Hub** | 従業員向け統合セルフサービスアプリ。アプリカタログ、SSO アクセス、通知 |
| **Workspace ONE Assist** | リモートサポートツール。画面共有・リモート制御・ファイル転送 |
| **Workspace ONE Experience Management** | デジタル従業員エクスペリエンスの測定・分析・改善。DEEM Agent によるテレメトリ収集 |
| **Workspace ONE Mobile Threat Defense** | モバイルデバイス向け脅威防御。フィッシング検出・脆弱性保護 |
| **Workspace ONE Tunnel** | Zero Trust VPN。Per-App VPN / Full Device VPN。UAG 上で動作 |
| **Workspace ONE Productivity Apps** | ビジネスアプリケーション（Boxer, Content, Web 等）へのセキュアアクセス |
| **Workspace ONE ITSM Connector** | ServiceNow 等の ITSM ツールとの統合。インシデント管理・サービスリクエスト自動化 |

---

## カテゴリ 3: Platform Services（プラットフォーム共通サービス）

Horizon と Workspace ONE の両方にまたがる共通サービス。

| 製品名 | 説明 |
|--------|------|
| **Omnissa Access** | ID プロバイダー（IdP）・SSO・条件付きアクセス。旧 VMware Identity Manager / Workspace ONE Access。Horizon の SAML Authenticator として使用。OCE-H 試験 Section 4.7.2 の対象 |
| **Omnissa Intelligence** | 分析・インサイト・自動化プラットフォーム。Experience Score / Custom Reports / Dashboards。OCE-H 試験 Section 4.7.3 の対象 |
| **Omnissa Freestyle Orchestrator** | ローコード/ノーコード IT 自動化プラットフォーム。ワークフローベースのデバイス管理・コンプライアンス自動化 |
| **Unified Access Gateway (UAG)** | エッジセキュリティゲートウェイ。Horizon エッジサービスと WS1 UEM サービス（Tunnel, Content Gateway, SEG）の両方をホスト。OCE-H 試験 Section 4.1.4 の対象 |
| **Omni** | AI アシスタント。管理者向けの自然言語によるインサイト・トラブルシューティング支援 |

---

## 製品間の関係 / Product Relationship

```
Omnissa Platform
├── Horizon Suite（VDI / DaaS）
│   ├── Horizon 8 / Horizon Cloud Service
│   ├── App Volumes
│   └── Dynamic Environment Manager (DEM)
├── Workspace ONE Suite（UEM）
│   ├── Workspace ONE UEM
│   ├── Intelligent Hub / Assist / Tunnel
│   ├── Mobile Threat Defense
│   └── Experience Management (DEEM)
├── Platform Services（共通）
│   ├── Omnissa Access（IdP / SSO）
│   ├── Omnissa Intelligence（分析 / 自動化）
│   ├── Freestyle Orchestrator（ワークフロー自動化）
│   └── Unified Access Gateway（エッジゲートウェイ）
└── Omni（AI）
```

Platform Services は Horizon Suite と Workspace ONE Suite の両方から共通で利用される。特に UAG は DMZ 上で Horizon のセキュアゲートウェイ機能と Workspace ONE の Tunnel / Content Gateway / SEG を同一アプライアンス上でホストする。Omnissa Access は両スイートに対して統合認証・SSO・条件付きアクセスを提供する。

---

## OCE-H 試験との関連マッピング / OCE-H Exam Mapping

| 製品 | 試験セクション | 関連度 |
|------|--------------|--------|
| Horizon 8 | 全セクション | 直接対象 |
| App Volumes | 4.1.8, 4.2 | 直接対象 |
| DEM | 4.1.7, 4.2 | 直接対象 |
| UAG | 4.1.4, 4.1.9 | 直接対象 |
| Omnissa Access | 4.7.2 | 直接対象 |
| Omnissa Intelligence | 4.7.3 | 直接対象 |
| Workspace ONE UEM | 資格要件のみ | 前提知識 |
| その他 | - | 試験範囲外 |

---

## 名称変遷 / Product Name History

旧名称からの変遷を整理する。試験問題や過去のドキュメントを参照する際に有用。

| 現在の名称 | 旧名称（VMware 時代） | さらに前の名称 |
|-----------|---------------------|---------------|
| Omnissa Horizon 8 | VMware Horizon 8 | VMware Horizon View |
| Omnissa App Volumes | VMware App Volumes | CloudVolumes |
| Omnissa DEM | VMware DEM | VMware UEM (User Environment Manager) |
| Omnissa Access | Workspace ONE Access | VMware Identity Manager (vIDM) |
| Omnissa Intelligence | Workspace ONE Intelligence | — |
| Workspace ONE UEM | Workspace ONE UEM | AirWatch |
| UAG | VMware UAG | — |

---

## 参考リンク / References

| リソース | URL |
|---------|-----|
| Omnissa 公式サイト | https://www.omnissa.com/ |
| Omnissa Docs | https://docs.omnissa.com/ |
| Omnissa TechZone | https://techzone.omnissa.com/ |
