## &#9724; Storage
서비스가 사용하는 저장소에 대한 설정을 할 수 있습니다.

+ Data Storage
  - Storage Source : 사용할 수 있는 Storage 소스를 선택 할 수 있습니다.
  - Storage Type : 사용할 수 있는 Storage 유형을 선택 할 수 있습니다.
  - Size(GiB) : 용량을 설정 할 수 있습니다. (단위 GiB = Gigabyte)
    ```
    custom : 값을 직접 설정 할 수 있습니다.
    ```
  - QoS(IOPS/GiB) : GiB 마다 초당 I/O 작업 수입니다.
  - Provisioned IOPS : QoS 와 요청된 볼륨 크기를 곱하면 Provisioned IOPS 값이 됩니다. (최소값 100)
+ Advanced
  - Storage Auto Scle-up : 저장소 크기가 자동 증가하도록 합니다. (미지원)
