### 3.2.1 Add Build

---

This feature allows you to add Docker image build tasks. Three options are available: Application download, application build, and image build.

**a\) Service > Build Management > Build Action Menu \(Activate\) > Edit Task Settings**![](/assets/2.5.0 빌드관리1 ko.png)![](/assets/2.3.0 빌드 추가.png)

**b\) Enter the necessary application download, application build, and image build information and click the [Create] button to create a build**![](/assets/2.3.0 빌드 추가2.png)

| **Build Phase** | **Description** |
| :--- | :--- |
| Application Download | Download the necessary source for a build |
| Application Build | Use when source compile is needed <br/>**Command** - Task to be executed during build <br/>**Host Path** - The container path where the operation is to take place and the host path for mounting <br/>**Working dir** - Actual path to work within the container; Matched with container path <br/>**Image** - Image to be used for the build |
| Image Build | The source from the previous phase is used to create a Docker file and subsequently an image to be saved in a registry |

* **Basic Build Information**![](/assets/2.3.0 빌드 추가3.png)

| **Basic Info** | **Description** |
| :--- | :--- |
| Name | Name of build to be created |
| Latest Action | Displays status of latest action |
| Status | Displays current build status |

* **Application Download**![](/assets/2.3.0 빌드 추가4.png)

| **Application Download** | **Description** |
| :--- | :--- |
| Repository Type | Type of version management tool that will download the source file. Only GIT is supported on the current version |
| Protocol Type | HTTP/HTTPS protocol provided by repository |
| Git Repository Type | Private/common supported |
| Repository URL | Repository URL for download |
| Repository User ID | User ID for access to repository |
| Repository Password | Password for access to repository |
| Target Branch | Branch information of source to be downloaded |

* **Application Build**![](/assets/2.3.0 빌드 추가5.png)

| **Application Build** | **Description** |
| :--- | :--- |
| Command | Command to be executed during build |
| Host Path | Path of downloaded source |
| Container Path | The container path where the operation is to take place |
| Working Dir | Actual path to work within the container. Matched with container path |
| Image | Container image for build |

* **Image Build**![](/assets/2.3.0 빌드 추가6.png)

| **Image Build** | Description |
| :--- | :--- |
| Dockerfile | Docker file for image creation |
| Registry Name | Registry where the created image is to be stored |
| Image | Name and tag of image to be stored in the registry |



