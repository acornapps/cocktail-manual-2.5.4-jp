### 3.1.1 클러스터 추가

---

클러스터를 추가 등록할 수 있는 기능이다.

##### a\)    클러스터 → 오른쪽 상단 + 모양의 버튼을 클릭한다.

![](/assets/2.3.2 클러스터추가.png)

##### b\)   기본 정보\(이름, k8s 버전, 설명\)를 입력한다.![](/assets/2.3.0 클러스터 추가2.png)

| **기본 정보** | 설명 |
| :--- | :--- |
| 이름 | 등록할 클러스터의 이름 |
| k8s 버전 | 클러스터에 설치된 Kubernetes의 버전정보. e.g) 1.8.13 |
| 설명 | 클러스터에 대한 사용자 설명 |

##### c-1\) 프로바이더 정보\(계정, 유형, 리전\)를 입력한다.

계정의 프로바이더와 유형에 따라 입력란이 변경된다. Baremetal의 경우, 리전은 Default값을 제공하며, 변경이 가능하다. ![](/assets/2.3.0 클러스터 추가3.png)

| **프로바이더** | **설명** |
| :--- | :--- |
| 계정 | 등록된 계정 |
| 유형 | Kubernetes의 사용 유형으로 MANAGED, PROVIER, GKE중 선택 |
| 리전 | Kubernetes가 설치된 서버의 리전 |

| **유형** | **설명** |
| :--- | :--- |
| MANAGED | CUBE Installer를 이용하여 kubernetes를 구성한 클러스터. |
| PROVIDER | Public Cloud의 VM을 이용하여 Kubernetes를 이용하지만 Public Cloud를 이용할 경우에 사용한다.\(로드밸런서와 스토리지 등 기타 서비스를 이용할 경우\) |
| GKE | Google Cloud Platform의 Google Kubernetes Engine으로 구성한 클러스터 |

#### ㅤ

* **프로바이더 유형 - MANAGED**![](/assets/2.3.0 클러스터 추가3-1.png)

| **추가입력** | **설명** |
| :--- | :--- |
| 노드 포트 URL | 노드에 포트를 붙여 서비스 노출하는 방식에서 포트 앞에 사용할  IP서비스\(Master IP or Loadbelancer IP\) |
| 노드 포트 범위 | 노드에 포트를 붙여 서비스 노출하는 방식에서 IP뒤에 사용할 포트의 범위.\(30000~32767 권장\) |

#### ㅤ

* **프로바이더 유형 - PROVIDER**![](/assets/2.3.0 클러스터 추가3-2.png)ㅤ

#### ㅤ

* **프로바이더 유형 - GKE**![](/assets/2.3.0 클러스터 추가3-3.png)

| **추가입력** | **설명** |
| :--- | :--- |
| 프로젝트 아이디 | Google Cloud Platform의 계정이 사용할 프로젝트의 아이디\(GKE를 사용할 프로젝트\) |

##### 

##### d\)   모니터링 정보\(계정, 유형, 리전\)를 입력한다.![](/assets/2.3.0 클러스터 추가4.png)

| **모니터링 정보 ** | **설명** |
| :--- | :--- |
| 마스터 URL | kubernetes API 주소. "[https://host:port](https://host:port)" 형식을 사용한다. |
| Ingress Host | 인그레스 방식에 사용할 Host IP Address 서비스\(Master IP or Loadbelancer IP\) |
| 모니터링 호스트 | Monitoring API가 설치되어 있는 서버의 IP 주소" [http://host](http://host)" |
| 모니터링 포트 | Monitoring API의 포트 정보 |
| 모니터링 사용자 | InfluxDB 사용자 ID값 |
| 모니터링 비밀번호 | InfluxDB 사용자 PW값 |

##### e\)   클러스터 유형을 입력한다.![](/assets/2.3.0 클러스터 추가6.png)

| **클러스터 유형 정보** | **설명** |
| :--- | :--- |
| 인증 유형 | k8s 클러스터를 사용하기 위한 인증수단 |

#### ㅤ

* **인증 유형 - certification**![](/assets/2.3.0 클러스터 추가6-1.png)

| 인증 정보 | **설명** |
| :--- | :--- |
| 사용자 아이디 | k8s 사용자 ID |
| 패스워드 | k8s 사용자 PW |
| Cluster CA Certification | 마스터 서버 접속 후 /etc/kubernetes/pki 경로 이동 후 ca.crt파일 값 입력 |
| Client Certificate Data | 마스터 서버 접속 후 /etc/kubernetes/pki 경로 이동 후 admin.crt 파일 값 입력 |
| Client Key Data | 마스터 서버 접속 후 /etc/kubernetes/pki 경로 이동 후 admin.key 파일 값 입력 |



