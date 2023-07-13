## &#9724; Service 
전체적인 서비스의 상태와 구성을 확인 할 수 있습니다.  
+ <code>[ Actions ]</code> : 추가 기능을 제공 합니다.
  - Overview : 전체적인 상태를 표현  
  - Alert : 서비스의 alert 설정 및 임계치변경 가능 
  - Monitoring : 서비스에 대한 모니터링 기능  
    - Resource Monitor : 리소스 사용량에 대한 모니터링 가능. 30분, 1시간, 3시간, 6시간, 12시간 단위로 확인 할 수 있습니다.
    - Service Status : 서비스 상태, 쿼리 속도 지연 상태 등 다양한 상태 정보를 확인 할 수 있습니다. 서비스 Type 에 따라 지원되지 않을 수 있습니다.
    - Advanced Monitor : 전문가를 위한 모니터링 뷰로 서비스에 대한 상세한 메트릭들이 그래프로 제공 됩니다. OAuth 로그인을 지원합니다.
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
  - StartUp : 서비스 시작 기능  
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
  - Failed : 서비스 비정상으로 즉시 서비스 확인 필요
  - Warning : 서비스 중 일부 Pod 이 비정상
  - NotReady : 서비스 생성되었으나 구성에 실패하여 재구성 필요
  - 기타 : Failed, Not, BackOff, Err, Unhealthy, Unschedulable  
    ```
    Running 상태가 아닐 경우 [ More ] 버튼을 클릭하여 내용을 확인 할 수 있습니다.
    Logs 기능을 이용하여 서비스를 제공하는 POD 의 로그를 확인 할 수 있습니다.
    Monitoring 기능을 이용하여 리소스와 서비스 정보를 확인 할 수 있습니다.
    ```
+ Namespace : 현재 서비스의 네임스페이스를 표기 합니다.
+ __[ More ]__ : 서비스에서 발생한 1시간 이내의 이벤트들을 표현합니다.
  - 서비스 및 스토리지 생성/삭제/수정/재시작
  - DB Failover
  - Replication Error
  - 알람
  - 환경설정 변경
  
