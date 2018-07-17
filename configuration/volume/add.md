### 5.4.1 Add Storage

---

This feature allows you to add storage volumes.

##### **a\) Cluster → Select Cluster.**![](/assets/2.3.2 클러스터 선택.png)

##### b**\) Select a volume from the detailed cluster screen**![](/assets/2.3.0 볼륨 추가.png)

##### c\) Enter cluster, name, description, storage plugin, policy, and storage class name in order.![](/assets/2.3.0 볼륨 추가2.png)

| **Storage Info** | **Description** |
| :--- | :--- |
| Name | PV name |
| Description | User-defined PV description |
| Policy | PV usage policy \(RETAIN/DELETE\) |
| Storage Plugin | Type of storage \(NFS Dynamic/Static, EBS, Google Persistent Disk, Azure Disk\) |
| Storage Class Name | Class name registered in k8s |
| Parameters | PV environment settings |

| **Policy** | **Description** |
| :--- | :--- |
| Retain | The data in a persistent volume \(PV\) remains even if the persistent volume claim \(PVC\) is deleted. Although it can be reused, the PV must be re-registered |
| Delete | When a PVC is deleted, the corresponding PV is also deleted |

##### 

##### d\) Set the storage class and parameters according to the storage plugin being used.

* ##### If using NFS dynamic storage plugin![](/assets/2.3.0 볼륨 추가2-1.png)

| Storage Plugin | **NFS** Dynamic |
| :--- | :--- |
| Policy | The dynamic plugin supports the Retain and Delete policies |
| Storage Class Name | cocktail-nfs \(Default value\) |

* **If using NFS static storage plugin**![](/assets/2.3.0 볼륨 추가2-2.png)

| Storage Plugin | **NFS** Static |
| :--- | :--- |
| Policy | The static plugin only supports the Retain policy |
| Parameter | Server: IP address of storage. Path: Mount path |

* **If using AWS storage plugin**![](/assets/2.3.0 볼륨 추가2-3.png)

| Storage Plugin | AWS EBS \(AWS storage service\) |
| :--- | :--- |
| Storage Class Name | default \(Fixed value\) ) |

* **If using Google storage plugin**![](/assets/2.3.0 볼륨 추가2-4.png)

| Storage Plugin | Google Persistent Disk \(GCP storage service\) |
| :--- | :--- |
| Storage Class Name | standard\(Default value\) |

* **If using Azure storage plugin**![](/assets/2.3.0 볼륨 추가2-5.png)

| Storage Plugin | Azure Disk \(Azure storage service\) |
| :--- | :--- |
| Storage Class Name | default\(Default value\) |



