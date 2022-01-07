## &#9724; Main
생성 할 수 있는 서비스의 유형을 선택 할 수 있습니다.

+ MariaDB 
  - Standalone : 1개 POD 만을 이용해 서비스를 제공합니다.  
  - High Availability : 2개 이상의 POD 를 이용해 서비스를 제공합니다.  
+ PostgreSQL
  - Standalone : 1개 POD 만을 이용해 서비스를 제공합니다.  
  - High Availability : 2개 이상의 POD 를 이용해 서비스를 제공합니다.  
+ MongoDB
  - Standalone : 1개 POD 만을 이용해 서비스를 제공합니다.  
  - ReplicaSet : 2개 이상의 POD 를 이용해 서비스를 제공합니다.  
+ Redis
  - Standalone : 1개 POD 만을 이용해 서비스를 제공합니다.  
  - High Availability : 2개 이상의 POD 를 이용해 서비스를 제공합니다.  
  - Cluster : 
+ Kafka
  - Standalone : 1개 POD 만을 이용해 서비스를 제공합니다.  
  - Multi Broker : 2개 이상의 POD 를 이용해 서비스를 제공합니다.  
+ RabiitMQ
  - Standalone : 1개 POD 만을 이용해 서비스를 제공합니다.  
  - Multi Broker : 2개 이상의 POD 를 이용해 서비스를 제공합니다.  
```
High Availability, Cluster, Multi Broker 는 고가용성 구성으로 운영 서비스에 적합 합니다.
POD 는 쿠버네티스에서 이용되는 Container의 관리 단위로 생성/관리/배포 가능한 가장 작은 단위의 유닛이며 Cluster 내에서 실제 Application 이 구동되는 Object 입니다.
```
