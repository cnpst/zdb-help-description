## &#9724; Resource
서비스를 제공하는 Instance 의 리소스에 대한 현황을 확인 할 수 있습니다.    
+ <code>[ Expand ]</code> : 추가 정보를 제공 합니다.
  - Storage : 저장소에 대한 정보
  - Ojbect Storage : 백업 파일이 저장되는 저장소에 대한 정보

### Instance 구성 정보
+ Status  : 리소스의 상태를 나타냅니다.

    - <code>[ running ]</code> : 정상
    - <code>[ warning ]</code>: 서비스 중 일부 Instance가 Running 상태가 아닌 경우이거나 재시작(*)이 필요한 경우 <br>
               kafka: exporter deploy 배포x / broker, zookeeper sts 정상 배포 <br>
               postgresql: standby 비정상 <br>
    - <code>[ StorageResizePending ]</code> : 스토리지 리사이즈 실행시 발생
    - <code>[ Shutdown ]</code> : 서비스 종료
    - <code>[ Terminating ]</code> : 서비스 종료 중
    - <code>[ Failed ]</code> : 서비스 실행 오류 (statefulset, deployment 생성 실패)
    - <code>[ NotReady ]</code> : Deployment, statefulset 의 status 기준 ready 상태가 아닌 pod 가 존재하는 경우 <br>
             kafka : exporter deploy 정상 배포 / broker, zookeeper sts 배포x  <br>
             postgresql: primary/pgpool 비정상 <br>
    - <code>[ Initializing ]</code> : 서비스 생성 초기화 (statefulset, secret, configmap 등 생성 단계)
    - <code>[ Initializing ]</code> : 스토리지 생성 단계. PVC 가 Bound 상태가 되면 생성 완료
    - <code>[ PodInitializing ]</code> : 컨테이너에 스토리지가 마운트 되어 서비스 인스턴스가 실행되고 초기 데이터 생성 단계<br>
 
    ```
  서비스가 정상 제공되지 않고 있다면, 이슈를 확인하고 해결 해야 합니다.
    ```

+ Name : 리소스 이름
 - 서비스 종류 : mariadb, mongodb, postgresql, redis, kafka, rabbitmq
+ Role : 리소스 역할
    - Mariadb 
      - Primary : read/write가 모두 가능한 role을 가집니다.
      - Secondary : read only만 가능한 role을 가집니다. 
    - Mongodb 
      - Primary : read/write가 모두 가능한 role을 가집니다.
      - Secondary : read only만 가능한 role을 가집니다. 
      - Arbiter : read/write 모두 불가능한 role 입니다.
    - PostgreSQL 
      - Primary : read/write가 모두 가능한 role을 가집니다.
      - Secondary : read only만 가능한 role을 가집니다. 
      - Pgpool : postgresql 서비스에서 Connection을 위해 Pgpool을 이용할 경우 pgpool role을 가집니다.
        ```
        Cloud Z 서비스의 Pgpool은 connection pooling 과 load balancing을 위해 사용되며, 
        automatic failover는 Pgpool이 아닌 repmgr에 의해 수행됩니다.
        ```
        Pgpool에 대한 자세한 설명은 아래 Pgpool 메뉴얼 을 참고하시기 바랍니다.  
        https://www.postgresql.org/about/news/pgpool-ii-432-429-4112-4019-and-3724-released-2454/
      
    - redis 
      - Master  : read/write가 모두 가능한 role을 
      - Slave  : read only만 가능한 role을 가집니다.
    - kafka 
      - Broker  : : message broker로서 전달받은 메시지를 전달해주는 role을 가집니다. 
      - Zookeeper  : Zookeeper : kafka 서비스 사용시 zookeeper role을 가집니다.
    - rabbitmq 
      - Broker  : : message broker로서 전달받은 메시지를 전달해주는 role을 가집니다. 
+ CPU : CPU 사용률 (단위 1000m = 1 Core)
    ```  
    CPU 사용량이 과도하게 높으면 서비스 지연이 발생 할 수 있습니다.
    과도하게 높은 CPU 사용량이 지속 될 경우 리소스 증설이나 DB, AP 성능 최적화를 고려 해야 합니다.
    ```
+ Memory : Memory 사용률 (단위 Mi = 메가바이트)
    ```  
    Cloud Z 서비스는 Swap 을 제공하지 않으며, Memory 사용량이 100% 가 되면 서비스 장애가 발생합니다.
    과도하게 높은 Memory 사용률은 서비스 DOWN 의 위험성에 대한 정보로 인식해야 하며 리소스 증설이나 DB, AP 성능 최적화를 고려 해야 합니다.
    Secondary에서도 Read only등의 서비스를 제공할 경우 Failover 발생 시 Connection 증가량을 고려하여 리소스를 구성해야 합니다.
    ```
+ Data Storage : Storage 사용률 (단위 Gi = 기가바이트)
    ```  
    Storage 사용량이 100% 가 되면 서비스 장애가 발생 합니다.
    Storage 사용량 모니터링을 통해 여유 있는 공간을 항상 확보 해야 합니다.
    ```
+ Uptime  : 리소스 가동 시간
    ```  
    가장 최근에 시작된 이후로 얼마의 시간이 지났는지 알 수 있습니다.
    ```
+ Zone : POD 가 할당된 노드의 영역 정보
    ```
    AWS 리전의 가용영역을 나타내며 가용성을 위해 Primary와 Secondary는 각각 다른 Zone에 위치 해야 합니다.    
    ```
    리전 및 가용영역에 대한 설명은 아래 AWS 메뉴얼을 참고 하시기 바랍니다.  
    https://aws.amazon.com/ko/about-aws/global-infrastructure/regions_az/  
    
+ <code>[ Actions ]</code> : 추가 기능을 제공 합니다.
  - Scale Up/Down : CPU 와 메모리를 변경 할 수 있습니다.
  - Show Log : 서비스를 제공하는 POD 의 로그를 확인 할 수 있습니다.  
    　　　　　이벤트 발생에 대한 내용을 로그를 통해 확인 할 수 있습니다. 
  - Monitoring : 30분, 1시간, 3시간, 6시간, 12시간 단위로 CPU Usage, Memory Usage, Storage Usage 를 확인 할 수 있습니다.
  - Object Info : 서비스를 제공하는 Kubernetes Resource 에 대한 정보를 확인 할 수 있습니다.  
    　　　　　　Kind : Kubernetes Resource 의 종류로 포함되는 Resource 
  - Restart : 서비스를 제공하는 POD 를 재시작 합니다.
  - Shutdown : 서비스를 중지 합니다.
  - Startup : 서비스를 시작 합니다.

───────────────────────────────────────────────────────

### Storage 구성 정보
서비스를 제공하는 POD 의 저장소에 대한 현황을 확인 할 수 있습니다.    
+ <code>[ Action ]</code> : 추가 기능을 제공 합니다.
  - Primary Scale Up : Primary Role 을 가진 POD Scale Up 기능
  - Secondary Scale Up : Secondary Role 을 가진 POD Scale Up 기능
  - Add Backup Storage : 백업 스토리지 추가
+ Name : 저장소의 이름
+ Status : 저장소의 상태
+ Volume : POD 에 종속되는 디스크 이름
+ Storage Class : 저장소 종류
  ```
  efs-zdb : Amazone Elastic File System 으로 파일을 추가하고 제거할 때 자동으로 확장되고 축소되며 관리 또는 프로비저닝이 필요하지 않습니다.
  ebs-gp2 : Amazone Elastic Block Store 으로 사용이 쉽고 확장 가능한 고성능 블록 스토리지 입니다.
  ```
+ IOPS/GiB : GiB 마다 초당 I/O 작업 수
+ Size(GiB) : 저장소 사이즈
+ Age : 저장소가 생성된 이후 지난 시간
+ Actions : 추가 기능을 제공 합니다.
  - Monitoring : Storage 사용량에 대한 그래프를 확인 할 수 있습니다.
  - Object Info : Kubernetes Resource 의 yaml 내용과 설명을 확인 할 수 있습니다.
  - Change Setting : IOPS 및 Throughput을 변경 할 수 있습니다.
  ```
  efs-zdb Storage Class을 사용하는 Backup Storage는 IOPS 및 Throughput에 대해 변경 할 수 없습니다.
  ```
  EFS의 자세한 사항은 아래 메뉴얼을 참고 하시기 바랍니다.  
  https://docs.aws.amazon.com/ko_kr/efs/latest/ug/performance.html

### Object Storage 구성 정보
+ Name : Object Storage 이름
+ Created Time : Object Storage 생성 일시
+ Used Size : 총 사용량 (단위 Mi : 메가바이트)
+ Full Backup : Full Backup 파일이 사용한 사이즈
+ Incremental Backup : Incremental Backup 파일이 사용한 사이즈
+ Binlog Backup : Binlog Backup 파일이 사용한 사이즈
+ Etc Size : 기타 로그 파일이 사용한 사이즈
