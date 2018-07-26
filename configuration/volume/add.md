### 5.4.1 ストレージ追加

---

ボリュームを追加して使用することができる。

##### **a\) クラスター → クラスター選択。**![](/assets/EN/2.5/5.4.1_1.png)

##### b**\) クラスターの詳細画面でボリュームを選択。**![](/assets/EN/2.5/5.4.1_2.png)

##### c\) クラスター名、 説明、 ストレージプラグイン、 リクレームポリシー、 ストレージクラス名、 パラメーターを順番に記入。
![](/assets/EN/2.5/5.4.1_3.png)

| **Storage Info** | **Description** |
| :--- | :--- |
| 名 | PV名 |
| 説明 | PVユーザー説明 |
| ストレージプラグイン | ストレージの種類 (NFS Dynamic/Static, EBS, Google Persistent Disk, Azure Disk) |
| リクレームポリシー | PV使用ポリシー（RETAIN/ DELETE） |
| ストレージクラス名 | k8s に登録された Class Name |
| パラメーター | PVの環境設定値 |

| **ポリシー** | **説明** |
| :--- | :--- |
| Retain | PersistentVolumeClaim（PVC）が削除されても 、PersistentVolume（PV）内にデータが残る。 後で再利用可能だが、 再利用時にはPVを再登録する必要がある。 |
| Delete | PVCが削除されると、 該当PVも一緒に削除される。 |

##### 

##### d\) Set the storage class and parameters according to the storage plugin being used.

* ##### If using NFS dynamic storage plugin![](/assets/EN/2.5/5.4.1_4.png)

| Storage Plugin | **NFS** Dynamic |
| :--- | :--- |
| Policy | The dynamic plugin supports the Retain and Delete policies |
| Storage Class Name | cocktail-nfs \(Default value\) |

* **If using NFS static storage plugin**![](/assets/EN/2.5/5.4.1_5.png)

| Storage Plugin | **NFS** Static |
| :--- | :--- |
| Policy | The static plugin only supports the Retain policy |
| Parameter | Server: IP address of storage. Path: Mount path |

* **If using AWS storage plugin**![](/assets/EN/2.5/5.4.1_6.png)

| Storage Plugin | AWS EBS \(AWS storage service\) |
| :--- | :--- |
| Storage Class Name | default \(Fixed value\) |

* **If using Google storage plugin**![](/assets/EN/2.5/5.4.1_7.png)

| Storage Plugin | Google Persistent Disk \(GCP storage service\) |
| :--- | :--- |
| Storage Class Name | standard\(Default value\) |

* **If using Azure storage plugin**![](/assets/EN/2.5/5.4.1_8.png)

| Storage Plugin | Azure Disk \(Azure storage service\) |
| :--- | :--- |
| Storage Class Name | default\(Default value\) |



