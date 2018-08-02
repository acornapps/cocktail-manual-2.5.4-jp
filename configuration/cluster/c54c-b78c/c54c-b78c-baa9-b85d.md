## 5.5.1 アラームリスト

---

アラームは、次のリストから発生条件が持続時間だけ継続した場合に発生する。

* #### AlertManager

| アラーム ID | **ALM-001** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | AlertmanagerDown |
| 持続時間 | 5分 |
| 発生条件 | Alertmanagerメトリックの収集ができない場合に発生 |
| 処理 | Prometheusのログと Alertmanagerのログとイベントを確認する。 <br/> 必要な場合には、Podを再起動する。 |

| アラーム ID | **ALM-002** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | AlertmanagerFailedReload |
| 持続時間 | 10分 |
| 発生条件 | Alertmanagerの設定変更時、 設定の再読み込み処理失敗時に発生 |
| 処理 | そのPodのログを確認して ConfigMapの設定エラーを修正する。 |

* #### ETCD3

| アラーム ID | **ETC-001** |
| :--- | :--- |
| レベル | **critical** |
| アラーム名 | InsufficientMembers |
| 持続時間 | 3分 |
| 発生条件 | ETCDメトリックの収集ができない場合に発生 |
| 処理 | ETCDクラスタの状態を確認する。 Prometheusのログと、そのノードの<br/> etcd状態を確認する。 |

| アラーム ID | **ETC-002** |
| :--- | :--- |
| レベル | **critical** |
| アラーム名 | NoLeader |
| 持続時間 | 1分 |
| 発生条件 | ETCDリーダーがない場合に発生 |
| 処理 | ETCDクラスタの状態を確認する。 Disk Latencyに起因する問題の可能<br/>性があるため、 以下のコマンドをETCDクラスタノード全体で実行する。<br /> \([ETCD Tuning](https://coreos.com/etcd/docs/latest/tuning.html#disk)\) ``$ sudo ionice -c2 -n0 -p `pgrep etcd` `` |

| アラーム ID | **ETC-003** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | HighNumberOfLeaderChanges |
| 持続時間 | すぐに |
| 発生条件 | 最近1時間の間、3回以上のリーダーの変更が発生した場合 |
| 処理 | ETCDクラスタの状態を確認する。 Disk Latencyに起因する問題の可能<br/>性があるため、 以下のコマンドをETCDクラスタノード全体で実行する。<br /> \([ETCD Tuning](https://coreos.com/etcd/docs/latest/tuning.html#disk)\) ``$ sudo ionice -c2 -n0 -p `pgrep etcd` `` |

| アラーム ID | **ETC-004** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | HighNumberOfFailedGRPCRequests |
| 持続時間 | 10分 |
| 発生条件 | 5分以内に gRPCメソッド呼び出しの 1％以上失敗した場合 |
| 処理 | ETCDクラスタと Kubernetesクラスタの 帯域幅を増やしたり、<br/>クラスタの Sacale-Upが必要です。 |

| アラーム ID | **ETC-005** |
| :--- | :--- |
| レベル | **critical** |
| アラーム名 | HighNumberOfFailedGRPCRequests |
| 持続時間 | 5分 |
| 発生条件 | 5分以内にgRPCメソッド呼び出しの 5％以上失敗した場合 |
| 処理 | ETCDクラスタと Kubernetesクラスタの 帯域幅を増やしたり、<br/>クラスタの Sacale-Upが必要です。 |

| アラーム ID | **ETC-006** |
| :--- | :--- |
| レベル | **critical** |
| アラーム名 | GRPCRequestsSlow |
| 持続時間 | 10分 |
| 発生条件 | 最近5分間gRPCメソッド要求の 待機時間の99パーセンタイル値が<br/>150msを超える場合 |
| 処理 | ETCDクラスタと Kubernetesクラスタの 帯域幅を増やしたり、<br/>クラスタの Sacale-Upが必要です。 |

| アラーム ID | **ETC-007** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | HighNumberOfFailedHTTPRequests |
| 持続時間 | 10分 |
| 発生条件 | 5分以内にHTTPエンドポイントへの 要求の1％以上が失敗した場合 |
| 処理 | ETCDクラスタと Kubernetesクラスタの 帯域幅を増やしたり、<br/>クラスタの Sacale-Upが必要です。 |

| アラーム ID | **ETC-008** |
| :--- | :--- |
| レベル | **critical** |
| アラーム名 | HighNumberOfFailedHTTPRequests |
| 持続時間 | 5分 |
| 発生条件 | 5分以内にHTTPエンドポイントへの 要求の5％以上が失敗した場合 |
| 処理 | ETCDクラスタと Kubernetesクラスタの 帯域幅を増やしたり、<br/>クラスタの Sacale-Upが必要です。 |

| アラーム ID | **ETC-009** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | HTTPRequestsSlow |
| 持続時間 | 10分 |
| 発生条件 | 最近5分間のHTTPリクエストの待機時間の 99パーセンタイル値が150msを超える場合 |
| 処理 | ETCDクラスタと Kubernetesクラスタの 帯域幅を増やしたり、<br/>クラスタの Sacale-Upが必要です。 |

| アラーム ID | **ETC-010** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | EtcdMemberCommunicationSlow |
| 持続時間 | 10分 |
| 発生条件 | 最近5分間のメンバー間の通信の待機時間の 99パーセンタイル値が<br/>150msを超える場合 |
| 処理 | ETCDクラスタの帯域幅を増やしたり、<br/>クラスタのScale-Upが必要です。 |

| アラーム ID | **ETC-011** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | HighNumberOfFailedProposals |
| 持続時間 | すぐに |
| 発生条件 | 最近1時間の間に5つ以上の失敗raft protocol要求がある場合。<br/>（RAFT ProtocolはETCD同期Protocol） |
| 処理 | [ETCDメトリック文書](https://github.com/coreos/etcd/blob/master/Documentation/metrics.md/)によると、 リーダー選出の一時的な障害や<br/>メンバー不足に起因する。<br/> ETCDクラスタ停止時間が長くなる場合に発生します。 <br />リーダーがいるのか、 中断されたETCDメンバーがいることを確認。 |

| アラーム ID | **ETC-012** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | HighFsyncDurations |
| 持続時間 | 10分 |
| 発生条件 | 最近5分間の wal fsync持続時間の 99パーセンタイル値が 500msを超える場合 <br />(wal fsync: ログエントリを適用する前に、ディスクに保存する時に呼び出される) |
| 処理 | [ETCDメトリック文書](https://github.com/coreos/etcd/blob/master/Documentation/metrics.md/)によると、 ディスクに問題がある場合に発生すること。 |

| アラーム ID | **ETC-013** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | HighCommitDurations |
| 持続時間 | 10分 |
| 発生条件 | 最近5分間のコミット持続時間の99パーセンタイル値が 250msを超える場合<br/>（backend commit: ディスクの最近の変更の増分スナップショットの<br/>コミットします。） |
| 処理 | [ETCDメトリック文書](https://github.com/coreos/etcd/blob/master/Documentation/metrics.md/)によると、 ディスクに問題がある場合に発生すること。 |

* #### General

| アラーム ID | **GEN-001** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | TargetDown |
| 持続時間 | 10分 |
| 発生条件 | メトリックの収集作業がない場合に発生。 いくつかの操作が失敗なのか表示。 |
| 処理 | Prometheusのログと、 そのタスクに対応するPodの ログとイベントを確認する。 |

| アラーム ID | **GEN-002** |
| :--- | :--- |
| レベル | ~~none~~ |
| アラーム名 | DeadMansSwitch |
| 持続時間 | すぐに |
| 発生条件 | DeadMansSwitch通知します。 |
| 処理 | このアラームは、 ユーザーに通知されません。 |

| アラーム ID | **GEN-003** |
| :--- | :--- |
| レベル | **critical** |
| アラーム名 | TooManyOpenFileDescriptors |
| 持続時間 | 10分 |
| 発生条件 | file descriptor使用率が 95％以上の時に発生 |
| 処理 | ノードのLimit値を変更する。（ノードの再起動が必要） |

| アラーム ID | **GEN-004** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | FdExhaustionClose |
| 持続時間 | 10分 |
| 発生条件 | 単純回帰分析（simple linear regression）を利用して、<br/>4時間以内にfile descriptor枯渇が予測される場合に発生 |
| 処理 | そのPodのログとイベントを確認する。 必要な場合には、<br/>ノードのLimit値を変更する。 （ノードの再起動が必要） |

| アラーム ID | **GEN-005** |
| :--- | :--- |
| レベル | **critical** |
| アラーム名 | FdExhaustionClose |
| 持続時間 | 10分 |
| 発生条件 | 単純回帰分析（simple linear regression）を利用して、<br/>1時間以内にfile descriptor枯渇が予測される場合に発生 |
| 処理 | そのPodのログとイベントを確認する。 必要な場合には、<br/>ノードのLimit値を変更する。 （ノードの再起動が必要） |

* #### Kube-ApiServer

| アラーム ID | **KAS-001** |
| :--- | :--- |
| レベル | **critical** |
| アラーム名 | K8SApiserverDown |
| 持続時間 | 5分 |
| 発生条件 | kube-apiserver メトリック収集がない場合に発生 |
| 処理 | Prometheusの ログとkube-apiserverの ログとイベントを確認する。<br/>必要な場合には、 Podを再起動する。 |

| アラーム ID | **KAS-002** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | K8SApiServerLatency |
| 持続時間 | 10分 |
| 発生条件 | 最近10分間のリクエスト待機時間の 99パーセンタイル値が<br/>1sよりも大きい場合に発生 |
| 処理 | 引き続き発生する場合は、 マスターノードを増設する。 |

* #### Kube-ControllerManager

| アラーム ID | **KCM-001** |
| :--- | :--- |
| レベル | **critical** |
| アラーム名 | K8SControllerManagerDown |
| 持続時間 | 5分 |
| 発生条件 | kube-controller-managerの メトリックの収集ができない場合に発生 |
| 処理 | Prometheusのログとkube-controller-managerの ログとイベントを確認する。<br/>必要な場合には、 Podを再起動する。 |

* #### Kube-Scheduler

| アラーム ID | **KSC-001** |
| :--- | :--- |
| レベル | **critical** |
| アラーム名 | K8SSchedulerDown |
| 持続時間 | 5分 |
| 発生条件 | kube-scheduler メトリック収集がない場合に発生 |
| 処理 | Prometheusのログとkube-schedulerの ログとイベントを確認する。<br/>必要な場合には、 Podを再起動する。 |

* #### Kube-State-Metrics

| アラーム ID | **KSM-001** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | DeploymentGenerationMismatch |
| 持続時間 | 15分 |
| 発生条件 | Deploymentに設定した generationと収集された generationが異なる場合に発生 |
| 処理 | Deploymentのログとイベントを確認する。 必要であればDeploymentを再配布する。 |

| アラーム ID | **KSM-002** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | DeploymentReplicasNotUpdated |
| 持続時間 | 15分 |
| 発生条件 | Deploymentに設定した replica数と変更されたり、<br/>available状態のreplica数が異なる場合に発生 |
| 処理 | Deployment変更が反映さがない状態なので、<br/>DeploymentとPodのログとイベントを確認する。 |

| アラーム ID | **KSM-003** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | DaemonSetRolloutStuck |
| 持続時間 | 15分 |
| 発生条件 | DaemonSetに状態が Readyではない Podがある場合に発生 |
| 処理 | そのDaemonsetとPodの ログとイベントを確認する。 |

| アラーム ID | **KSM-004** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | K8SDaemonSetsNotScheduled |
| 持続時間 | 10分 |
| 発生条件 | DaemonSetに実行されてすることがPod数よりも、 実行中のPod数が小さい場合に発生 |
| 処理 | そのDaemonsetとPodのログとイベントを確認する。 <br />配布がないされたノードが正常であることを確認する。 <br />マスターノードが隔離された場合には、 Daemonsetに<br/>toleration設定がされているかどうかを確認する。 |

| アラーム ID | **KSM-005** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | DaemonSetsMissScheduled |
| 持続時間 | 10分 |
| 発生条件 | DaemonSetに間違っスケジュールされた Podが生じた場合に発生 |
| 処理 | そのDaemonsetとPodの ログとイベントを確認する。|

| アラーム ID | **KSM-006** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | PodFrequentlyRestarting |
| 持続時間 | 10分 |
| 発生条件 | 最近1時間の間Pod再起動回数が 5回以上の場合に発生 |
| 処理 | そのPodのログとイベントを確認する。 必要であればPodを再起動する。 |

* #### Kubelet

| アラーム ID | **KBL-001** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | K8SNodeNotReady |
| 持続時間 | 1時間 |
| 発生条件 | Nodeの状態が Readyではない場合に発生 |
| 処理 | そのノードの状態とイベントを確認する。 ssh経由でノードに接続して<br/>kubeletの状態を確認する。 |

| アラーム ID | **KBL-002** |
| :--- | :--- |
| レベル | **critical** |
| アラーム名 | K8SManyNodesNotReady |
| 持続時間 | 1分 |
| 発生条件 | クラスタ全体でNodeの 状態がReadyではない割合が 20％以上である場合に発生 |
| 処理 | そのノードの状態とイベントを確認する。 ssh経由でノードに接続して<br/>kubeletの状態を確認する。 |

| アラーム ID | **KBL-003** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | K8SKubeletDown |
| 持続時間 | 1時間 |
| 発生条件 | クラスタ全体で 3％以上のkubeletメトリック収集がない場合に発生 |
| 処理 | Prometheusのログと、 そのノードの状態とイベントを確認する。<br/> ssh経由でノードに接続してkubeletの状態を確認する。 |

| アラーム ID | **KBL-004** |
| :--- | :--- |
| レベル | **critical** |
| アラーム名 | K8SKubeletDown |
| 持続時間 | 1時間 |
| 発生条件 | クラスタ全体で 10％以上のkubeletメトリック収集がない場合に発生 |
| 処理 | Prometheusのログと、 そのノードの状態とイベントを確認する。<br/> ssh経由でノードに接続してkubeletの状態を確認する。 |

| アラーム ID | **KBL-005** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | K8SKubeletTooManyPods |
| 持続時間 | すぐに |
| 発生条件 | Nodeの配置されたPodの 数が100を超えると発生 （制限は110） |
| 処理 | 制限値に達すると、 それ以上Pod生成がしない。 他のノードの状態も同様に<br/>確認して余裕がない場合は、 ノードを増設する。 |

* #### Node

| アラーム ID | **NOD-001** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | NodeExporterDown |
| 持続時間 | 10分 |
| 発生条件 | NodeExporterメトリックの 収集ができない場合に発生 |
| 処理 | Prometheusの ログとNodeExporterの ログとイベントを確認する。<br/>必要な場合には、 Podを再起動する。 |

| アラーム ID | **NOD-002** |
| :--- | :--- |
| レベル | **critical** |
| アラーム名 | K8SNodeOutOfDisk |
| 持続時間 | すぐに |
| 発生条件 | Nodeの状態が OutOfDiskときに発生 |
| 処理 | そのノードのディスクを増設する。 |

| アラーム ID | **NOD-003** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | K8SNodeMemoryPressure |
| 持続時間 | すぐに |
| 発生条件 | Nodeの状態が MemoryPressureときに発生 |
| 処理 | そのノードのメモリを増設する。 |

| アラーム ID | **NOD-004** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | K8SNodeDiskPressure |
| 持続時間 | すぐに |
| 発生条件 | Nodeの状態が DiskPressureときに発生 |
| 処理 | ノードでは、 ログ、 未使用dodkcer image、 pv backupなどを削除して<br/>ディスク領域を確保する。 <br />引き続き発生する場合は、 そのノードのディスクを増設する。 |

| アラーム ID | **NOD-005** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | NodeCPUUsage |
| 持続時間 | 30分 |
| 発生条件 | Node最近5分間の平均CPU使用率が 90％を超える場合に発生 |
| 処理 | そのノードのCPUを増設する。 |

| アラーム ID | **NOD-006** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | NodeMemoryUsage |
| 持続時間 | 30分 |
| 発生条件 | Node Memory使用量が 90％を超える場合に発生 |
| 処理 | そのノードのメモリを増設する。 |

* #### Prometheus

| アラーム ID | **PRM-001** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | PrometheusFailedReload |
| 持続時間 | 10分 |
| 発生条件 | Prometheusの設定変更時、 設定の再読み込み処理失敗時に発生 |
| 処理 | そのPodのログを確認して ConfigMapの設定エラーを修正する。 |

* #### Cocktail

| アラーム ID | **CKT-001** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | PvLowRequestDisk |
| 持続時間 | 30分 |
| 発生条件 | PVが要求されたディスクのサイズに比べ使用量が 80％を超えると発生 |
| 処理 | PVのサイズを増やす。 ただし、 サーバーを再配布必要があること。 |

| アラーム ID | **CKT-002** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | PvLowTotalDisk |
| 持続時間 | 30分 |
| 発生条件 | PVがマウントされたディスクのサイズに比べ使用量が 80％を超えると発生 |
| 処理 | マウントされたディスクの状態を確認して未使用のPVを削除する。<br/>必要であれば、 ディスクを増設する。 |

| アラーム ID | **CKT-003** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | PodCPULimitUsage |
| 持続時間 | 30分 |
| 発生条件 | Resource Limit設定値に比べCPU使用率が 90％を超えると発生 |
| 処理 | 引き続き発生する場合は、 DeploymentのCPU Limit値を変更 |

| アラーム ID | **CKT-004** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | PodMemoryLimitUsage |
| 持続時間 | 30分 |
| 発生条件 | Resource Limit設定値に比べMemory使用率が 90％を超えると発生 |
| 処理 | 引き続き発生する場合は、 DeploymentのMemory Limit値を変更 |



