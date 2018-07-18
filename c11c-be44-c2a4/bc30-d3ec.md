### 3.1.5 Pipeline

---

With the pipeline feature, you can build an image and deploy to a server all at once.

You can also change the image version of a deployed server and quickly redeploy.

##### a\) Service > Select Application Map > Pipeline. ![](/assets/EN/2.5/3.1.5_1.png)![](/assets/EN/2.5/3.1.5_2.png)

| **Pipeline Menu ** | **Description ** |
| :---: | :--- |
| Batch execution | Execute pipeline tasks in batch |
| Run | Execute a specific pipeline task |

| **Image Menu** | **Build** | **Description ** |
| :---: | :--- | :--- |
| Image Tag | X | Deploy server of the corresponding version when enter tag in registry |
| Appointed | ⃝ | Deploy designated server version among images |
| Latest | ⃝ | Deploy latest server version among images |
| Build & Deployment | ⃝ | Deploy corresponding server version after a new image is built |

##### b\) Execute Pipeline

##### **1. If server was created with a common image**

Enter image tag and click [Run] or [Batch execution]. \(Only available if the deployed version is different from the version entered; Excludes ‘Latest’\) ![](/assets/EN/2.5/3.1.5_3.png)

##### **2. If server was created with a built image**

* **Deploying a designated image**

Select [Appointed] and an image from the right of the pipeline task list and click [Run] or [Batch execution]. \(Only available if the deployed version is different from the version entered\)![](/assets/EN/2.5/3.1.5_4.png)

* **Deploying a newly-built image**

Select [Build & Deployment] from the right of the pipeline task list and check [Execution whether]. Click [Run] or [Batch execution]. \(Only available if [Execution whether] is checked.\) ![](/assets/EN/2.5/3.1.5_5.png)

* **Deploying the latest image**

Select [Latest] from the right of the pipeline task list and click [Run] or [Batch execution]. \(Only available if the deployed version is different from the version entered\) ![](/assets/EN/2.5/3.1.5_6.png)

* **Edit Build and View Log**

You will be redirected to the Edit Build page when the name of a build image is clicked.![](/assets/EN/2.5/3.1.5_7.png)

You can view the log by clicking on the build tag name.![](/assets/EN/2.5/3.1.5_8.png)![](/assets/EN/2.5/3.1.5_9.png)

