### 5.1.1 Add Cluster

---

This feature allows you to add clusters.

##### a\) Cluster → Click the [+] button in the top-right corner.![](/assets/2.5_ko_cluster_03.png)

##### b\) Enter basic information \(name, k8s version, and description\).![](/assets/2.3.0 클러스터 추가2.png)

| **Basic Information** | Description |
| :--- | :--- |
| Name | Name of cluster to be added |
| k8s version | Kubernetes version installed on cluster \(e.g., 1.8.13\) |
| Description | User-defined cluster description |

##### 

##### c\) Enter provider information \(account, type, and region\).

The input fields vary depending on the provider and account type. For bare-metal, a default value is assigned for the region and may be changed as necessary. ![](/assets/2.3.0 클러스터 추가3.png)

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

* **Provider Type - MANAGED**![](/assets/2.3.0 클러스터 추가3-1.png)

| **Add'l Input** | **Description** |
| :--- | :--- |
| Node Port URL | IP to be used with a port in a method where service access is exposed by attaching a port to a node \(Master or load balancer IP\) |
| Node Port Range | Range of ports to be used with an IP in a method where service access is exposed by attaching a port to a node. \(30000 - 32767 recommended\) |

#### ㅤ

* **Provider Type - PROVIDER**![](/assets/2.3.0 클러스터 추가3-2.png)ㅤ

#### ㅤ

* **Provider Type - GKE**![](/assets/2.3.0 클러스터 추가3-3.png)

| **Add'l Input** | **Description** |
| :--- | :--- |
| Project ID | ID of a project using a Google Cloud Platform account \(Project using GKE\) |

##### 

##### d\) Enter the monitoring information \(account, type, and region\).![](/assets/2.5.1 클러스터 추가 1 ko.png)

| **Monitoring Info ** | **Description** |
| :--- | :--- |
| Master URL | Kubernetes API address \(Format: "[https://host:port](https://host:port)" \) |
| Ingress Host | Host IP address for Ingress method \(Master or load balancer IP\) |
| Monitoring Host | Monitoring Host IP address of the server where the monitoring API is installed. \("[http://host](http://host)"\) Monitoring Port |
| Monitoring Port | Port for monitoring API |

##### 

##### e\) Enter the cluster type.![](/assets/2.3.0 클러스터 추가6.png)

| **Cluster Type Info** | **Description** |
| :--- | :--- |
| Certification Type | Certification method for k8s clusters |

#### ㅤ

* **Certification Type**![](/assets/2.3.0 클러스터 추가6-1.png)

| Certification Info | **Description** |
| :--- | :--- |
| User ID | k8s user ID |
| Password | k8s user password |
| Cluster CA Certification | Connect to master server, go to /etc/kubernetes/pki/, and enter the ca.crt file value |
| Client Certificate Data | Connect to master server, go to /etc/kubernetes/pki/, and enter the admin.crt file value |
| Client Key Data | Connect to master server, go to /etc/kubernetes/pki/, and enter the admin.key file value |



