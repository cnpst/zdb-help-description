## &#9724; Service 
해당 서비스가 위치한 Namespace, 설정한 Tag, DB 서비스 Version 정보 등 전반적인 정보를 확인할 수 있습니다..  
+ <code>[ Actions ]</code> : 추가 기능을 제공 합니다.
  - Overview : 전체적인 상태를 표현  
  - Monitoring : 서비스에 대한 모니터링 기능  
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
  - Management : 유저 권한 관리 기능
  - Shutdown : 서비스 종료 기능  
  - Restart : 서비스를 재시작 기능  
  - Delete : 서비스 삭제 기능  

### 서비스 구성 정보
+ Name : 서비스명
+ Type : 서비스 종류
+ Tags : 시스템 및 사용자 Tag를 표기 하며, Default 시스템 Tag는 다음과 같습니다.
  - standalone : standalone 구조
  - ha : HA 구조
  - backup : backup 기능 사용
  - failover : failover 기능 사용
+ Health : 현재 서비스 상태 정보를 표기 하며, 상태 정보는 다음과 같습니다.  
  - Running : 정상
  - Initializing : 서비스 생성 초기화 중
  - StorageInitializing : 스토리지 생성 중
  - PodInitializing : Pod 생성 중
  - Terminating : 종료중
  - ShutDown : 종료
  - Failed : 서비스 생성 실패
  - Warning : 경고
  - NotReady : 서비스 생성중
  - StorageResizePending : 스토리지 리사이즈 실행시 발생 
  - 기타 : Failed, Not, BackOff, Err, Unhealthy, Unschedulable  
    ```
    Running 상태가 아닐 경우 [ More ] 버튼을 클릭하여 내용을 확인 할 수 있습니다.
    Logs 기능을 이용하여 서비스를 제공하는 POD 의 로그를 확인 할 수 있습니다.
    Monitoring 기능을 이용하여 리소스와 서비스 정보를 확인 할 수 있습니다.
    ```
+ Namespace : 현재 서비스의 네임스페이스를 표기 합니다.
+ Version : 현재 서비스의 Version 정보를 표시합니다.
+ __[ Refresh ]__ : 서비스에 변경 된 항목들을 새로고침 하며, 리소스가 변경 되어 이벤트 발생 시 자동으로 갱신 됩니다
+ __[ More ]__ : 정상메세지 이외의 INfo, Waring, Error정보들 표현합니다. 버튼을 Click 하면 사용자 요청에 의해 실행되거나 시스템 오퍼레이터로부터 식별된 서비스의 장애 정보 혹은 상태 정보를 사용자에게 실시간 제공합니다. 
이벤트 정보는 최초 발생 후 중복 발생하지 않으며 1시간 후 삭제되는 휘발성 이벤트 입니다.
     ```
  - 서비스 및 스토리지 생성/삭제/수정/재시작
  - DB Failover
  - Replication Error
  - 알람
  - 환경설정 변경
     ```
