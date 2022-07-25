## &#9724; Topology
Provisioning 된 데이터 서비스 인스턴스의 물리적인 Instance의 구성(Avaiable Zone, Node)과 논리적인 데이터 서비스 Topology 정보(HA 구성 시 Master/Slave의 관계와 Replication 상태, Cluster 구성인 경우 Cluster Member의 Role과 상태 등)를 제공하며, Pod의 로그나 상태를 확인하거나 Topology의 변경 기능을 제공합니다.
서비스를 제공하는 Instance 들의  구성을 확인 할 수 있습니다.  

+ <code>[ Expand ]</code> : 추가 정보를 제공 합니다.
+ <code>[ Actions ]</code> : 추가 기능을 제공 합니다.
  - Refresh : 구성 정보를 갱신하여 확인 할 수 있습니다.

### Topology 구성 정보
![image](https://user-images.githubusercontent.com/78724621/180754648-7bfc18da-12a9-4a46-ae21-93cb234e1943.png)

+ Role(Number) : 서비스의 역할을 나타냅니다. Number는 Instance의 개수를 나타냅니다.
  - Primary : read/write가 모두 가능한 role을 가지며 한개의 Instance를 포함합니다.
  - Secondary : read only만 가능한 role을 가지며 구성에 따라 한개 또는 여러개의 Instance를 포함합니다.

```
 PRIMARY 는 장애가 발생 했을 경우 SECONDARY 로 FAILOVER 될 수 있습니다.  
 Instance의 이름이 primary 이더라도 HA 환경에서 PRIMARY 나 SECONDARY 역할을 수행 할 수 있습니다.
```
+ Instance Name : Instance명을 나타냅니다
+ Replication Status : replication 상태를 나타냅니다.
  -	Running : Replication이 정상 작동합니다.
  -	Stop : Replication이 중단되었습니다.
  -	Error : Replication 동작시 에러가 발생하였습니다.
  -	Delay : Replication 지연이 발생하였습니다.(1800초 이상)
+ Instance IP : Instance의 IP를 나타냅니다.
+ Host : Node의 IP를 나타냅니다.
+ Zone : Instance가 속한 노드의 가용영역을 나타냅니다.

### Mariadb(HA) Topology 구성 정보
![image](https://user-images.githubusercontent.com/78724621/180757127-cc17b816-fe6a-4ad7-a8c4-de6cf7c8ba9d.png)
+ Primary : read/write가 모두 가능한 role을 가지며 한개의 Instance를 포함합니다.
+ Secondary : read only만 가능한 role을 가지며 구성에 따라 한개 또는 여러개의 Instance를 포함합니다.
+ <code>[ Actions ]</code> : 추가 기능을 제공 합니다.
    - Show Log : 선택된 인스턴스(Pod)의 Log 정보를 나타냅니다.
      - Slow Log : 선택된 Instance에서 발생한 Slow Query관련 Log 정보가 조회됩니다.
      - Error Log : 선택된 Instance에서 발생한 Error 관련 Log 정보가 조회됩니다.
    - Replication : Replication과 관련된 기능을 Secondary에서 제공합니다.
      - status : Replication 상태 정보를 제공합니다.
      - stop slave : Replication을 중지합니다.
      - start slave : Replication을 시작합니다.
    - Restart : 선택된 Instance에 대해 재시작 합니다.
### Postgresql(HA) Topology 구성 정보
![image](https://user-images.githubusercontent.com/78724621/180757355-0e796a69-22d7-4efe-8799-94449df0b0ce.png)
+ Primary : read/write가 모두 가능한 role을 가지며 한개의 Instance를 포함합니다.
+ Standby : read only만 가능한 role을 가지며 구성에 따라 한개 또는 여러개의 Instance를 포함합니다.
+ Pgpool : postgresql 서비스 사용 시  pgpool role을 가지며 구성에 따라 한개 또는 여러개의 Instance를 포함합니다.
+ <code>[ Actions ]</code> : 추가 기능을 제공 합니다.
    - Show Log : 선택된 Instance(Pod)의 Log 정보를 나타냅니다.
      - Postgresql Log  : 선택된 Instance에서 발생한 Log를 조회합니다. Primary와 Standby에서만 조회 가능합니다.
      - Pgpool Log : 선택된 Instance에서 발생한 Log를 조회합니다. Pgpool에서만 조회 가능합니다.
    - Replication : Replication과 관련된 기능을 Primary에서 제공합니다.
      - status : Replication 상태 정보를 제공합니다.
      ```
      pg_stat_replication view를 통해 replication 상태를 제공 합니다.
      ```
    - Restart : 선택된 Instance에 대해 재시작 합니다.
### Mongodb(HA) Topology 구성 정보
![image](https://user-images.githubusercontent.com/78724621/180758340-587cb849-8844-4370-b70b-166767a466d9.png)
+ Primary : read/write가 모두 가능한 role을 가지며 한개의 Instance를 포함합니다.
+ Secondary : read only만 가능한 role을 가지며, 2개의 인스턴스를 포함합니다.
+ <code>[ Actions ]</code> : 추가 기능을 제공 합니다.
    - Show Log : 선택된 Instance(Pod)의 Log 정보를 나타냅니다.
    - Restart : 선택된 Instance에 대해 재시작 합니다.

### Redis(HA) Cluster Topology 구성 정보
![image](https://user-images.githubusercontent.com/78724621/180759191-eca4fc54-5152-4486-9771-d1ec1aae4a1f.png)
+ Master : read/write가 모두 가능한 role을 가지며 구성에 따라 1개 또는 여러개의 인스턴스를 포함합니다.
+ Replicas : read only만 가능한 role을 가지며 구성에 따라 1개 또는 여러개의 인스턴스를 포함합니다.
+ <code>[ Actions ]</code> : 추가 기능을 제공 합니다.
    - Show Log : 선택된 Instance(Pod)의 Log 정보를 나타냅니다.
      - Log : 선택된 인스턴스에서 발생한 Log를 조회합니다.
    -	Failover : Failover를 수행합니다.
    -	Restart : 선택된 Instance에 대해 재시작 합니다.

### Kafka(Multi Broker) Topology 구성 정보
![image](https://user-images.githubusercontent.com/78724621/180759673-8c1bed83-3fa1-4bfd-8b83-d089568c8812.png)
+ Broker : message broker로서 전달받은 메시지를 전달해주는 role을 가지며, 여러 개의 인스턴스를 포함합니다.
+ Zookeeper : kafka 서비스 사용시 zookeeper role을 가지며 구성에 따라 여러 개의 인스턴스를 포함합니다.
+ <code>[ Actions ]</code> : 추가 기능을 제공 합니다.
    - Show Log : 선택된 Instance(Pod)의 Log 정보를 나타냅니다.
      - Log : 선택된 인스턴스에서 발생한 Log를 조회합니다.
    -	Restart : 선택된 Instance에 대해 재시작 합니다.

