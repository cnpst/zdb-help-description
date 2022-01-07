## &#9724; Backup
서비스에 대한 백업을 설정 할 수 있습니다.

+ Use Schedule Backup : 계획된 백업을 수행 할 수 있습니다.
  - 전체백업 수행주기 : 매일 받거나 주 1회 받도록 설정 할 수 있습니다.
  - 전체백업 수행시간 : 전체 백업 수행 시간을 정할 수 있습니다.
    ```
    업무가 가장 가벼운 시간대를 설정해야 합니다.
    ```
  - 보관기간 : 백업 파일 보관 기간을 설정 할 수 있습니다.
  - 수행모드 : 백업 수행 모드를 선택 할 수 있습니다.
    ```
    정상모드 : 
    저속모드 : 
    ```
  - 증분백업 활성화 : 증분 백업을 설정 할 수 있습니다.
    ```
    서비스를 운영함에 있어 전체 백업의 성능이나 사이즈가 부담스러울 경우 고려 할 수 있습니다.
    ```
  - 증분백업 수행주기 : 지정된 수행 주기를 선택 할 수 있습니다.
    ```
    1시간 간격 : 1시간 마다 수행 합니다.
    2시간 간격 : 2시간 마다 수행 합니다.
    6시간 간격 (06시 시작) : 6, 12, 18, 24 시에 수행 합니다.
    6시간 간격 (07시 시작) : 7, 13, 19, 1 시에 수행 합니다.
    6시간 간격 (08시 시작) : 8, 14, 20, 2 시에 수행 합니다.
    6시간 간격 (09시 시작) : 9, 15, 21, 3 시에 수행 합니다.
    6시간 간격 (10시 시작) : 10, 16, 22, 4 시에 수행 합니다.
    6시간 간격 (11시 시작) : 11, 17, 23, 5 시에 수행 합니다.
    12시간 간격 : 0, 12 시에 백업을 수행 합니다.
    24시간 간격 : 0 시에 백업을 수행 합니다.
    ```
  - binlog 백업 활성화 : PITR (시간기반복구) 를 하기 위해 필요한 옵션입니다.
  - binlog 백업 수행주기(분) : 분 단위로 수행 주기를 설정 할 수 있습니다.
+ Use Extra Backup Storage : 백업 전용 저장소를 사용 할 수 있습니다.
  - Storage Source : 사용할 수 있는 Storage 소스를 선택 할 수 있습니다.
  - Storage Type : 사용할 수 있는 Storage 유형을 선택 할 수 있습니다.
  - Size(GiB) : 용량을 설정 할 수 있습니다. (단위 GiB = Gigabyte)
  ```
  백업으로 인해 데이터가 저장 되어야할 저장소의 공간이 부족할 수 있습니다.
  운영 환경에서는 백업 전용 저장소를 사용하는 것이 좋습니다.
  ```