## &#9724; Resource
서비스의 메모리와 CPU 를 설정 할 수 있습니다.

+ Namespace Quota : 선택한 Namespace 에 할당 할 수 있는 리소스를 표시 합니다.
+ Resource Request
  - Cpu/Memory Preset : CPU 와 Memory 가 같이 자동 조정 됩니다. 해지시 개별적으로 설정 할 수 있습니다.
  - Same as Mater : 모든 POD 의 리소스를 Master POD 와 동일하게 설정 할 수 있습니다. 해지시 Master 와 개별적으로 설정 할 수 있습니다.
+ Master : Master POD 의 리소스를 설정 합니다.
  - Memory : POD 의 메모리를 설정 합니다. (단위 Mi = Megabyte)
  - CPU : POD 의 CPU 를 설정 합니다. (단위 1000m = 1 Core)
  - <code>[ Check ]</code> : 설정한 리소스를 사용할 수 있는지 검사 합니다.
