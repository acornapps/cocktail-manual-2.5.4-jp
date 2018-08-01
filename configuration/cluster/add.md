### 5.1.1 クラスター追加

---

クラスターを追加登録することができる機能である。

##### a\) クラスター → 右上の+ボタンをクリック。![](/assets/JP/2.5/5.1.1_1.png)

##### b\) 基本情報（クラスター名、k8sバージョン、説明）を入力。![](/assets/JP/2.5.3/5.1.1_2.png)

| **基本情報** | 説明 |
| :--- | :--- |
| クラスター名 | 登録するクラスタの名前 |
| k8sバージョン | クラスタにインストールされたKubernetesのバージョン情報。e.g）1.8.13 |
| ID | クラスタ固有のID（ユーザー指定）、アラームメッセージRedirect時に必要 |
| 説明 | クラスタのユーザー説明 |

##### c\) プロバイダ情報（アカウント、タイプ、地域）を入力。

アカウントのプロバイダとタイプに応じて入力欄が変更される。Baremetalの場合、地域はDefault値を提供し、変更が可能である。 ![](/assets/JP/2.5/5.1.1_3.png)

| **プロバイダ** | **説明** |
| :--- | :--- |
| アカウント | 登録されたアカウント |
| タイプ | Kubernetesの使用タイプとして、MANAGED、PROVIER、GKEの中から選択 |
| 地域 | Kubernetesがインストールされたサーバーのリージョン |

| **タイプ** | **説明** |
| :--- | :--- |
| MANAGED | CUBE Installerを利用して、kubernetesを構成したクラスタ |
| PROVIDER | Public CloudのVMでKubernetesを利用するが、 Public Cloudを利用する場合に使用する。 （ロードバランサやストレージなどその他のサービスを利用する場合） |
| GKE | Google Cloud PlatformのGoogle Kubernetes Engineで構成したクラスタ |

#### ㅤ

* **プロバイダの種類 - MANAGED**![](/assets/JP/2.5/5.1.1_4.png)

| **追加入力** | **説明** |
| :--- | :--- |
| ノードポート URL | ノードにポートを付けてサービスを公開するタイプの中で、 ポートの前に使用するIPサービス （Master IP or Loadbelancer IP） |
| ノードポート 範囲 | ノードにポートを付けてサービス公開するタイプの中で、 IPの後に使用するポートの範囲 。 \(30000 - 32767 推奨\) |

#### ㅤ

* **プロバイダの種類 - PROVIDER**![](/assets/JP/2.5/5.1.1_5.png)

#### ㅤ

* **プロバイダの種類 - GKE**![](/assets/JP/2.5/5.1.1_6.png)

| **追加入力** | **説明** |
| :--- | :--- |
| プロジェクト ID | Google Cloud Platformのアカウントが使用するプロジェクトのID （GKEを使用するプロジェクト） |

##### 

##### d\) 監視情報（マスターURL、 Ingress Host、 モニタリングホスト, モニタリングポート）を入力する。![](/assets/JP/2.5/5.1.1_7.png)

| **モニタリング 情報 ** | **説明** |
| :--- | :--- |
| マスターURL | Kubernetes APIのアドレス。 \("[https://host:port](https://host:port)" 形式を使用する。\) |
| Ingress Host | イングレス方式で使用するHost IP Addressサービス（Master IP or Loadbalancer IP） |
| モニタリングホスト | Monitoring APIがインストールされているサーバーのIPアドレス \("[http://host](http://host)"\) |
| モニタリングポート | Monitoring APIのポート情報 |

##### 

##### e\) クラスターのタイプを入力![](/assets/JP/2.5/5.1.1_8.png)

| **クラスタータイプの情報** | **説明** |
| :--- | :--- |
| 認証タイプ | k8sクラスターを使用するための認証手段 |

#### ㅤ

* **認証タイプ - certification**![](/assets/EN/2.5/5.1.1_9.png)

| 認証情報 | **説明** |
| :--- | :--- |
| ユーザーID | k8s ユーザーID |
| パスワード | k8s ユーザーPW |
| Cluster CA Certification | マスターサーバー接続後、/etc/kubernetes/pkiパス移動後、 ca.crtファイルの値を入力 |
| Client Certificate Data | マスターサーバー接続後、/etc/kubernetes/pkiパス移動後、admin.crtファイルの値を入力 |
| Client Key Data | マスターサーバー接続後、/etc/kubernetes/pkiパス移動後、admin.keyファイルの値を入力 |



