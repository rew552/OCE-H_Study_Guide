# A3: Omnissa ライセンス体系 / Omnissa Licensing Overview

## 概要 / Overview

本資料では Omnissa 製品群のライセンス体系を全体的に整理する。Horizon 8 のライセンス詳細（ライセンスタイプ、使用モデル、混在ルール、Edge Gateway デプロイ等）については [Section 1.5: Manage Licenses and Deploy Edge Gateway](../Section1_Infrastructure_Planning_and_Management/1.05_Licenses_Edge_Gateway.md) を参照のこと。

---

## 1. Omnissa ライセンス体系の全体像 / Licensing Framework

Omnissa の製品ラインは大きく 3 つのライセンス体系に分類される。

```
Omnissa Licensing
├── Horizon Suite（VDI / DaaS）
│   ├── Horizon Standard / Standard Plus / Enterprise Plus
│   ├── Horizon Apps Standard / Apps Enterprise
│   ├── Horizon for Linux
│   ├── App Volumes（Standard / Advanced）
│   └── DEM（Standard / Enterprise）
├── Workspace ONE Suite（UEM / Digital Workspace）
│   ├── Standard / Advanced / Enterprise
│   └── Enterprise for VDI
└── Platform Services（共通サービス）
    ├── Omnissa Access — スイートに含まれる or 個別購入
    ├── Omnissa Intelligence — スイートに含まれる or Subscription 付属
    └── UAG — 追加ライセンス不要
```

- **Horizon Suite**: 仮想デスクトップ・アプリケーション配信（VDI / DaaS）向けのライセンス
- **Workspace ONE Suite**: 統合エンドポイント管理（UEM）・デジタルワークスペース向けのライセンス
- **Platform Services**: Omnissa Access、Intelligence、UAG 等の共通サービス。各スイートに含まれるか、単体で購入可能

---

## 2. Horizon Suite ライセンス / Horizon Suite Licensing

Horizon 8 のライセンスタイプ（Perpetual / Term / Plus SaaS Subscription / Universal SaaS Subscription）、使用モデル（Named User / CCU）、および管理手順の詳細は [Section 1.5](../Section1_Infrastructure_Planning_and_Management/1.05_Licenses_Edge_Gateway.md) を参照。

### 2.1 ライセンスタイプ / License Types（概要）

| ライセンスタイプ / Type         | 提供形態 / Model           | キー管理 / Key Management       |
| ------------------------------- | -------------------------- | ------------------------------- |
| **Perpetual**                   | 永久ライセンス（買い切り） | ライセンスキー手動入力          |
| **Term**                        | 期間ライセンス（1年/3年）  | ライセンスキー手動入力          |
| **Plus SaaS Subscription**      | SaaS サブスクリプション    | Horizon Edge Gateway 経由で自動 |
| **Universal SaaS Subscription** | SaaS サブスクリプション    | Horizon Edge Gateway 経由で自動 |

→ 詳細（猶予期間、混在ルール、restricted mode 等）: [Section 1.5](../Section1_Infrastructure_Planning_and_Management/1.05_Licenses_Edge_Gateway.md)

### 2.2 使用モデル / Usage Models

| モデル / Model                      | 対象 / Target Use Case                   | カウント方法 / Counting                         |
| ----------------------------------- | ---------------------------------------- | ----------------------------------------------- |
| **Named User (NU)**                 | 全従業員が常時アクセスする環境           | エンタイトルメント + 実際のログインの組み合わせ |
| **Concurrent Connected User (CCU)** | シフトワーカー・学生等のタイムシェア環境 | ある時点で接続中のユーザー数                    |

→ カウント方法の詳細: [Section 1.5](../Section1_Infrastructure_Planning_and_Management/1.05_Licenses_Edge_Gateway.md)

### 2.3 Horizon エディション（バンドル） / Horizon Editions

エディションによって含まれる製品構成が異なる。

| エディション / Edition      | 含まれる製品 / Included Products                                        | 主な対象 / Target                                           |
| --------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------- |
| **Horizon Standard**        | Horizon 8 (Connection Server, Agent, Client), vSphere for Desktop       | 基本的な VDI 環境 / Basic VDI                               |
| **Horizon Standard Plus**   | Standard + App Volumes Standard                                         | アプリ配信が必要な環境 / VDI with app delivery              |
| **Horizon Enterprise Plus** | Standard Plus + App Volumes Advanced + DEM + ThinApp + vSAN for Desktop | フル機能の大規模環境 / Full-featured enterprise VDI         |
| **Horizon for Linux**       | Linux デスクトップ向け / Linux desktop                                  | Linux VDI                                                   |
| **Horizon Apps Standard**   | RDSH Published App のみ / RDSH Published Apps only                      | アプリケーション配信専用 / App delivery only                |
| **Horizon Apps Enterprise** | Apps Standard + App Volumes Advanced + DEM                              | フル機能のアプリケーション配信 / Full-featured app delivery |

> **注**: エディション構成は変更される可能性がある。最新情報は [Omnissa 公式サイト](https://www.omnissa.com/) を確認すること。

### 2.4 App Volumes エディション / App Volumes Editions

| エディション / Edition | 機能 / Features                                                                                      |
| ---------------------- | ---------------------------------------------------------------------------------------------------- |
| **Standard**           | Application パッケージの配信（Classic モード） / Application package delivery (Classic mode)         |
| **Advanced**           | Standard + Writable Volumes + Apps on Demand + ThinApp 統合 / Standard + Writable Volumes + Apps on Demand + ThinApp integration |

- App Volumes Standard は Horizon Standard Plus 以上に含まれる
- App Volumes Advanced は Horizon Enterprise Plus / Horizon Apps Enterprise に含まれる
- 単体購入も可能

### 2.5 DEM ライセンス / DEM Licensing

| エディション / Edition | 機能 / Features                                                                                   |
| ---------------------- | ------------------------------------------------------------------------------------------------- |
| **DEM Standard**       | 基本的なプロファイル管理（DirectFlex、FlexEngine） / Basic profile management                     |
| **DEM Enterprise**     | 全機能: Smart Policies, Application Profiler, ADMX-based Settings, Condition Sets / Full features |

- DEM は Horizon Enterprise Plus に含まれる
- 単体ライセンスとしても提供（DEM Standard / DEM Enterprise）
- Horizon Standard / Standard Plus には DEM は含まれないため、必要に応じて単体購入が必要

---

## 3. Workspace ONE ライセンス / Workspace ONE Licensing

### 3.1 Workspace ONE エディション / Workspace ONE Editions

| エディション / Edition | 含まれる主要機能 / Key Features                                                                      | 価格帯（参考）/ Price (Reference) |
| ---------------------- | ---------------------------------------------------------------------------------------------------- | --------------------------------- |
| **Standard**           | UEM 基本機能、デバイス管理、アプリ配信 / Basic UEM, device management, app delivery                  | $3.78/device/month                |
| **Advanced**           | Standard + Intelligent Hub、Access（Basic）、Tunnel / Standard + Hub, Access (Basic), Tunnel         | $6/device/month                   |
| **Enterprise**         | Advanced + Intelligence、Freestyle、Experience Management / Advanced + Intelligence, Freestyle, DEEM | $10/device/month                  |
| **Enterprise for VDI** | Enterprise + Horizon 統合 / Enterprise + Horizon integration                                         | $20/device/month                  |

> **注**: 価格は参考値であり、変動する。最新の価格は Omnissa の営業担当または公式サイトで確認すること。

### 3.2 ライセンスモデル / Licensing Models

| モデル / Model       | 説明 / Description                                                                                   |
| -------------------- | ---------------------------------------------------------------------------------------------------- |
| **Per Device**       | デバイス単位のライセンス。1 デバイスに対して 1 ライセンスを消費 / One license per managed device     |
| **Per User**         | ユーザー単位のライセンス。1 ユーザーが複数デバイスを管理する場合に有利 / One license per user, covers multiple devices |
| **SaaS（クラウド）** | Omnissa がホストするクラウドサービスとして利用 / Cloud-hosted by Omnissa                             |
| **On-Premises**      | 自社データセンターにデプロイして利用 / Self-hosted deployment                                        |

### 3.3 Workspace ONE エディション別の機能マッピング / Feature Mapping

| 機能 / Feature               | Standard | Advanced | Enterprise |
| ---------------------------- | :------: | :------: | :--------: |
| UEM（デバイス管理）          | ○        | ○        | ○          |
| アプリ配信                   | ○        | ○        | ○          |
| Intelligent Hub              | —        | ○        | ○          |
| Omnissa Access（Basic）      | —        | ○        | ○          |
| Workspace ONE Tunnel         | —        | ○        | ○          |
| Omnissa Intelligence         | —        | —        | ○          |
| Freestyle Orchestrator       | —        | —        | ○          |
| Experience Management (DEEM) | —        | —        | ○          |
| Mobile Threat Defense        | —        | —        | ○          |

---

## 4. Platform Services のライセンス / Platform Services Licensing

Platform Services は Horizon Suite および Workspace ONE Suite の両方から利用される共通サービスである。

| サービス / Service               | ライセンス形態 / Licensing                                                                           | 備考 / Notes                                                                                        |
| -------------------------------- | ---------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| **Omnissa Access**               | Workspace ONE Advanced 以上に含まれる。Horizon との統合で使用する場合は Horizon + Access の個別ライセンスも可能 | IdP / SSO / 条件付きアクセスを提供。旧 Workspace ONE Access / VMware Identity Manager               |
| **Omnissa Intelligence**         | Workspace ONE Enterprise に含まれる。Horizon Subscription（Plus / Universal）では自動的に利用可能    | 分析・レポート・自動化プラットフォーム                                                              |
| **UAG (Unified Access Gateway)** | Horizon / Workspace ONE の各ライセンスに含まれる（追加ライセンス不要）                               | DMZ に配置するエッジセキュリティゲートウェイ。Horizon と Workspace ONE の両方のサービスをホスト可能 |

---

## 5. Horizon + Workspace ONE の統合ライセンス / Integrated Licensing

### 5.1 Workspace ONE Enterprise for VDI

Workspace ONE Enterprise + Horizon Enterprise Plus を統合したバンドルライセンス。

| 項目 / Item      | 内容 / Details                                                                     |
| ---------------- | ---------------------------------------------------------------------------------- |
| **含まれる製品** | Workspace ONE Enterprise の全機能 + Horizon Enterprise Plus の全機能               |
| **対象**         | VDI 環境とエンドポイント管理を統合的に運用する大規模組織                           |
| **主なメリット** | 単一の契約・サポート窓口、Access / Intelligence の共有利用、ライセンス管理の簡素化 |

### 5.2 個別購入 vs. 統合バンドル / Separate vs. Integrated Bundle

| 比較項目 / Criteria       | 個別購入 / Separate                                 | 統合バンドル (Enterprise for VDI)                                      |
| ------------------------- | --------------------------------------------------- | ---------------------------------------------------------------------- |
| **契約**                  | Horizon と Workspace ONE で個別                     | 単一契約                                                               |
| **サポート**              | 製品ごとに個別問い合わせ                            | 統合サポート                                                           |
| **Access / Intelligence** | 製品ごとに個別ライセンスが必要な場合あり            | 共有利用（追加ライセンス不要）                                         |
| **コスト**                | 機能要件に応じて最適化可能                          | 両スイートのフル機能を含むため、全機能を使用する場合はコスト効率が高い |
| **適するケース**          | Horizon のみ、または Workspace ONE のみ使用する場合 | 両方のスイートを全社的に導入する場合                                   |

---

## 6. ライセンスに関する注意事項 / Licensing Notes

### 6.1 Broadcom 買収後のライセンス移行 / Post-Broadcom License Transition

- 2024 年の Broadcom による VMware 買収に伴い、EUC 事業部門は Omnissa として独立
- 既存の VMware ライセンスキーは Omnissa 形式への移行が必要
- **Horizon 2412 以降**: Omnissa ライセンスモジュールの新形式キーが必須。60 日の猶予期間内に移行すること
- ライセンスキーの取得先は VMware Customer Connect から Omnissa Customer Connect ポータルに変更

### 6.2 Perpetual ライセンスの新規販売 / Perpetual License Availability

- Perpetual（永久）ライセンスの新規販売は終了傾向にあり、Subscription モデルへの移行が推奨されている
- 既存の Perpetual ライセンス保持者は引き続きサポート契約の更新が可能（SnS: Support and Subscription）

### 6.3 vSphere for Desktop ライセンス / vSphere for Desktop Licensing

- vSphere for Desktop は Horizon バンドル（Standard 以上）に含まれる
- Horizon VDI 用途では vSphere Standard / Enterprise Plus の個別購入は不要
- vSphere for Desktop ライセンスには猶予期間がない（Term License 失効時、即座に制限モードに移行）

### 6.4 vSAN for Desktop ライセンス / vSAN for Desktop Licensing

- vSAN for Desktop は Horizon Enterprise Plus に含まれる
- VDI ストレージに vSAN を使用する場合、Enterprise Plus エディションを選択することで追加コストなしで利用可能

---

## ライセンス体系サマリー / Licensing Summary

```
┌─────────────────────────────────────────────────────────────┐
│                    Workspace ONE Enterprise for VDI          │
│  ┌───────────────────────────┐ ┌───────────────────────────┐ │
│  │   Workspace ONE Enterprise │ │  Horizon Enterprise Plus  │ │
│  │  ┌───────────────────────┐│ │ ┌───────────────────────┐ │ │
│  │  │ UEM + Hub + Tunnel    ││ │ │ Horizon 8             │ │ │
│  │  │ Access + Intelligence ││ │ │ App Volumes Advanced  │ │ │
│  │  │ Freestyle + DEEM      ││ │ │ DEM + ThinApp         │ │ │
│  │  │ Mobile Threat Defense ││ │ │ vSphere/vSAN for DT   │ │ │
│  │  └───────────────────────┘│ │ └───────────────────────┘ │ │
│  └───────────────────────────┘ └───────────────────────────┘ │
│              ┌─────────────────────────────┐                 │
│              │    Platform Services        │                 │
│              │  Access / Intelligence / UAG │                 │
│              └─────────────────────────────┘                 │
└─────────────────────────────────────────────────────────────┘
```

---

## 参考リンク / References

| リソース / Resource                    | URL                                                                                                  |
| -------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| Omnissa 公式サイト                     | https://www.omnissa.com/                                                                             |
| Omnissa Docs                           | https://docs.omnissa.com/                                                                            |
| Omnissa Licensing FAQ                  | https://www.omnissa.com/licensing/                                                                   |
| Omnissa Customer Connect               | https://customerconnect.omnissa.com/                                                                 |
| Section 1.5: Licenses and Edge Gateway | [1.05_Licenses_Edge_Gateway.md](../Section1_Infrastructure_Planning_and_Management/1.05_Licenses_Edge_Gateway.md) |

x