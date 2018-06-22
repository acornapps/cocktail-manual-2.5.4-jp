# Cocktail Cloud 구성 개요

---

칵테일 클라우드는 그 역할에 따라 5개의 레이어로 구성된다.

![](/assets/cocktailcloud-architecture.png)

* **Cluster Management Layer **: 컨테이너가 배포/실행되는 인프라\(클러스터\)와 오케스트레이션\(Orchestration\)을 담당하는 레이어다. 오케스트레이션은  Kubernetes\([https://kubernetes.io](https://kubernetes.io)\)가 담당하고 인프라 관리, 모니터링 등 확장 관리 기능을 제공한다.

* **Service Management Layer **: 서비스\(Workload\)를 기준으로 컨테이너 구성과 관리를 담당하는 레이어다. 서비스를 구성하는 다수의 컨테이너와 관련 객체를 패키징하고 그 수명주기와 모니터링을 관리한다.

* **Pipeline **: 코드에서 컨테이너 빌드, 배포까지의 과정을 자동화하여 지속적인 통합/배포를 수행한다. 사용자는 원하는 파이프라인 구성을 설정과 스크립트를 통해 할 수 있다.

* **Catalog **: 공통으로 사용되는 런타임\(DB, 미들웨어 등\)템플릿을 제공하는 레이어다. 템플릿은 필요할 때 별도의 구성 작업 없이 바로 배포하여 사용 할 수 있다. 또한 사용자 어플리케이션의 스냅샷도 저장,  관리 할 수 있다.

* **Dashboard **: 클러스터, 서비스 현황과 모니터링 뷰를 제공 한다.

계속해서 각 레이어를 구체적으로 살펴 보자

---

이전글 : [Cocktail Cloud 이해](/README.md)

다음글 : [Cluster Management Layer\(클러스터 관리 레이어\)](/cluster-management-layerd074-b7ec-c2a4-d130-ad00-b9ac-b808-c774-c5b429.md)

