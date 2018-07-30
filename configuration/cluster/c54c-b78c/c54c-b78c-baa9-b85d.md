#
# 5.5.1 アラームリスト

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
| 処理 | ETCDクラスタの状態を確認する。 Disk Latencyに起因する問題であることがありますので、 以下のコマンドをETCDクラスタノード全体で実行する。 \([ETCD Tuning](https://coreos.com/etcd/docs/latest/tuning.html#disk)\)<br /> ``$ sudo ionice -c2 -n0 -p `pgrep etcd` `` |

| アラーム ID | **ETC-003** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | HighNumberOfLeaderChanges |
| 持続時間 | すぐに |
| 発生条件 | 最近1時間の間、3回以上のリーダーの変更が発生した場合 |
| 処理 | ETCDクラスタの状態を確認する。 Disk Latencyに起因する問題であることがありますので、 以下のコマンドをETCDクラスタノード全体で実行する。 \([ETCD Tuning](https://coreos.com/etcd/docs/latest/tuning.html#disk)\)<br /> ``$ sudo ionice -c2 -n0 -p `pgrep etcd` `` |

| アラーム ID | **ETC-004** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | HighNumberOfFailedGRPCRequests |
| 持続時間 | 10分 |
| 発生条件 | 5分以内に gRPCメソッド呼び出しの 1％以上失敗した場合 |
| 処理 | ETCDクラスタと Kubernetesクラスタの 帯域幅を増やしたり、 クラスタの Sacale-Upが必要です。 |

| アラーム ID | **ETC-005** |
| :--- | :--- |
| レベル | **critical** |
| アラーム名 | HighNumberOfFailedGRPCRequests |
| 持続時間 | 5分 |
| 発生条件 | 5分以内にgRPCメソッド呼び出しの 5％以上失敗した場合 |
| 処理 | ETCDクラスタと Kubernetesクラスタの 帯域幅を増やしたり、 クラスタの Sacale-Upが必要です。 |

| アラーム ID | **ETC-006** |
| :--- | :--- |
| レベル | **critical** |
| アラーム名 | GRPCRequestsSlow |
| 持続時間 | 10分 |
| 発生条件 | 最近5分間gRPCメソッド要求の 待機時間の99パーセンタイル値が 150msを超える場合 |
| 処理 | ETCDクラスタと Kubernetesクラスタの 帯域幅を増やしたり、 クラスタの Sacale-Upが必要です。 |

| アラーム ID | **ETC-007** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | HighNumberOfFailedHTTPRequests |
| 持続時間 | 10分 |
| 発生条件 | 5分以内にHTTPエンドポイントへの 要求の1％以上が失敗した場合 |
| 処理 | ETCDクラスタと Kubernetesクラスタの 帯域幅を増やしたり、 クラスタの Sacale-Upが必要です。 |

| アラーム ID | **ETC-008** |
| :--- | :--- |
| レベル | **critical** |
| アラーム名 | HighNumberOfFailedHTTPRequests |
| 持続時間 | 5分 |
| 発生条件 | 5分以内にHTTPエンドポイントへの 要求の5％以上が失敗した場合 |
| 処理 | ETCDクラスタと Kubernetesクラスタの 帯域幅を増やしたり、 クラスタの Sacale-Upが必要です。 |

| アラーム ID | **ETC-009** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | HTTPRequestsSlow |
| 持続時間 | 10分 |
| 発生条件 | 最近5分間のHTTPリクエストの待機時間の 99パーセンタイル値が150msを超える場合 |
| 処理 | ETCDクラスタと Kubernetesクラスタの 帯域幅を増やしたり、 クラスタの Sacale-Upが必要です。 |

| アラーム ID | **ETC-010** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | EtcdMemberCommunicationSlow |
| 持続時間 | 10分 |
| 発生条件 | 最近5分間のメンバー間の通信の待機時間の 99パーセンタイル値が150msを超える場合 |
| 処理 | ETCDクラスタの帯域幅を増やしたり、 クラスタのScale-Upが必要です。 |

| アラーム ID | **ETC-011** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | HighNumberOfFailedProposals |
| 持続時間 | すぐに |
| 発生条件 | 最近1時間の間に5つ以上の失敗raft protocol要求がある場合。<br/>（RAFT ProtocolはETCD同期Protocol） |
| 処理 | [ETCDメトリック文書](https://github.com/coreos/etcd/blob/master/Documentation/metrics.md/)によると、 リーダー選出の一時的な障害やメンバー不足に起因する ETCDクラスタ停止時間が長くなる場合に発生します。 リーダーがいるのか、中断されたETCDメンバーがいることを確認 |

| アラーム ID | **ETC-012** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | HighFsyncDurations |
| 持続時間 | 10分 |
| 発生条件 | 최근 5분 동안의 wal fsync 지속 시간의 99번째 백분위가 500ms보다 클 경우<br /> \(wal fsync: 로그 항목을 적용하기 전에 디스크에 저장시 호출.\) |
| 処理 | [ETCD 메트릭 문서](https://github.com/coreos/etcd/blob/master/Documentation/metrics.md%29에) 따르면 디스크에 문제가 있을 경우 발생한다고 함. |

| アラーム ID | **ETC-013** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | HighCommitDurations |
| 持続時間 | 10分 |
| 発生条件 | 최근 5분 동안의 커밋 지속 시간 중 99번째 백분위가 250ms보다 클 경우<br /> \(backend commit: 디스크에 대한 최근 변경 사항의 증분 스냅 샷의 커밋.\) |
| 処理 | [ETCD 메트릭 문서](https://github.com/coreos/etcd/blob/master/Documentation/metrics.md%29에) 따르면 디스크에 문제가 있을 경우 발생한다고 함. |

* #### General

| アラーム ID | **GEN-001** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | TargetDown |
| 持続時間 | 10分 |
| 発生条件 | 메트릭 수집 작업이 안 될 경우 발생. 어떤 작업이 실패인지 표시됨. |
| 処理 | Prometheus의 로그 및 해당 작업에 해당하는 Pod의 로그 및 이벤트를 확인한다. |

| アラーム ID | **GEN-002** |
| :--- | :--- |
| レベル | ~~none~~ |
| アラーム名 | DeadMansSwitch |
| 持続時間 | すぐに |
| 発生条件 | DeadMansSwitch 알림. |
| 処理 | 해당 알람은 사용자에게 통지되지 않습니다. |

| アラーム ID | **GEN-003** |
| :--- | :--- |
| レベル | **critical** |
| アラーム名 | TooManyOpenFileDescriptors |
| 持続時間 | 10分 |
| 発生条件 | file descriptor 사용율이 95%이상 일때 발생 |
| 処理 | 노드의 Limit값을 변경한다.\(노드의 재시작 필요\) |

| アラーム ID | **GEN-004** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | FdExhaustionClose |
| 持続時間 | 10分 |
| 発生条件 | 단순회귀분석\(simple linear regression\)을 이용하여 4시간 이내에<br /> file descriptor 고갈이 예측될 경우 발생 |
| 処理 | 해당 Pod의 로그 및 이벤트를 확인한다.<br /> 필요할 경우, 노드의 Limit값을 변경한다.\(노드의 재시작 필요\) |

| アラーム ID | **GEN-005** |
| :--- | :--- |
| レベル | **critical** |
| アラーム名 | FdExhaustionClose |
| 持続時間 | 10分 |
| 発生条件 | 단순회귀분석\(simple linear regression\)을 이용하여 1시간 이내에<br /> file descriptor 고갈이 예측될 경우 발생 |
| 処理 | 해당 Pod의 로그 및 이벤트를 확인한다.<br /> 필요할 경우, 노드의 Limit값을 변경한다.\(노드의 재시작 필요\) |

* #### Kube-ApiServer

| アラーム ID | **KAS-001** |
| :--- | :--- |
| レベル | **critical** |
| アラーム名 | K8SApiserverDown |
| 持続時間 | 5分 |
| 発生条件 | kube-apiserver 메트릭 수집이 안 될 경우 발생 |
| 処理 | Prometheus의 로그 및 kube-apiserver의 로그와 이벤트를 확인한다.<br /> 필요할 경우, Pod를 재시작한다. |

| アラーム ID | **KAS-002** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | K8SApiServerLatency |
| 持続時間 | 10分 |
| 発生条件 | 최근 10분 동안의 요청 대기 시간 중 99번째 백분위가 1s보다 클 경우 발생 |
| 処理 | 계속 발생할 경우, 마스터 노드를 증설한다. |

* #### Kube-ControllerManager

| アラーム ID | **KCM-001** |
| :--- | :--- |
| レベル | **critical** |
| アラーム名 | K8SControllerManagerDown |
| 持続時間 | 5分 |
| 発生条件 | kube-controller-manager 메트릭 수집이 안 될 경우 발생 |
| 処理 | Prometheus의 로그 및 kube-controller-manager의 로그와 이벤트를 확인한다.<br /> 필요할 경우, Pod를 재시작한다. |

* #### Kube-Scheduler

| アラーム ID | **KSC-001** |
| :--- | :--- |
| レベル | **critical** |
| アラーム名 | K8SSchedulerDown |
| 持続時間 | 5分 |
| 発生条件 | kube-scheduler 메트릭 수집이 안 될 경우 발생 |
| 処理 | Prometheus의 로그 및 kube-scheduler의 로그와 이벤트를 확인한다.<br /> 필요할 경우, Pod를 재시작한다. |

* #### Kube-State-Metrics

| アラーム ID | **KSM-001** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | DeploymentGenerationMismatch |
| 持続時間 | 15分 |
| 発生条件 | Deployment에 설정한 generation과 수집된 generation이 다를 경우 발생 |
| 処理 | Deployment의 로그 및 이벤트를 확인한다.<br /> 필요하면 Deployment를 재배포한다. |

| アラーム ID | **KSM-002** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | DeploymentReplicasNotUpdated |
| 持続時間 | 15分 |
| 発生条件 | Deployment에 설정한 replica 개수와 변경되거나 available 상태의<br /> replica 개수가 다를 경우 발생 |
| 処理 | Deployment 수정 사항이 반영이 안 된 상태이므로 Deployment 및<br /> Pod의 로그 및 이벤트를 확인한다. |

| アラーム ID | **KSM-003** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | DaemonSetRolloutStuck |
| 持続時間 | 15分 |
| 発生条件 | DaemonSet에 상태가 Ready가 아닌 Pod가 있을 경우 발생 |
| 処理 | 해당 Daemonset과 Pod의 로그 및 이벤트를 확인한다. |

| アラーム ID | **KSM-004** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | K8SDaemonSetsNotScheduled |
| 持続時間 | 10分 |
| 発生条件 | DaemonSet에 실행되어 할 Pod 개수 보다 실행중인<br /> Pod 개수가 작을 경우 발생 |
| 処理 | 해당 Daemonset과 Pod의 로그 및 이벤트를 확인한다.<br /> 배포가 안 된 노드가 정상인지 확인한다.<br /> 마스터 노드가 격리된 경우, Daemonset에 toleration 설정이 되어 있는지 확인한다. |

| アラーム ID | **KSM-005** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | DaemonSetsMissScheduled |
| 持続時間 | 10分 |
| 発生条件 | DaemonSet에 잘못 스케쥴된 Pod가 생겼을 경우 발생 |
| 処理 | 해당 Daemonset과 Pod의 로그 및 이벤트를 확인한다. |

| アラーム ID | **KSM-006** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | PodFrequentlyRestarting |
| 持続時間 | 10分 |
| 発生条件 | 최근 1시간 동안 Pod 재시작 횟수가 5회 이상일 경우 발생 |
| 処理 | 해당 Pod의 로그 및 이벤트를 확인한다. 필요하면 Pod를 재시작한다. |

* #### Kubelet

| アラーム ID | **KBL-001** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | K8SNodeNotReady |
| 持続時間 | 1時間 |
| 発生条件 | Node 상태가 Ready가 아닐 경우 발생 |
| 処理 | 해당 노드의 상태 및 이벤트를 확인한다.<br /> ssh를 통해 노드에 접속하여 kubelet의 상태를 확인한다. |

| アラーム ID | **KBL-002** |
| :--- | :--- |
| レベル | **critical** |
| アラーム名 | K8SManyNodesNotReady |
| 持続時間 | 1分 |
| 発生条件 | 클러스터 전체에서 Node 상태가 Ready가 아닌 비율이 20%이상일 경우 발생 |
| 処理 | 해당 노드들의 상태 및 이벤트를 확인한다.<br /> ssh를 통해 노드에 접속하여 kubelet의 상태를 확인한다. |

| アラーム ID | **KBL-003** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | K8SKubeletDown |
| 持続時間 | 1時間 |
| 発生条件 | 클러스터 전체에서 3%이상의 kubelet 메트릭 수집이 안 될 경우 발생 |
| 処理 | Prometheus의 로그 및 해당 노드의 상태 및 이벤트를 확인한다.<br /> ssh를 통해 노드에 접속하여 kubelet의 상태를 확인한다. |

| アラーム ID | **KBL-004** |
| :--- | :--- |
| レベル | **critical** |
| アラーム名 | K8SKubeletDown |
| 持続時間 | 1時間 |
| 発生条件 | 클러스터 전체에서 10%이상의 kubelet 메트릭 수집이 안 될 경우 발생 |
| 処理 | Prometheus의 로그 및 해당 노드들의 상태 및 이벤트를 확인한다.<br /> ssh를 통해 노드에 접속하여 kubelet의 상태를 확인한다. |

| アラーム ID | **KBL-005** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | K8SKubeletTooManyPods |
| 持続時間 | すぐに |
| 発生条件 | Node의 배치된 Pod의 수가 100개가 넘으면 발생.\(제한값은 110\) |
| 処理 | 제한값에 도달할 경우, 더 이상 Pod 생성이 안됨.<br /> 다른 노드들의 상태도 같이 확인하여 여유가 없을 경우, 노드를 증설한다. |

* #### Node

| アラーム ID | **NOD-001** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | NodeExporterDown |
| 持続時間 | 10分 |
| 発生条件 | NodeExporter 메트릭 수집이 안 될 경우 발생 |
| 処理 | Prometheus의 로그 및 NodeExporter의 로그와 이벤트를 확인한다.<br /> 필요할 경우, Pod를 재시작한다. |

| アラーム ID | **NOD-002** |
| :--- | :--- |
| レベル | **critical** |
| アラーム名 | K8SNodeOutOfDisk |
| 持続時間 | すぐに |
| 発生条件 | Node 상태가 OutOfDisk일 때 발생 |
| 処理 | 해당 노드의 디스크를 증설한다. |

| アラーム ID | **NOD-003** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | K8SNodeMemoryPressure |
| 持続時間 | すぐに |
| 発生条件 | Node 상태가 MemoryPressure일 때 발생 |
| 処理 | 해당 노드의 메모리를 증설한다. |

| アラーム ID | **NOD-004** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | K8SNodeDiskPressure |
| 持続時間 | すぐに |
| 発生条件 | Node 상태가 DiskPressure일 때 발생 |
| 処理 | 노드에서 로그, 미사용 dodkcer image, pv backup등을 삭제하여 디스크 공간을 확보한다.<br /> 계속 발생할 경우, 해당 노드의 디스크를 증설한다. |

| アラーム ID | **NOD-005** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | NodeCPUUsage |
| 持続時間 | 30分 |
| 発生条件 | Node 최근 5분간 평균 CPU 사용량이 90%를 넘을 경우 발생 |
| 処理 | 해당 노드의 CPU를 증설한다. |

| アラーム ID | **NOD-006** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | NodeMemoryUsage |
| 持続時間 | 30分 |
| 発生条件 | Node Memory 사용량이 90%를 넘을 경우 발생 |
| 処理 | 해당 노드의 메모리를 증설한다. |

* #### Prometheus

| アラーム ID | **PRM-001** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | PrometheusFailedReload |
| 持続時間 | 10分 |
| 発生条件 | Prometheus의 설정 변경시, 설정 다시읽기 작업 실패시 발생 |
| 処理 | 해당 Pod의 로그를 확인하여 ConfigMap의 설정 오류를 수정한다. |

* #### Cocktail

| アラーム ID | **CKT-001** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | PvLowRequestDisk |
| 持続時間 | 30分 |
| 発生条件 | PV가 요청한 디스크의 크기 대비 사용량이 80%가 넘으면 발생 |
| 処理 | PV의 크기를 늘린다. 단, 서버를 재배포 해야함. |

| アラーム ID | **CKT-002** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | PvLowTotalDisk |
| 持続時間 | 30分 |
| 発生条件 | PV가 마운트된 디스크의 크기 대비 사용량이 80%가 넘으면 발생 |
| 処理 | 마운트된 디스크의 상태를 확인하고 미사용 PV를 제거한다.<br /> 필요하면 디스크를 증설한다. |

| アラーム ID | **CKT-003** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | PodCPULimitUsage |
| 持続時間 | 30分 |
| 発生条件 | Resource Limit 설정값 대비 CPU 사용율이 90%가 넘으면 발생 |
| 処理 | 계속 발생할 경우, Deployment의 CPU Limit 값 변경 |

| アラーム ID | **CKT-004** |
| :--- | :--- |
| レベル | warning |
| アラーム名 | PodMemoryLimitUsage |
| 持続時間 | 30分 |
| 発生条件 | Resource Limit 설정값 대비 Memory 사용율이 90%가 넘으면 발생 |
| 処理 | 계속 발생할 경우, Deployment의 Memory Limit 값 변경 |



