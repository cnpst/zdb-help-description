# Overview
## 1. 서비스 정보
서비스의 기본정보들을 확인할 수 있으며,목록 선택 메뉴를 통해 각 서비스의 자세한 내용을 확인 할 수 있습니다.
### 1.1 목록
<!-- 표 -->
|         구분        | 설명   |  
|:---: | :--- |  
| Overview                 | 기본 페이지로 Resource, Connection info, Topology에 대한 정보를 보여줍니다.  |  
| Monitoring                 | 모니터링 페이지로 리소스 모니터링을 제공합니다. |
| Logs                  | 서비스에 대한 로그 정보를 제공합니다.   |  
| Tags                  | 사용자가 Tag를 만들거나 삭제 할 수 있습니다. |
| Events                  | 콘솔 UI 사용에 대한 Event를 기록 합니다.  |  
| Backup                  | 서비스에 대해 스케쥴 백업 설정 및 사용자 백업을 할 수 있습니다. |
| Configuration                  | 서비스에 대한 파라메터등 구성정보를 정의 합니다.  |  
| Shutdown                  | 서비스를 종료합니다. |
| Restart                   | 서비스를 재시작합니다. |

### 1.2 서비스 구성 정보
+ Name : 서비스명을 표기 합니다.
+ Type  : 시스템 Tag 및 사용자 Tag를 표기 합니다.
+ Tag  : 시스템 Tag 및 사용자 Tag를 표기 하며, 시스템 Tag는 다음과 같습니다.

<!-- 표 -->
  |         구분        | 설명   |  
  |:---: | :--- |  
  | ha                  | HA 구조  |  
  | backup                  | backup 기능 사용 |
  | failover                   | failover 기능 사용   |  
  | public                    | public endpoint 사용   |  

+ Health : 현재 서비스 상태 정보를 표기 하며, 상태 정보는 다음과 같습니다.
<!-- 표 -->
  |         구분        | 설명   |  
  |:---: | :--- |  
  | Running                   | 정상  |  
  | Initializing                   | 서비스 생성 초기화중. |
  | StorageInitializing                    | 스토리지 생성 중   |  
  | PodInitializing                     | Pod 생성 중   |  
  | Terminating                       | 종료중   |
  | ShutDown                      | 종료   |  
  | Failed                      | 서비스 생성 실패   |
  | Warning                       | 경고 ( ha 의 경우 slave 가 shutdown 인경우, pod 가 running 상태가 아닌 pod 가 포함된 경우   |
  | NotReady                        | 서비스 생성중 statefulset or deployment 가 생성이 완료되지 않은 경우  |
  | 기타                        | Failed, Not, BackOff, Err, Unhealthy, Unschedulable   |
  
  + Namespace : 현재 서비스의 네임스페이스를 표기 합니다.
  + More : 정상메세지 이외의 INfo, Waring, Error정보들 표현합니다.
       - 서비스 및 스토리지 생성/삭제/수정/재시작
       - DB Failover
       - Replication Error
       - 알람
       - 환경설정 변경
## 2. Resource
서비스의 POD에 대한 Resource 사용을 표기 합니다. 
### 2.1 Resource 화면 구성
+ Status  : 정상, 비정상을 나타냅니다.
+ Name : POD명을 나타냅니다.
+ Role : HA 구성은 Primary와 Secondary Role로 구성됩니다. 
+ CPU(m) : CPU 사용률을 나타냅니다.
+ Memory(M) : Memory 사용률을 나타냅니다.
+ Storage(GB) : Storage 사용률을 나타냅니다.
+ Uptime  : POD가 기동된 시간을 나타냅니다
+ Actions : 각 POD들에 대한 Resource를 수정하거나 재기동 할 수 있으며, 모니터링을 할수 있습니다.
       - 모니터링
               * 모니터링
               * Event
               * Object Info  
       - 목록 보기   
               * Scale Up/Down 
               * Storage Scale Up
               * Show Log
               * Object Info
               * Advanced Monitoring   
               * Restart   
## 3. Connection Info
서비스에 대한 연결 정보를 제공 합니다.
### 3.1 연결 정보
+ Admin Account : 초기 접속을 위한 admin 계정을 확인할 수 있습니다.
+ Admin Password : admin 계정에 대한 Pasword를 확인 할 수 있습니다. 기본값은 랜덤하게 제공되며 마스킹 처리됩니다. 패스워드 확인이 필요한경우 보기 버튼을 클릭합니다. 패스워드 복사 및 수정이 가능합니다.
+ Port : 서비스 접속을 위한 포트 확인이 가능합니다 설정을 통해 변경 가능합니다.
+ Cluster : Cluster IP에 대해 network 설정을 확인 할 수 있습니다. Public Network로 설정한 경우 공개적으로 액세스할 수 있습니다. Private Network는 내부에서만 엑세스가 가능 합니다.
+ Connection String : Jdbc를 통한 엑세스를 위한 Connection String을 제공 합니다.
+ Command Line :  터미널 엑세스를 위한 접속 Command를 제공 합니다.

## 4. Connection Info
Topology를 통해 서비스의 구성을 확인할 수 있습니다.
H/A를 구성할 경우 Primary와 Secondary를 확인할 수 있습니다.
