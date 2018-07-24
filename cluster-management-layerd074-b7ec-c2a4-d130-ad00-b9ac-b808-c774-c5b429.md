# クラスタ管理のレイヤー

---

クラスタ管理のレイヤーは、クラスタを構成するインフラとコンテナオーケストレーションエンジンに分けられる。構成の詳細は、下の図のとおりである。

![](/assets/cocktailcloud-architecture-2.png)

Cocktail Cloud automatically provisions the cluster infrastructure and orchestration engine according to user configuration. The tool responsible for this is Cube. Cube constitutes high-availability \(HA\) Kubernetes clusters. Cube-provisioned cluster configurations provide high reliability, security, and scalability. \(This is referred to as a Cube cluster.\)

Cube clusters currently support the cloud platforms and providers listed below. Note, however, that Cube can be configured independently on any infrastructure. The following is based on automatic infrastructure provisioning.

* Physical infrastructure \(Baremetal\)

* Cloud platform : Openstack, Cloudstack, VMWare

* Cloud service : AWS, GCP, Azure

Cube also provides cluster management features such as Kubernetes version upgrading, node \(physical/virtual machine\) adding/deleting, and backups.

Cocktail Cloud provides integrated-management of multiple clusters. That is, multiple clusters can be assigned to the desired service, and all clusters can be managed and monitored.

Clusters can be added as needed. Additional scaling components are provided via Cube clusters.

* Monitoring : Infrastructure, container, service \(workload\) status, configuration, resource monitoring.
* Alerting : Alerts via email/messenger when specific conditions are met.
* Metering : View usage cost of public cloud clusters.
* Inspecting : Change tracking and event management of containers and Kubernetes objects

Information and management functions provided via scaling component are available through Cocktail Cloud's Custer Management view.

---

Previous Topic : [Cocktail Cloud Structure Overview](/cocktail-cloud-ad6c-c131-ac1c-c694.md)

Next Topic : [Service Management Layer](/c11c-be44-c2a4-ad00-b9ac-b808-c774-c5b4.md)

