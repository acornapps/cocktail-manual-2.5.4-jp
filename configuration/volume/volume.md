## 5.4 Volume

---

This feature allows you to add public cloud and external storage information and also provides volume monitoring.

**a\) Cluster → Select Cluster → Volume.**![](/assets/2.3.2 클러스터 선택.png)![](/assets/2.3.0 볼륨.png)

| **Storage Settings** | **Description** |
| :--- | :--- |
| [+] button | Redirects to Add Storage page |
| Name | Name of storage \(user-defined\) |
| Type | Type of storage \(NFS/EBS/Google Persistent Disk/Azure Disk\) |
| Storage Class Name | Class name registered in k8s |
| Policy | Storage volume policy \(Retain/Recycle/Delete\) |
| Status |Storage usage status |

| **Volume Settings** | **Description** |
| :--- | :--- |
| Volume Name | PVC name |
| Status | PVC mount status |
| Usage | Allocated PV capacity and usage |
| Access Mode | PV access privileges |
| Age | PVC uptime |



