## 7.1 Kubernetes\(k8s\)

#### 1.Cluster

| 用語 | 説明 |
| :--- | :--- |
| Namespace | k8sの仮想クラスタで、 ユーザーが複数のチームやプロジェクトに分散して作業することができる別の環境 |
| Nodes | k8sのクラスタリングされているアプリケーションを駆動する物理サーバーまたはVM |
| Persistent Volumes\(PV\) | 外部ストレージ。 NFS、 iSCSI、 クラウドが提供するストレージシステムをサポート |
| Roles | 使用に基づいて権限を付与 |
| Storage Classes | PVを動的にProvisioningする場合にNFSサーバーを識別するための識別子 |

#### 2.Workloads

| 用語 | 説明 |
| :--- | :--- |
| Cron Jobs | 「ある時点で一度」 または 「ある時点で繰り返し」など時間ベースでの管理作業 |
| Deployments | Podを作成するための設定値の登録情報 |
| Jobs | Jobは、一括処理を行うPodのSupervisor。 つまり、 特定の計算またはバックアップといった特定の間だけ実行されるプロセス |
| Pods | 複数のコンテナで構成されているk8sにおけるdeployのための最小単位。 Podは、アプリケーションスタックで異なるDocker imageを混合し、構成 |
| Replica Sets | 指定された Podのレプリカが常に実行（維持）されるようにする |
| Replication Controllers | 指定された数のPodのレプリカが実行されているかをチェック |
| Stateful Sets | Podのデプロイおよび拡張を管理し、 Podの順序と特性の設定を提供 |

#### 3.Discovery and load balancing

| 用語 | 説明 |
| :--- | :--- |
| Ingresses | 外部からのアクセスを橋渡しするもので名前ベースの仮想ホスティングを提供 |
| Services | 複数のコンテナを一つの論理ユニットでグループ化し、 外部からアクセスできる単一EndPointを提供 |

#### 4.config and storage

| 用語 | 説明 |
| :--- | :--- |
| Config Maps | データを保存して使用することができるようにサポート |
| Persistent Volume Claime\(PVC\) | ユーザーのPVに対する要求。 PodはPVCでリソース（CPUおよびメモリ）、 ストレージのサイズおよびアクセス権限（rw、readonly...）を要求することができる |
| Secrets | PasswordまたはOAuthトークンおよびssh keyなどのストレージ |

#### 5.settings

K8sの Global Settingsの値を調整することができる。

| オプション | 説明 |
| :--- | :--- |
| Cluster name | Kubernetes Cluster名の値を調整する |
| Items per page | 1ページで表示できるItemsの値を調整する |
| Auto-refresh time interval | Logを自動で再読み込みする時間を調整する |



