# クイックリファレンス

このドキュメントは、OCE-H試験対策のための重要な数値、設定値、制限値、ログファイルの場所などを一覧にしたクイックリファレンスです。

## ポート番号一覧

### Connection Server

| ポート | プロトコル | 用途 | 方向 |
|--------|-----------|------|------|
| 443 | HTTPS | 管理コンソール、クライアント接続 | 受信 |
| 4001 | TCP | JMS（Connection Server間通信） | 内部通信 |
| 4100 | TCP | View Composer（リンククローン用、Horizon 8では非推奨） | 内部通信 |

### Unified Access Gateway (UAG)

| ポート | プロトコル | 用途 | 方向 |
|--------|-----------|------|------|
| 443 | HTTPS | クライアント接続、管理 | 受信 |
| 4172 | TCP/UDP | PCoIPトンネル | 受信 |
| 22443 | TCP | Blast Protocolトンネル | 受信 |
| 9443 | HTTPS | 管理インターフェース | 受信 |
| 8443 | HTTPS | 内部管理（オプション） | 内部通信 |

:::important
UAGのHA構成では、ロードバランサーがこれらのポートを監視する必要があります。
:::

### Horizon Agent

| ポート | プロトコル | 用途 | 方向 |
|--------|-----------|------|------|
| 4172 | TCP/UDP | PCoIP | 受信 |
| 22443 | TCP | Blast Protocol | 受信 |
| 3389 | TCP | RDP | 受信 |
| 9427 | TCP | Agent管理 | 内部通信 |

### Enrollment Server

| ポート | プロトコル | 用途 | 方向 |
|--------|-----------|------|------|
| 443 | HTTPS | デバイス登録、管理 | 受信 |

### vCenter Server

| ポート | プロトコル | 用途 | 方向 |
|--------|-----------|------|------|
| 443 | HTTPS | API、管理コンソール | 受信 |
| 902 | TCP/UDP | ESXiホストハートビート | 内部通信 |

### App Volumes Manager

| ポート | プロトコル | 用途 | 方向 |
|--------|-----------|------|------|
| 443 | HTTPS | 管理コンソール、API | 受信 |
| 2049 | TCP/UDP | NFS（ストレージ接続） | 内部通信 |
| 445 | TCP | SMB（ストレージ接続） | 内部通信 |

### DEM (Dynamic Environment Manager)

| ポート | プロトコル | 用途 | 方向 |
|--------|-----------|------|------|
| 445 | TCP | SMB（ファイル共有） | 内部通信 |
| 135 | TCP | RPC | 内部通信 |
| 49152-65535 | TCP | RPC動的ポート範囲 | 内部通信 |

### RDSH (Remote Desktop Session Host)

| ポート | プロトコル | 用途 | 方向 |
|--------|-----------|------|------|
| 3389 | TCP | RDP | 受信 |
| 49152-65535 | TCP | RDPセッション用の動的ポート範囲 | 受信 |

### Recording Server

| ポート | プロトコル | 用途 | 方向 |
|--------|-----------|------|------|
| 443 | HTTPS | 管理コンソール | 受信 |
| 902 | TCP | 録画データ転送 | 内部通信 |

### Edge Gateway

| ポート | プロトコル | 用途 | 方向 |
|--------|-----------|------|------|
| 443 | HTTPS | Omnissa Intelligenceへの接続 | 送信 |

## タイムアウト設定の推奨値

### 標準環境

| 設定項目 | 推奨値 | 説明 |
|---------|--------|------|
| アイドルタイムアウト | 30分（1800秒） | アイドル状態が続いた場合のセッション切断時間 |
| 最大セッション時間 | 8時間（28800秒） | セッションの最大継続時間 |
| 切断後のログオフ | 10分（600秒） | 切断されたセッションをログオフするまでの時間 |

### セキュリティ重視環境

| 設定項目 | 推奨値 | 説明 |
|---------|--------|------|
| アイドルタイムアウト | 15分（900秒） | より短いタイムアウトでセキュリティを強化 |
| 最大セッション時間 | 4時間（14400秒） | セッション時間を制限 |
| 切断後のログオフ | 5分（300秒） | より迅速なログオフ |

### 開発者環境

| 設定項目 | 推奨値 | 説明 |
|---------|--------|------|
| アイドルタイムアウト | 60分（3600秒） | 開発作業を考慮した長めのタイムアウト |
| 最大セッション時間 | 12時間（43200秒） | 長時間の開発作業に対応 |
| 切断後のログオフ | 30分（1800秒） | 作業の継続を考慮 |

## パフォーマンス目標値

### CPU

| メトリック | 目標値 | 警告レベル | クリティカルレベル |
|-----------|--------|-----------|------------------|
| CPU使用率 | 80%以下 | 80-90% | 90%以上 |
| CPU待機時間 | 最小限 | - | 高い待機時間が継続 |

### メモリ

| メトリック | 目標値 | 警告レベル | クリティカルレベル |
|-----------|--------|-----------|------------------|
| メモリ使用率 | 90%以下 | 90-95% | 95%以上 |
| ページング | 発生しない | わずかに発生 | 頻繁に発生 |
| スワップ使用 | 最小限 | 使用中 | 高い使用率 |

### ディスク

| メトリック | 目標値 | 警告レベル | クリティカルレベル |
|-----------|--------|-----------|------------------|
| ディスクレイテンシ | 20ms以下 | 20-50ms | 50ms以上 |
| 読み取りIOPS | データストア容量内 | - | 容量超過 |
| 書き込みIOPS | データストア容量内 | - | 容量超過 |
| ディスク使用率 | 80%以下 | 80-90% | 90%以上 |

:::warning
Boot StormやLogon Stormが発生する場合、ディスクIOPSが大幅に増加します。適切なストレージ設計が必要です。
:::

### ネットワーク

| メトリック | 目標値（LAN） | 目標値（WAN） | 警告レベル | クリティカルレベル |
|-----------|-------------|-------------|-----------|------------------|
| ネットワークレイテンシ | 1ms以下 | 150ms以下 | 150-200ms | 200ms以上 |
| パケットロス | 1%以下 | 1%以下 | 1-5% | 5%以上 |
| 帯域幅使用率 | 80%以下 | 80%以下 | 80-90% | 90%以上 |

### セッションパフォーマンス

| メトリック | 目標値 | 警告レベル | クリティカルレベル |
|-----------|--------|-----------|------------------|
| ログオン時間 | 30秒以下 | 30-60秒 | 60秒以上 |
| フレームレート | 30fps以上 | 20-30fps | 20fps以下 |
| RTT (Round Trip Time) | 150ms以下 | 150-200ms | 200ms以上 |

## 制限値

### 命名制限

| 項目 | 制限値 | 説明 |
|------|--------|------|
| VM名の最大文字数 | 15文字 | NetBIOS名の制限 |
| プールIDの最大文字数 | 64文字 | Horizon Consoleの制限 |
| ファームIDの最大文字数 | 64文字 | Horizon Consoleの制限 |
| アプリケーション名の最大文字数 | 64文字 | Horizon Consoleの制限 |

### リソース制限

| 項目 | 制限値 | 説明 |
|------|--------|------|
| エンタイトルメント（ユーザー/グループ） | 制限なし | 推奨: グループベースの管理 |
| RDSHホストあたりの最大セッション数 | 推奨: 50-100 | リソースとアプリケーションによる |
| デスクトッププールあたりの最大VM数 | 制限なし | リソースとライセンスによる |
| レプリケーショングループ内のConnection Server数 | 推奨: 2-5 | 高可用性のため |
| Cloud Pod Architectureの最大ポッド数 | 10ポッド | フェデレーションの制限 |
| Global Entitlementあたりの最大プール数 | 制限なし | リソースによる |

### ストレージ制限

| 項目 | 制限値 | 説明 |
|------|--------|------|
| ゴールデンイメージの推奨サイズ | 60-100GB | OSとアプリケーションを含む |
| Writable Volumeの推奨サイズ | 10-50GB | ユーザーデータと設定 |
| AppStackの推奨サイズ | 5-20GB | アプリケーションによる |
| Instant Cloneの親VM差分ディスク | 最小限 | ストレージ効率が高い |

### GPU制限

| 項目 | 制限値 | 説明 |
|------|--------|------|
| vGPUプロファイルあたりの最大VM数 | プロファイルによる | NVIDIA vGPUプロファイルによる |
| DirectPath I/O GPU | 1 VMあたり1 GPU | 物理GPUの直接割り当て |
| vSGA | 制限なし | ソフトウェアベースの共有 |

## ログファイルの場所

### Connection Server

| ログファイル | パス | 説明 |
|------------|------|------|
| 主要ログ | `C:\ProgramData\VMware\VDM\logs\vdm.log` | Connection Serverの主要ログ |
| 管理ログ | `C:\ProgramData\VMware\VDM\logs\vdm-admin.log` | 管理操作のログ |
| イベントログ | `C:\ProgramData\VMware\VDM\logs\vdm-events.log` | イベントログ |
| セキュリティログ | `C:\ProgramData\VMware\VDM\logs\vdm-security.log` | セキュリティログ |
| JMSログ | `C:\ProgramData\VMware\VDM\logs\vdm-jms.log` | JMS通信のログ |

### Horizon Agent

| ログファイル | パス | 説明 |
|------------|------|------|
| 主要ログ | `C:\ProgramData\VMware\VDM\logs\vdm.log` | Agentの主要ログ |
| Agentログ | `C:\ProgramData\VMware\VDM\logs\vdm-agent.log` | Agent固有のログ |
| Instant Cloneログ | `C:\ProgramData\VMware\VDM\logs\vdm-instantclone.log` | Instant Clone関連のログ |

:::tip
Instant Cloneデバッグモードを有効にすると、より詳細なログが生成されます。
:::

### App Volumes Manager

| ログファイル | パス | 説明 |
|------------|------|------|
| Managerログ | `C:\Program Files\VMware\App Volumes\Manager\logs\` | App Volumes Managerのログ |
| Agentログ | `C:\ProgramData\VMware\AppVolumes\Logs\` | App Volumes Agentのログ |

### DEM (Dynamic Environment Manager)

| ログファイル | パス | 説明 |
|------------|------|------|
| FlexEngineログ | `C:\ProgramData\VMware\DEM\FlexEngine\Logs\FlexEngine.log` | DEMの主要ログ |
| 非同期ログ | `C:\ProgramData\VMware\DEM\FlexEngine\Logs\FlexEngine-Async.log` | 非同期処理のログ |
| 起動前ログ | `C:\ProgramData\VMware\DEM\FlexEngine\Logs\FlexEngine-PreStartup.log` | ログイン前の処理ログ |

### Unified Access Gateway (UAG)

| ログファイル | 説明 |
|------------|------|
| ログバンドル | `collect-log-bundle` コマンドで収集 | SSH経由でログバンドルを生成 |
| アクセスログ | `/opt/vmware/gateway/logs/access.log` | アクセスログ（UAG内部） |
| エラーログ | `/opt/vmware/gateway/logs/error.log` | エラーログ（UAG内部） |

### Recording Server

| ログファイル | パス | 説明 |
|------------|------|------|
| Recording Serverログ | `C:\ProgramData\VMware\VDM\RecordingServer\logs\` | Recording Serverのログ |

### Horizon Client (Windows)

| ログファイル | パス | 説明 |
|------------|------|------|
| クライアントログ | `%APPDATA%\VMware\VMware Horizon View Client\logs\view-client-*.log` | クライアントの主要ログ |
| SSLログ | `%APPDATA%\VMware\VMware Horizon View Client\logs\view-ssl-*.log` | SSL関連のログ |

### Horizon Client (macOS)

| ログファイル | パス | 説明 |
|------------|------|------|
| クライアントログ | `~/Library/Logs/VMware Horizon View Client/` | クライアントのログ |

### Horizon Client (Linux)

| ログファイル | パス | 説明 |
|------------|------|------|
| クライアントログ | `~/.vmware/log/vmware-horizon-client/` | クライアントのログ |

## 主要な設定ファイル

### Connection Server

| 設定ファイル | パス | 説明 |
|------------|------|------|
| Agent設定 | `C:\ProgramData\VMware\VDM\agent.cfg` | Agent設定ファイル（存在する場合） |
| グローバル設定 | データベース内 | Connection Serverのグローバル設定 |

### Horizon Agent

| 設定ファイル | パス | 説明 |
|------------|------|------|
| Agent設定 | `C:\ProgramData\VMware\VDM\agent.cfg` | Agent設定ファイル |

### DEM

| 設定ファイル | パス | 説明 |
|------------|------|------|
| FlexEngine設定 | `C:\Program Files\Immidio\FlexEngine\FlexEngine.ini` | DEM設定ファイル |

### Horizon Client (Windows)

| 設定ファイル | パス | 説明 |
|------------|------|------|
| 設定ファイル | `%APPDATA%\VMware\VMware Horizon View Client\preferences\preferences.xml` | クライアント設定 |

### Horizon Client (macOS)

| 設定ファイル | パス | 説明 |
|------------|------|------|
| 設定ファイル | `~/Library/Preferences/com.vmware.horizon.plist` | クライアント設定 |

## システム要件

### Connection Server

| 項目 | 最低要件 | 推奨要件 |
|------|---------|---------|
| CPU | 2コア | 4コア以上 |
| メモリ | 4GB | 8GB以上 |
| ディスク | 10GB | 20GB以上 |
| OS | Windows Server 2016以降（64ビット） | Windows Server 2019以降 |
| .NET Framework | 4.7.2以降 | 最新版 |

### Unified Access Gateway

| 項目 | 最低要件 | 推奨要件 |
|------|---------|---------|
| CPU | 2コア | 4コア以上 |
| メモリ | 4GB | 8GB以上 |
| ディスク | 20GB | 40GB以上 |
| OS | Photon OS 3.0以降 | Photon OS 最新版 |

### Enrollment Server

| 項目 | 最低要件 | 推奨要件 |
|------|---------|---------|
| CPU | 2コア | 4コア以上 |
| メモリ | 4GB | 8GB以上 |
| ディスク | 10GB | 20GB以上 |
| OS | Windows Server 2016以降（64ビット） | Windows Server 2019以降 |

### Horizon Agent

| 項目 | 最低要件 | 推奨要件 |
|------|---------|---------|
| OS | Windows 7以降、Windows Server 2012以降 | Windows 10/11、Windows Server 2019以降 |
| メモリ | 2GB | 4GB以上 |
| ディスク | 20GB | 60GB以上 |

### RDSH Host

| 項目 | 最低要件 | 推奨要件 |
|------|---------|---------|
| OS | Windows Server 2016以降 | Windows Server 2019以降 |
| CPU | 4コア | 8コア以上 |
| メモリ | 8GB | 16GB以上（セッション数による） |
| セッションあたりのメモリ | 512MB | 768MB-1GB |

### App Volumes Manager

| 項目 | 最低要件 | 推奨要件 |
|------|---------|---------|
| CPU | 2コア | 4コア以上 |
| メモリ | 4GB | 8GB以上 |
| ディスク | 20GB | 40GB以上 |
| OS | Windows Server 2016以降（64ビット） | Windows Server 2019以降 |
| データベース | SQL Server 2012以降、Oracle 11g以降 | SQL Server 2019以降、Oracle 19c以降 |

### Recording Server

| 項目 | 最低要件 | 推奨要件 |
|------|---------|---------|
| CPU | 4コア | 8コア以上 |
| メモリ | 8GB | 16GB以上 |
| ディスク | 100GB | 500GB以上（記録データ用） |
| OS | Windows Server 2016以降（64ビット） | Windows Server 2019以降 |

## よく使用するコマンド

### PowerShell

```powershell
# Connection Serverサービスの状態確認
Get-Service | Where-Object {$_.Name -like "*VMware*"}

# Agentサービスの再起動
Restart-Service "VMware Horizon View Agent"

# ポート接続テスト
Test-NetConnection -ComputerName horizon.contoso.com -Port 443

# CPU使用率の確認
Get-Counter "\Processor(_Total)\% Processor Time"

# メモリ使用率の確認
Get-Counter "\Memory\% Committed Bytes In Use"

# ディスク使用率の確認
Get-WmiObject Win32_LogicalDisk | Select-Object DeviceID, @{Name="Size(GB)";Expression={[math]::Round($_.Size/1GB,2)}}, @{Name="FreeSpace(GB)";Expression={[math]::Round($_.FreeSpace/1GB,2)}}

# ファイアウォールルールの追加
New-NetFirewallRule -DisplayName "Horizon Connection Server HTTPS" -Direction Inbound -LocalPort 443 -Protocol TCP -Action Allow

# Instant Cloneデバッグモードの有効化
Set-ItemProperty -Path "HKLM:\SOFTWARE\VMware, Inc.\VMware VDM\Agent" -Name "InstantCloneDebug" -Value 1 -Type DWord
```

### コマンドプロンプト

```cmd
# DNS解決の確認
nslookup horizon.contoso.com

# ネットワーク経路の確認
tracert horizon.contoso.com

# より詳細なネットワーク診断
pathping horizon.contoso.com

# グループポリシーの更新
gpupdate /force
```

### Cloud Pod Architecture (Imvutil)

```cmd
# Cloud Pod Architectureの状態確認
imvutil -c -l

# グローバルエンタイトルメントの一覧表示
imvutil -c -l -g

# ポッドの一覧表示
imvutil -c -l -p

# ホームサイトの設定
imvutil -c -s -u username -h pod-name
```

### UAG (SSH経由)

```bash
# ログバンドルの収集
collect-log-bundle

# 設定の確認
/opt/vmware/gateway/bin/gateway-cli status

# 設定のエクスポート
/opt/vmware/gateway/bin/gateway-cli export-config
```

## タイムアウト設定の優先順位

1. **アプリケーションレベル**: 最も高い優先順位
2. **ファームレベル**: 中間の優先順位
3. **グローバルレベル**: 最も低い優先順位（デフォルト）

より高いレベルの設定が下位レベルの設定を上書きします。

## エンタイトルメントの優先順位

- **個別ユーザー**: グループより優先される場合がある（設定による）
- **グループ**: 推奨される管理方法
- **複数のグループ**: すべてのグループのエンタイトルメントが適用される
- **Global Entitlement**: Cloud Pod Architectureで使用される、複数ポッドにまたがるエンタイトルメント

## クローン方式の選択ガイド

| 用途 | 推奨方式 | 理由 |
|------|---------|------|
| 永続デスクトップ | フルクローン | 完全な独立性とカスタマイズ性 |
| 非永続デスクトップ（小規模） | インスタントクローン | 高速プロビジョニングとストレージ効率 |
| 非永続デスクトップ（大規模） | インスタントクローン | スケーラビリティとストレージ効率 |
| 非永続デスクトップ（Horizon 7以前） | リンククローン | 旧バージョンでの使用 |

:::important
Horizon 8では、Instant Cloneが推奨されるクローン方式です。Linked Cloneは非推奨です。
:::

## 表示プロトコルの選択ガイド

| 環境 | 推奨プロトコル | 理由 |
|------|--------------|------|
| すべての環境 | Blast Protocol | デフォルト、適応的最適化 |
| WAN環境 | Blast Protocol または PCoIP | 低レイテンシと帯域幅効率 |
| 3Dグラフィックス | Blast Protocol | H.264コーデックによる最適化 |
| 基本的な環境 | RDP | 標準プロトコル、互換性 |

## アプリケーション配信方法の選択ガイド

| 環境 | 推奨方法 | 理由 |
|------|---------|------|
| 小規模環境 | クラシック配信 | シンプルな管理 |
| 大規模環境 | オンデマンド配信 | リソース効率とVM起動時間の短縮 |
| 頻繁に使用されるアプリ | クラシック配信 | 起動時間の短縮 |
| たまに使用されるアプリ | オンデマンド配信 | リソース効率 |

## GPUアクセラレーションの選択ガイド

| 用途 | 推奨方式 | 理由 |
|------|---------|------|
| 3Dグラフィックス、CAD | vGPU | 複数VMでGPUリソースを共有 |
| 高性能グラフィックス | DirectPath I/O | 物理GPUの直接割り当て |
| 基本的なグラフィックス | vSGA | ソフトウェアベースの共有 |
| 高密度環境 | vGPU | VM密度を最大化 |

## FIPS 140-2モード

FIPS 140-2モードを有効にする場合、以下のコンポーネントでFIPS対応が必要です：

- Connection Server
- Unified Access Gateway
- Horizon Agent（オプション）

:::caution
FIPS 140-2モードを有効にすると、一部の機能が制限される可能性があります。本番環境で有効にする前に、テスト環境で十分に検証してください。
:::

## Cloud Pod Architectureの制限

- 最大10ポッドまでフェデレーション可能
- 各ポッドは独立したvCenter Serverを持つ必要がある
- グローバルLDAPインスタンスとローカルLDAPインスタンスの違いを理解する必要がある
- Home Site戦略の実装が推奨される
