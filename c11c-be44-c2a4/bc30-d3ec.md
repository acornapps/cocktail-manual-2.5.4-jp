### 3.1.5 Pipeline

---

With the pipeline feature, you can build an image and deploy to a server all at once.

You can also change the image version of a deployed server and quickly redeploy.

##### a\) Service > Select Application Map > Pipeline. ![](/assets/2.5.0 서버중지1 ko.png)![](/assets/2.5.0 파이프라인 메인1.png)

| **Pipeline Menu ** | **Description ** |
| :---: | :--- |
| Batch Execute | Execute pipeline tasks in batch |
| Execute | Execute a specific pipeline task |

| **Image Menu** | **Build** | **Description ** |
| :---: | :--- | :--- |
| Image Tag | X | Deploy server of the corresponding version when enter tag in registry |
| Designated | ⃝ | Deploy designated server version among images |
| Latest | ⃝ | Deploy latest server version among images |
| Build & Deploy | ⃝ | Deploy corresponding server version after a new image is built |

##### b\) Execute Pipeline

##### **1. If server was created with a common image**

Enter image tag and click [Execute] or [Batch Execute]. \(Only available if the deployed version is different from the version entered; Excludes ‘Latest’\) ![](/assets/2.5.0 파이프라인 태그입력1.png)

##### **2. If server was created with a built image**

* **Deploying a designated image**

Select [Designated] and an image from the right of the pipeline task list and click [Execute] or [Batch Execute]. \(Only available if the deployed version is different from the version entered\)![](/assets/2.5.0 파이프라인 지정이미지1.png)

* **Deploying a newly-built image**

Select [Build & Deploy] from the right of the pipeline task list and check [Confirm Execute]. Click [Execute] or [Batch Execute]. \(Only available if [Confirm Execute] is checked.\) ![](/assets/2.5.0 파이프라인 빌드앤배포1.png)

* **Deploying the latest image**

Select [Latest] from the right of the pipeline task list and click [Execute] or [Batch Execute]. \(Only available if the deployed version is different from the version entered\) ![](/assets/2.5.0 파이프라인 최신이미지1.png)

* **Edit Build and View Log**

You will be redirected to the Edit Build page when the name of a build image is clicked.![](/assets/2.5.0 파이프라인 메인2.png)

You can view the log by clicking on the build tag name.![](/assets/2.5.0 파이프라인 메인3.png)![](/assets/2.5.0 파이프라인 로그1.png)

