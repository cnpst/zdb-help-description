## &#9724; Connection Info
Provisioning 된 데이터 서비스 인스턴스에 Access 하기 위한 Endpoint 정보를 제공하며, 기본적으로 Cluster 내부의 Application에서만 접근하도록 허용하며, 네트워크 구성 및 클러스터 상태에 따라 Private/Public Load Balancer를 통해 Cluster 외부에서 Access를 지원합니다. 데이터 서비스 관리를 위한 admin 계정이 있는경우 계정 정보를 보여주고 변경하는 기능을 제공하며, HA(High Available) 구성이 된 데이터 서비스의 경우에는 Auto Failover를 설정하는 기능을 제공합니다.

+ <code>[ Expand ]</code> : 추가 정보를 제공 합니다. 
  - Connections : 서비스에 연결된 클라이언트 정보를 나타내며, HA 구조에서는 Primary, Secondary Instance에 대해 정보를 제공 합니다. 각 차트에 마우스를 올릴 경우 해당 시점의 Connection 정보를 확인 할 수 있습니다.
    -	connected : 서비스에 연결된 클라이언트 수
    -	used : 서비스에 연결된 최대 클라이언트 수
    -	max : 서비스에 연결 가능한 최대 클라이언트 수
  - Network I/O : 데이터 송수신 양을 나타내며, Network I/O는 하나의 그래프에 서비스의 모든 Instance가 포함됩니다.각 차트에 마우스를 올릴 경우 해당 시점의 Network I/O 정보를 확인 할 수 있습니다. 
    - tx : 전송된 데이터량
    - rx : 수신된 데이터량
+ <code>[ Actions ]</code> : 추가 기능을 제공 합니다.
  -  Monitoring : 서비스의 Network I/O를 모니터링 할 수 있습니다.
  -  Event : 서비스의 이벤트를 확인 할 수 있습니다.
  -  Object Info : 모니터아이콘 눌렀을때 제공하는 Object Info 와 동일
  -  Databases : 서비스의 DB List를 나타냅니다.
  -  System Variables : 서비스의 시스템 환경변수 List를 나타냅니다.
  -  Status Variables : 서비스의 Global Status List를 나타냅니다.
  -  Processes : 각 서비스 인스턴스에 띄워진 프로세스 정보를 나타냅니다.

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
