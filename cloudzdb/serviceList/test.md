# Cloud Z DB v2.0 가이드 Sample

## 1. MariaDB

---
MySQL을 대체(MySQL과 동일한 소스 코드를 기반) 할 수 있는 오픈 소스의 관계형 데이터베이스 관리 시스템(RDBMS)으로
단순한 트랜잭션 처리와 읽기 성능이 중요한 OLTP 환경에 적합합니다.
```sql
SELECT straight_join
    DATE_FORMAT(now(), '%Y%m%d%H%i%s') nowtime,
    w.trx_mysql_thread_id waiting_thread,
    w.trx_id waiting_trx_id,
    w.trx_query waiting_query,
    b.trx_mysql_thread_id blocking_thread,
    b.trx_id blocking_trx_id,
    b.trx_query blocking_query,
    bl.lock_id blocking_lock_id,
    bl.lock_mode blocking_lock_mode,
    bl.lock_type blocking_lock_type,
    bl.lock_table blocking_lock_table,
    bl.lock_index blocking_lock_index,
    wl.lock_id waiting_lock_id,
    wl.lock_mode waiting_lock_mode,
    wl.lock_type waiting_lock_type,
    wl.lock_table waiting_lock_table,
    wl.lock_index waiting_lock_index
FROM
    information_schema.INNODB_LOCK_WAITS ilw ,
    information_schema.INNODB_TRX b ,
    information_schema.INNODB_TRX w ,
    information_schema.INNODB_LOCKS bl ,
    information_schema.INNODB_LOCKS wl
WHERE
    b.trx_id = ilw.blocking_trx_id
    AND w.trx_id = ilw.requesting_trx_id
    AND bl.lock_id = ilw.blocking_lock_id
    AND wl.lock_id = ilw.requested_lock_id\G;
```

## 2. MongoDB

---
확장 가능성 및 표준 준수를 강조하는 객체-관계형 데이터베이스 관리 시스템(ORDBMS)으로
복잡한 쿼리를 사용하는 OLTP 환경 또는 많은 저장 데이터를 분석하고 응용할수 있는 OLAP 환경에 적합합니다.
소규모의 애플리케이션에서부터 수많은 동시 접속 사용자가 있는 대규모 애플리케이션(또는 데이터 웨어하우스용)에 이르기까지 여러 부하를 관리할 수 있습니다.

| RDBMS       | MongoDB     |
| :---:       | :---:       |  
| Database    |  Database   |  
| Table       |  Collection |
| Tuple/Row   |  Document   |
| Column      |  Field      |
| Table Join  |  Embedded Documents |
| Primary Key |  Primary Key  (Default key _id provided by mongodb itself) |
  

### Database Server and Client  
| RDBMS         | MongoDB |
| :---:         | :---:   |  
| Mysqld/Oracle |  mongod |  
| mysql/sqlplus |  mongo  |
  

## 3. PostgreSQL

---
NoSQL 데이터베이스로 필요한 쿼리 제공 및 인덱싱을 활용해 원하는 수준의 확장성과 유연성을 제공하는 문서 데이터베이스입니다
JSON과 같은 동적 스키마형 도큐먼트 / 개발자 친화적  

<img src="https://github.com/cnpst/zdb-help-description/blob/main/resources/images/postgresql.png" width="300" height="200">




