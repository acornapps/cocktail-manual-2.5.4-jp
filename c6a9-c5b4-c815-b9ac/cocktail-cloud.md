## 7.2 Cocktail Cloud

#### 1.環境設定

カクテルクラウドを利用するため、事前に情報を登録するサービス

| **用語** | **説明** |
| :--- | :--- |
| ユーザー | Cocktail Cloudを利用するためのユーザ管理をサポート |
| アカウント | k8s Clusterのユーザー認証情報の管理をサポート |
| サービス | 業務またはプロジェクト単位でタスクを分散して管理。 管理者は、 一般ユーザーに対してサービス単位でアクセス権を付与することができる |

C. クラスター: Page for managing information related to k8s use

#### 2.Service

Tasks can be subdivided into application units, and Docker images can be created through builds. Applications can be created, viewed, modified, and deleted via built images.

| **用語** | **説明** |
| :--- | :--- |
| Application Map | k8s Namespace |
| build | Service that supports tasks for the creation of Docker images |
| Monitoring | Provides resource monitoring of servers, pods, and containers in an application |
| Pipeline | Service for streamlining processes from building to deployment |
| Setting | Service for storing and using variable values or files in application units |

#### 3.Catalog

Service for easily creating, modifying, and deploying servers by creating templates of application configurations.

#### 4.Cluster

Service for registering, managing, and querying clusters, nodes, applications, volumes/storage, alerts, and meters

| **用語** | **説明** |
| :--- | :--- |
| Cluster | Server packages that constitute k8s orchestration |
| Node | Individual server in a k8s server cluster. Categorized as either master or worker |
| Application | Service consisting of one or more containers |
| Volume/Storage | External storage information |
| Alerts | Alerts for cluster events |
| Metering | Cluster cost information |



