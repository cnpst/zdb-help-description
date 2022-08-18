## &#9724; Service Status
서비스 상태, 네트워크 연결 상태, 쿼리 속도 지연 상태 등 다양한 상태 정보를 확인 할 수 있습니다. 

### Mariadb Service Status
  - Service Status : DB 서비스의 상태를 나타냅니다.
    - Name : 서비스의 Instance명
    - Roles :  서비스 역할
    - DB Status : DB 상태를 정의 합니다.
      -	Running : 서비스 정상 
      -	Stop : 서비스 Stop
    - Replication Status : Replication 상태를 나타냅니다.
      -	Running : 복제 동작중
      -	Stop : 복제 중지 상태
      -	Delay : 복제 지연(1800s 이상)
      -	Error : 복제 오류
    - DB Uptime : DB가 기동된 시간
    - <code>[ Action ]</code> : 추가 정보를 제공 합니다. 
      - Error Log : Logs 페이지로 연결되며, Error Log를 확인 할 수 있습니다.
      -	Replication Status : Secondary에 대한 Replication 상태를 확인할 수 있습니다.

  - Connection Status : DB 클라이언트 연결 상태가 표시 됩니다.
    - Name : 서비스의 Instance명
    - Max Connection Count : Parameter에 정의된 접속가능한 최대 Connection 수
    - Connection Count : DB에 접속된 Connection 수
    - Active Connection Count : DB에 접속된 세션 중 Active한 Connection 수
    - Connection Count Rate(%) : 최대 Connection 대비 접속된 Connection 의 비율
    - <code>[ Action ]</code> : 추가 정보를 제공 합니다. 
      - Connection Status : (준비중)

  - Slow Query Status : DB Slow Query 상태를 나타냅니다.
    - Name : 서비스의 Pod명
    -	Slow Query Count : 15초 동안의 Slow Query 개수
    -	Slow Query Count Rate(%) :  Slow Query 비율 (지원예정)
    -	Slow Query Setting Time : Slow 쿼리 기준 시간 표기
    - <code>[ Action ]</code> : 추가 정보를 제공 합니다. 
      - Slow Query Session Status : 시간순으로 Active Session 정보를 확인 할 수 있습니다.
          
  - Replication Delay Status : DB Replication 상태를 나타냅니다.
    -	Name : 서비스의 Instance명
    -	Status : 복제 진행 상태
      - Running : 복제 동작중
      - Stop : 복제 중지 상태 (stop slave)
      - Delay : 복제 지연(1800s 이상)
      - Error : 복제 오류
    -	Lags(s) : Replication Delay 시간
    - <code>[ Action ]</code> : 추가 정보를 제공 합니다. 
      - Replication Status : (준비중)
      
  - Lock Status : DB Lock 상태를 나타냅니다.
    - Name : 서비스의 Pod명
    - Row Lock Count : Row Lock으로 Waiting하는 Session의 개수
    - Metadata Lock Count : Metadata Lock으로 Waiting하는 Session의 개수
    - Lock Duration Time(s) :  Lock으로 Waiting하는 Session중 가장 오랫동안 대기하는 세션의 시간
    - <code>[ Action ]</code> : 추가 정보를 제공 합니다.
      - Row Lock Status : DML에 의한 Lock 정보를 확인 할 수 있습니다.
      - Metadata Lock Status : DDL에 의한 Lock 정보를 확인 할 수 있습니다.
      ```
      Lock 정보는 Lock에 의한 Waiting Session이 존재할경우에 표기 됩니다.
      ```

### PostgreSQL Service Status
  - Service Status : DB 서비스의 상태를 나타냅니다.
    - Name : 서비스의 Instance명
    - Role :  서비스 역할
    - DB Status : DB 상태를 정의 합니다.
      -	Running : 서비스 정상 
      -	Stop : 서비스 Stop 
    - Replication Status : Replication 상태를 나타냅니다. 
      -	Running : 복제 동작중
      -	Stop : 복제 중지 상태
      -	Delay : 복제 지연 (50 MB 이상의 지연이 발생)
    - Repmgr Status : Replication 상태를 나타냅니다.
      -	Running : Repmgr 동작중
      -	Stop : Repmgr 중지 상태
      -	Error : Repmgr 오류
         ex) Pod의 Member-role과 repmgr의 Role이 같지 않을때 Error 표기
    - DB Uptime : DB가 기동된 시간
    - <code>[ Action ]</code> : 추가 정보를 제공 합니다. 
      - Repmgr Cluster Show : Repmgr의 상태정보를 제공 합니다.
      -	Replication Status : Replication의 상태정보를 제공 합니다.
      ```
      Repmgr의 상태정보는 "repmgr cluster show"를 통해 제공 됩니다.
      Repliation의 상태정보는 각 Instance는 아래 PostgreSQL View를 통해 제공 됩니다.
      Primary : pg_stat_replication
      Secondary : pg_stat_wal_receiver
      ```
  - Pgpool Status : Pgpool 서비스의 상태를 나타냅니다.
    - Name : 서비스의 Instance명
    - Pgpool Status : 서비스 역할
      -	Running : Pgpool 서비스 정상
      -	Stop : Pgpool 서비스 중지
      -	Error : Pgpool 서비스 에러 
        ex) pgpool pod의 Primary member role과 host의 pg_role이 일치하지 않을때)
    - <code>[ Action ]</code> : 추가 정보를 제공 합니다. 
      - Pgpool Show Nodes : Pgpool의 상태정보를 제공 합니다.
      ```
      Pgpool의 상태정보는 "show pool_nodes"를 통해 제공 됩니다.
      ```
  - Vacuum Status : Vacuum에 대한 상태를 나타냅니다.
    - Name : 서비스의 Instance명
    - Oldest Current Xid : 가장 오래된 xid 값
    - Perecnt Towards Wraparound : "2000000000" 값 대비 "Oldest Current Xid"의 비율
    - Perecnt Towards Emergency Autovac : "autovacuum_freeze_max_age" 값 대비 "Oldest Current Xid"의 비율
      ```
      "Perecnt Towards Wraparound" ,"Perecnt Towards Emergency Autovac"의 값이 계속 증가한다면, 
      Autovacuum이 잘 작동하고 있는지 체크가 필요 합니다.
      ```
