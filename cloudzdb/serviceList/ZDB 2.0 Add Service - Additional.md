## &#9724; Additional
서비스에 대한 추가적인 설정을 할 수 있습니다.

+ Database Name : 데이터베이스 이름을 설정 할 수 있습니다.
+ Character-set : 서비스가 지원하는 캐릭터셋 중 하나를 선택 할 수 있습니다.
+ Auto Failover : Master 노드 장애 발생시 임계 시간동안 서비스가 복구되지 않을 경우 자동으로 Slave 노드로 서비스를 전환합니다.
  ```
  5초 주기 5회 동안 Master POD 가 장애 상태로 인지 될 경우 Slave 가 Master 역할을 수행하게 됩니다.
  ```
+ Pgpool Loadbalancer Mode : PostgreSQL Pgpool 의 load_balance_mode 를 설정합니다. 
+ Advanced
  - Use Default Configuration : 기본 값을 사용하여 구성하게 됩니다. 서비스 생성 이후에도 설정 값은 변경할 수 있습니다.
    ```
    Master Config, Salve Config 를 동일한 구성으로 설정 하거나 서로 다른 구성으로 설정 할 수 있습니다.
    ```
