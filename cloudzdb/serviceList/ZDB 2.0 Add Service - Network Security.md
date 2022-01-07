## &#9724; Network & Security
서비스 Endpoint 와 비밀번호 설정을 할 수 있습니다.

+ Credential 
  - Admin Password Random Generation : 비밀번호가 랜덤하게 자동 생성 되는 것을 선택 합니다.
    ```
    체크 해지시 사용자가 직접 비밀번호를 설정 할 수 있습니다.
    ```
+ Service expose
  - Port : 포트 번호를 지정 할 수 있습니다.
  - Cluster (Cluster IP) : 동일 클러스터에 deploy 되어 있는 어플리케이션(Pod)에서만 접속을 허용하는 Endpoint를 제공합니다.
  - Private Network (Private Load Balancer) : 동일 Cloud Service Provider의 동일 VLAN/VPC 또는 Spanning 된 Virtual Network 환경에서 접속 가능한 Endpoint 를 제공합니다.
  - Public Network (Public Load Balancer) : 인터넷 접점(Public)에 있는 Portable IP를 부여하여 어디에서나 접속할 수 있는 Endpoint를 제공합니다.
    ```
    OFF 버튼 클릭시 ON 으로 설정됩니다.
    ```
+ Advanced
