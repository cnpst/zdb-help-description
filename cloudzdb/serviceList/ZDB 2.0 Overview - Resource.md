## &#9724; Resource
서비스를 제공하는 POD 의 리소스에 대한 현황을 확인 할 수 있습니다.    
+ <code>[ Expand ]</code> : 추가 정보를 제공 합니다.
  - Storage : 저장소에 대한 정보
  - Ojbect Storage : 백업 파일이 저장되는 저장소에 대한 정보
  - Object : 백업 파일이 저장되는 저장소에 존재하는 파일 리스트

### Resource 구성 정보
+ Status  : 리소스의 상태를 나타냅니다.
    - <code>[ running ]</code> : 정상
    - <code>[ warning ]</code> : 서비스 정상, 이슈 발생
      ```
      서비스가 정상 제공되고 있더라도 발생한 문제는 해결 해야 합니다.
      ```
    - <code>[ critical ]</code> : 장애 발생
      ```
      서비스가 정상 제공 되고 있지 않으므로 즉시 이슈를 확인하고 해결 해야 합니다.
      ```
+ Name : 리소스 이름을 확인 할 수 있습니다.
+ Role : 리소스 역할을 확인 할 수 있습니다.
+ CPU : CPU 사용률을 나타냅니다. (단위 1000m = 1 Core)
    ```  
    CPU 사용량이 과도하게 높으면 서비스 지연이 발생 할 수 있습니다.
    과도하게 높은 CPU 사용량이 지속 될 경우 리소스 증설이나 DB, AP 성능 최적화를 고려 해야 합니다.
    ```
+ Memory : Memory 사용률을 나타냅니다. (단위 Mi = 메가바이트)
    ```  
    Memory 사용량이 100% 가 되면 서비스 장애가 발생합니다.
    과도하게 높은 Memory 사용률은 서비스 DOWN 의 위험성에 대한 정보로 인식해야 하며 리소스 증설이나 DB, AP 성능 최적화를 고려 해야 합니다.
    ```
+ Data Storage : Storage 사용률을 나타냅니다. (단위 Gi = 기가바이트)
    ```  
    Storage 사용량이 100% 가 되면 서비스 장애가 발생 합니다.
    Storage 사용량 모니터링을 통해 여유 있는 공간을 항상 확보 해야 합니다.
    ```
+ Uptime  : 리소스 가동 시간을 나타냅니다.
    ```  
    가장 최근에 시작된 이후로 얼마의 시간이 지났는지 알 수 있습니다.
    ```
+ Zone : POD 가 할당된 노드의 영역 정보를 확인 할 수 있습니다.
+ <code>[ Actions ]</code> : 추가 기능을 제공 합니다.
  - Scale Up/Down : CPU 와 메모리를 변경 할 수 있습니다.
  - Show Log : 서비스를 제공하는 POD 의 로그를 확인 할 수 있습니다.  
    　　　　　이벤트 발생에 대한 내용을 로그를 통해 확인 할 수 있습니다. 
  - Monitoring : 30분, 1시간, 3시간, 6시간, 12시간 단위로 CPU Usage, Memory Usage, Storage Usage 를 확인 할 수 있습니다.
  - Object Info : 서비스를 제공하는 Kubernetes Resource 에 대한 정보를 확인 할 수 있습니다.  
    　　　　　　Kind : Kubernetes Resource 의 종류로 포함되는 Resource 
  - Restart : 서비스를 제공하는 POD 를 재시작 할 수 있습니다.
