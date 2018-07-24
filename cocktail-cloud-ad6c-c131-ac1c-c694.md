# Cocktail Cloud 構成ガイド

---

カクテルクラウドは、その役割に応じて、5つのレイヤーで構成されている。

![](/assets/cocktailcloud-architecture.png)

* **Cluster Management Layer **: コンテナがデプロイ/実行するインフラ（クラスタ）とオーケストレーション（Orchestration）を担うレイヤー。オーケストレーションは、Kubenetes(https://kubernetes.io) が担い、インフラ管理、監視など拡張管理機能を提供する。

* **Service Management Layer **: サービス（Workload）に基づいて、コンテナの構成と管理を担うレイヤー。サービスを構成する多数のコンテナと関連オブジェクトをパッケージ化して、そのライフサイクルと監視を管理する。

* **Pipeline **: コードからコンテナのビルド、デプロイまでのプロセスを自動化し、継続的インテグレーション/デプロイを行う。ユーザーは、必要なパイプライン構成を設定とスクリプトで行うことができる。

* **Catalog **: 共通のランタイム（DB、ミドルウェアなど）テンプレートを提供するレイヤー。テンプレートは、追加の構成作業なく必要なときにすぐデプロイして使用することができる。また、ユーザーアプリケーションのスナップショットも保存、管理することができる。

* **Dashboard **: クラスタ、サービスのステータスと監視ビューを提供する。

続いて、各レイヤーに関して詳しく説明する。

---

Previous Topic : [Cocktail Cloud の概念](/README.md)

Next Topic : [クラスタ管理のレイヤー](/cluster-management-layerd074-b7ec-c2a4-d130-ad00-b9ac-b808-c774-c5b429.md)

