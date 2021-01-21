# 🔌 LLDP(_Link Layer Discovery Protocol_)
* 물리적인 망의 형상 정보와 상위 계층이 지원하는 기능들에 대한 정보, 그리고 자원들의 변경 상황을 알리는데 사용되는 새로운 제어 프로토콜이다.

* LLDP Neighbor (LLDP 인접 디바이스 정보) 페이지에는 인접 디바이스에서 수신한 정보가 포함되어 있다.

* LLDP를 사용할 경우 시스템 관리자가 특히 VLAN(가상 LAN), 링크 통합 등을 포함하는 복잡한 네트워크에서 결함이 있는 시스템 구성을 쉽게 감지할 수 있다.

* 서버, 스위치, 기타 네트워크 구성 장치 간 물리적 연결을 추적할 필요 없이 토폴로지에 대한 정보를 쉽게 얻을 수 있다.

- - -

### **< 광스위치 세 개를 연결한 모습 >**

-위 장비부터 192.168.0.2/192.168.0.3/192.168.0.4 IP를 가지고 있음

<img src="https://user-images.githubusercontent.com/62328584/105135167-eb5a7b00-5b32-11eb-939c-6e96fb5ce61b.jpg" width="550px" height="400px"></img><br/>

▶192.168.0.2 주소를 가진 장비의 경우 가운데 장비와 인접해(Neighbor) 있음을 알 수 있다.

<img src="https://user-images.githubusercontent.com/62328584/105136354-daab0480-5b34-11eb-9b87-15fe9aeabd01.png" width="1250px" height="250px"></img><br/>

<img src="https://user-images.githubusercontent.com/62328584/105137542-cff16f00-5b36-11eb-8c32-ead471d751c2.jpg" width="550px" height="400px"></img><br/>

▶192.168.0.3 주소를 가진 장비의 경우 위, 아래 장비와 인접해(Neighbor) 있음을 알 수 있다.

<img src="https://user-images.githubusercontent.com/62328584/105137617-f1525b00-5b36-11eb-93f8-dedbb86e059a.png" width="1250px" height="300px"></img><br/>

    -LLDP Neighbor기능을 통해 장비 간의 연결상태를 파악할 수 있다.
