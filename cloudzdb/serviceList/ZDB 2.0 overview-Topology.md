## &#9724; Topology
서비스를 제공하는 POD 들의  구성을 확인 할 수 있습니다.  
+ <code>[ Expand ]</code> : 추가 정보를 제공 합니다.
+ <code>[ Actions ]</code> : 추가 기능을 제공 합니다.
  - Refresh : 구성 정보를 갱신하여 확인 할 수 있습니다.

### Topology 구성 정보
+ Replications : HA 구성 환경에 대한 정보
+ PRIMARY : HA 환경에서 primary Role 을 가진 POD 정보  
    ```  
    PRIMARY 는 장애가 발생 했을 경우 SECONDARY 로 FAILOVER 될 수 있습니다.  
    이와 같이 pod 의 이름이 primary 이더라도 HA 환경에서 PRIMARY 나 SECONDARY 역할을 수행 할 수 있습니다.
    ```
+ Replications : SECONDARY : HA 환경에서 secondary Role 을 가진 POD 정보  
    ```  
    SECONDARY 는 PRIMARY 장애가 발생 했을 경우 PRIMARY 로 FAILOVER 될 수 있습니다.  
    이와 같이 pod 의 이름이 secondary 이더라도 HA 환경에서 SECONDARY 나 PRIMARY 역할을 수행 할 수 있습니다.
    ```
+ <code>[ Actions ]</code> : 추가 기능을 제공 합니다.
    - Show Log : POD 의 로그를 확인 할 수 있습니다.
    - Failover : Failover 를 수행 시킬 수 있습니다.
    - Restart : POD 를 재기동 할 수 있습니다.