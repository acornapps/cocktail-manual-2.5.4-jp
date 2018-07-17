## 7.1 Kubernetes\(k8s\)

#### 1.Cluster

| Term | Description |
| :--- | :--- |
| Namespace | A separate environment in which users across multiple teams or projects can work in virtual k8s clusters |
| Nodes | A physical server or VM running clustered k8s applications |
| Persistent Volumes\(PV\) | External storage; Supports NFS, iSCSI, and cloud storage systems |
| Roles | Grants permissions according to usage case. |
| Storage Classes | Identifier for identifying NFS servers when dynamically provisioning a PV |

#### 2.Workloads

| Term | Description |
| :--- | :--- |
| Cron Jobs | Time-based administration tasks such as 'Once at a certain time' or 'Repeat at a certain time |
| Deployments | Settings values for pod generation |
| Jobs | A job is a pod's supervisor that performs batch processing. In other words, it's a process that runs only for a specific period as with certain calculations or backups |
| Pods | A minimum unit consisting of one or more containers for deployment in k8s. A pod is a mix of different Docker images in an application stack |
| Replica Sets | Ensures that a specified pod copy is always running. |
| Replication Controllers | Checks whether a specified number of pod copies are running |
| Stateful Sets | Manages pod deployment and scaling and provides settings for the order and characteristics of pods |

#### 3.Discovery and load balancing

| Term | Description |
| :--- | :--- |
| Ingresses | Provides name-based virtual hosting for external access requests |
| Services | Provides a single endpoint that can be accessed externally by grouping multiple containers into a single logical unit |

#### 4.config and storage

| Term | Description |
| :--- | :--- |
| Config Maps | Stores data for use |
| Persistent Volume Claime\(PVC\) | User request for a PV. A pod can request resources (CPU and memory) as well as the size of and access privileges \(RW, RO, etc.\) to a storage space |
| Secrets | Repository for password, OAuth tokens, and SSH keys |

#### 5.settings

K8s의Global Settings값을 조정 할 수 있습니다.

| Option | Description |
| :--- | :--- |
| Cluster name | Adjusts the name value of a Kubernetes cluster |
| Items per page | Adjusts the number of items that are displayed on a page |
| Auto-refresh time interval | Adjusts the time interval for automatically refreshing logs |



