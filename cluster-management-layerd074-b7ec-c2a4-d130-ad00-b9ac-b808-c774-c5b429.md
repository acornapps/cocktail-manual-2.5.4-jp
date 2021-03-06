# クラスタ管理のレイヤー

---

クラスタ管理のレイヤーは、クラスタを構成するインフラとコンテナオーケストレーションエンジンに分けられる。構成の詳細は、下の図のとおりである。

![](/assets/cocktailcloud-architecture-2.png)

カクテルクラウドは、クラスタインフラとオーケストレーションエンジンをユーザーの設定に基づいて自動的にプロビジョニング（Provisioning）するが、これを担うツールが CUBEである。CUBEは、高可用性（High Availability、HA）のKubernetesクラスタを構成している。CUBEがプロビジョニングするクラスタ構成は、高い安定性とセキュリティ、拡張性を提供する。（これをCUBEクラスタという。）

CUBEクラスタは、現在、以下のようなクラウドプラットフォームおよびプロバイダをサポートしている。しかし、CUBE は、インフラに依存しない構成が可能であるため、どのようなインフラでも構成が可能である。下記は、インフラの自動プロビジョニングを基準としたものである。

* 物理インフラ（Baremetal）

* クラウドプラットフォーム : Openstack、Cloudstack、VMWare

* クラウドサービス : AWS、GCP、 Azure

また、CUBEツールは、クラスタのKubernetesのバージョンアップ、ノード（物理/仮想マシン）の追加/削除、バックアップといったクラスタ管理のための機能を提供する。

カクテルクラウドは、マルチクラスタを統合管理する。つまり、複数のクラスタを必要なサービスに割り当て、クラスタ全体の管理と監視を行う。クラスタは、必要に応じて追加することができる。

CUBEクラスタには、管理のための拡張コンポーネントが追加で提供される。

* Monitoring : インフラ、コンテナ、サービス（Workload）の状態、構成、リソースを監視
* Alerting : 特定の条件になったとき、電子メール、メッセンジャーでアラートを通知および管理
* Metering : パブリッククラウドクラスタの場合の使用コストを照会
* Inspecting : コンテナおよびKubernetesオブジェクトの変更履歴およびイベントの管理

拡張コンポーネントが提供する情報と管理機能は、カクテルクラウドの「クラスタ管理」ビュー（View）で確認できる。

---

Previous Topic : [Cocktail Cloud 構成ガイド](/cocktail-cloud-ad6c-c131-ac1c-c694.md)

Next Topic : [サービス管理レイヤー](/c11c-be44-c2a4-ad00-b9ac-b808-c774-c5b4.md)

