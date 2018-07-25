### 5.1.1 クラスター追加

---

クラスターを追加登録することができる機能である。

##### a\) クラスター → 右上の+ボタンをクリック。![](/assets/EN/2.5/5.1.1_1.png)

##### b\) 基本情報（クラスター名、k8sバージョン、説明）を入力。![](/assets/EN/2.5/5.1.1_2.png)

| **基本情報** | 説明 |
| :--- | :--- |
| クラスター名 | 登録するクラスタの名前 |
| k8sバージョン | クラスタにインストールされたKubernetesのバージョン情報。e.g）1.8.13 |
| 説明 | クラスタのユーザー説明 |

##### c\) Enter provider information \(account, type, and region\).

The input fields vary depending on the provider and account type. For bare-metal, a default value is assigned for the region and may be changed as necessary. ![](/assets/EN/2.5/5.1.1_3.png)

| **Provider** | **Description** |
| :--- | :--- |
| Account | Registered account |
| Type | Kubernetes usage type; Select MANAGED, PROVIDER, or GKE |
| Region | Region where the Kubernetes server is installed |

| **Type** | **Description** |
| :--- | :--- |
| MANAGED | Cluster where Kubernetes is configured via CUBE Installer |
| PROVIDER | Select if using a public cloud and Kubernetes via a VM \(If using other services such as load balancers and storage\) |
| GKE | Cluster configured with Google Kubernetes Engine on Google Cloud Platform |

#### ㅤ

* **Provider Type - MANAGED**![](/assets/EN/2.5/5.1.1_4.png)

| **Add'l Input** | **Description** |
| :--- | :--- |
| Node Port URL | IP to be used with a port in a method where service access is exposed by attaching a port to a node \(Master or load balancer IP\) |
| Node Port Range | Range of ports to be used with an IP in a method where service access is exposed by attaching a port to a node. \(30000 - 32767 recommended\) |

#### ㅤ

* **Provider Type - PROVIDER**![](/assets/EN/2.5/5.1.1_5.png)

#### ㅤ

* **Provider Type - GKE**![](/assets/EN/2.5/5.1.1_6.png)

| **Add'l Input** | **Description** |
| :--- | :--- |
| Project ID | ID of a project using a Google Cloud Platform account \(Project using GKE\) |

##### 

##### d\) Enter the monitoring information \(account, type, and region\).![](/assets/EN/2.5/5.1.1_7.png)

| **Monitoring Info ** | **Description** |
| :--- | :--- |
| Master URL | Kubernetes API address \(Format: "[https://host:port](https://host:port)" \) |
| Ingress Host | Host IP address for Ingress method \(Master or load balancer IP\) |
| Monitoring Host | Monitoring Host IP address of the server where the monitoring API is installed. \("[http://host](http://host)"\) Monitoring Port |
| Monitoring Port | Port for monitoring API |

##### 

##### e\) Enter the cluster type.![](/assets/EN/2.5/5.1.1_8.png)

| **Cluster Type Info** | **Description** |
| :--- | :--- |
| Certification Type | Certification method for k8s clusters |

#### ㅤ

* **Certification Type**![](/assets/EN/2.5/5.1.1_9.png)

| Certification Info | **Description** |
| :--- | :--- |
| User ID | k8s user ID |
| Password | k8s user password |
| Cluster CA Certification | Connect to master server, go to /etc/kubernetes/pki/, and enter the ca.crt file value |
| Client Certificate Data | Connect to master server, go to /etc/kubernetes/pki/, and enter the admin.crt file value |
| Client Key Data | Connect to master server, go to /etc/kubernetes/pki/, and enter the admin.key file value |



