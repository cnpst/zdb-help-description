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
+ Auto Failover : HA 구조 일 경우 auto failover 기능을 지원 합니다.
    ```  
    3초마다 live 여부를 체크하며 10회 실패시 failover 가 자동으로 수행 됩니다.
    제약 사항
    1. primary 와 secondary 의 파라미터 설정이 동일 해야 합니다. (event_scheduler 제외)
    2. primary 1 node + secondary 1 node 로 구성된 HA 구조여야 합니다.
    ```
