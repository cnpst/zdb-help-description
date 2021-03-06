# Overview
  
───────────────────────────────────────────────────────
  
## &#9724; Service 
전체적인 서비스의 상태와 구성을 확인 할 수 있습니다.  
+ <code>[ Actions ]</code> : 추가 기능을 제공 합니다.
  - Overview : 전체적인 상태를 표현  
  - Monitoring : 서비스에 대한 모니터링 기능  
    ```
    리소스와 서비스의 상세한 모니터링을 수행 할 수 있습니다.
    ```
  - Logs : 로그 확인 기능  
  - Tags : 태그 기능  
    ```
    사용자 정의 태그를 통해 서비스에 대한 정보를 표현 할 수 있습니다.
    ```
  - Events : 서비스에 대한 이벤트 정보 확인  
  - Backup : 서비스에 백업 기능  
    ```
    백업 설정과 결과를 확인 할 수 있으며 복원을 수행 할 수 있습니다.
    ```
  - Configuration : 환경 설정 관리 기능  
  - Shutdown : 서비스 종료 기능  
  - Restart : 서비스를 재시작 기능  
  - Delete : 서비스 삭제 기능  

### 서비스 구성 정보
+ Name : 서비스명
+ Type : 서비스 종류
+ Tag : 시스템 및 사용자 Tag를 표기 하며, Default 시스템 Tag는 다음과 같습니다.
  - ha : HA 구조
  - backup : backup 기능 사용
  - failover : failover 기능 사용
  - public : public endpoint 사용
+ Health : 현재 서비스 상태 정보를 표기 하며, 상태 정보는 다음과 같습니다.  
  - Running : 정상
  - Initializing : 서비스 생성 초기화 중
  - StorageInitializing : 스토리지 생성 중
  - PodInitializing : Pod 생성 중
  - Terminating : 종료중
  - ShutDown : 종료
  - Failed : 서비스 생성 실패
  - Warning : 경고
  - NotReady : 서비스 생성중
  - 기타 : Failed, Not, BackOff, Err, Unhealthy, Unschedulable  
    ```
    Running 상태가 아닐 경우 [ More ] 버튼을 클릭하여 내용을 확인 할 수 있습니다.
    Logs 기능을 이용하여 서비스를 제공하는 POD 의 로그를 확인 할 수 있습니다.
    Monitoring 기능을 이용하여 리소스와 서비스 정보를 확인 할 수 있습니다.
    ```
+ Namespace : 현재 서비스의 네임스페이스를 표기 합니다.
+ __[ More ]__ : 정상메세지 이외의 INfo, Waring, Error정보들 표현합니다.
  - 서비스 및 스토리지 생성/삭제/수정/재시작
  - DB Failover
  - Replication Error
  - 알람
  - 환경설정 변경
  
───────────────────────────────────────────────────────
  
## &#9724; Resource
서비스를 제공하는 POD 의 리소스에 대한 현황을 확인 할 수 있습니다.    
+ <code>[ Expand ]</code> : 추가 정보를 제공 합니다.
  - Storage : 저장소에 대한 정보
  - Ojbect Storage : 백업 파일이 저장되는 저장소에 대한 정보
  - Object : 백업 파일이 저장되는 저장소에 존재하는 파일 리스트

### Resource 구성 정보
+ Status  : 리소스의 상태를 나타냅니다.
    - <code>[ Running ]</code> : 정상
    - <code>[ Warning ]</code> : 서비스 정상, 이슈 발생
      ```
      서비스가 정상 제공되고 있더라도 발생한 문제는 해결 해야 합니다.
      ```
    - <code>[ Critical ]</code> : 장애 발생
      ```
      서비스가 정상 제공 되고 있지 않으므로 즉시 이슈를 확인하고 해결 해야 합니다.
      ```
+ Name : 리소스 이름
+ Role : 리소스 역할
+ CPU : CPU 사용률을 나타냅니다. (단위 1000m = 1 Core)
    ```  
    CPU 사용량이 과도하게 높으면 서비스 지연이 발생 할 수 있습니다.
    과도하게 높은 CPU 사용량이 지속 될 경우 리소스 증설이나 DB, AP 성능 최적화를 고려 해야 합니다.
    ```
+ Memory : Memory 사용률을 나타냅니다. (단위 Mi = 메가바이트)
    ```  
    Memory 사용량이 100% 가 되면 서비스 장애가 발생합니다.
    과도하게 높은 Memory 사용률은 서비스 DOWN 의 위험성에 대한 정보로 인식해야 하며 리소스 증설이나 DB, AP 성능 최적화를 고려 해야 합니다.
    ```
+ Storage : Storage 사용률을 나타냅니다. (단위 Gi = 기가바이트)
    ```  
    Storage 사용량이 100% 가 되면 서비스 장애가 발생 합니다.
    Storage 사용량 모니터링을 통해 여유 있는 공간을 항상 확보 해야 합니다.
    ```
+ Uptime  : 리소스 가동 시간을 나타냅니다.
    ```  
    가장 최근에 시작된 이후로 얼마의 시간이 지났는지 알 수 있습니다.
    ```
+ <code>[ Actions ]</code> : 추가 기능을 제공 합니다.
  - Scale Up/Down : CPU 와 메모리를 변경 할 수 있습니다.
  - Show Log : 서비스를 제공하는 POD 의 로그를 확인 할 수 있습니다.  
    　　　　　이벤트 발생에 대한 내용을 로그를 통해 확인 할 수 있습니다. 
  - Monitoring : 30분, 1시간, 3시간, 6시간, 12시간 단위로 CPU Usage, Memory Usage, Storage Usage 를 확인 할 수 있습니다.
  - Object Info : 서비스를 제공하는 Kubernetes Resource 에 대한 정보를 확인 할 수 있습니다.  
    　　　　　　Kind : Kubernetes Resource 의 종류로 포함되는 Resource 
  - Restart : 서비스를 제공하는 POD 를 재시작 할 수 있습니다.
  
───────────────────────────────────────────────────────
   
## &#9724; Connection Info
데이터베이스 접속 정보에 대해 확인 할 수 있습니다.  
+ <code>[ Expand ]</code> : 추가 정보를 제공 합니다. 
  - Connections, Network I/O 그래프를 확인 할 수 있습니다.
+ <code>[ Actions ]</code> : 추가 기능을 제공 합니다.
  -  Object Info : 모니터아이콘 눌렀을때 제공하는 Object Info 와 동일

### Connection Info 구성 정보
+ Admin Account : 서비스 관리자 계정 이름
+ Admin Password : 서비스 관리자 비밀번호
+ Port : 서비스 접속 Port 번호
+ Cluster (Cluster IP) : 동일 클러스터에 deploy 되어 있는 Pod 에서만 접속을 허용하는 Endpoint  
모든 서비스는 Cluster IP 가 존재합니다.
+ Private Network (Private Load Balancer) : 동일 Cloud Service Provider의 동일 VLAN/VPC 또는 Spanning 된 Virtual Network 환경에서 접속 가능한 Endpoint
+ Public Network (Public Load Balancer) : 인터넷 접점(Public)에 있는 Portable IP를 부여하여 어디에서나 접속할 수 있는 Endpoint
    ```  
    ON 이나 OFF 상태의 버튼 클릭 후 service name 입력을 하면 해당 기능을 ON, OFF 할 수 있습니다.
    ```
+ Connection String : jdbc 를 이용한 연결 명령어 예시
+ Command Line :  client tool 을 이용한 연결 명령어 예시
  
───────────────────────────────────────────────────────
  
## &#9724; Topology
서비스를 제공하는 POD 들의  구성을 확인 할 수 있습니다.  
+ <code>[ Expand ]</code> : 추가 정보를 제공 합니다.
+ <code>[ Actions ]</code> : 추가 기능을 제공 합니다.
  - Refresh : 구성 정보를 갱신하여 확인 할 수 있습니다.

### Topology 구성 정보
+ Replications : HA 구성 환경에 대한 정보
+ PRIMARY : HA 환경에서 primary Role 을 가진 POD 정보  
    ```  
    PRIMARY 는 장애가 발생 했을 경우 SECONDARY 로 FAILOVER 될 수 있습니다.  
    이와 같이 pod 의 이름이 primary 이더라도 HA 환경에서 PRIMARY 나 SECONDARY 역할을 수행 할 수 있습니다.
    ```
+ Replications : SECONDARY : HA 환경에서 secondary Role 을 가진 POD 정보  
    ```  
    SECONDARY 는 PRIMARY 장애가 발생 했을 경우 PRIMARY 로 FAILOVER 될 수 있습니다.  
    이와 같이 pod 의 이름이 secondary 이더라도 HA 환경에서 SECONDARY 나 PRIMARY 역할을 수행 할 수 있습니다.
    ```
+ <code>[ Actions ]</code> : 추가 기능을 제공 합니다.
    - Show Log : POD 의 로그를 확인 할 수 있습니다.
    - Failover : Failover 를 수행 시킬 수 있습니다.
    - Restart : POD 를 재기동 할 수 있습니다.
