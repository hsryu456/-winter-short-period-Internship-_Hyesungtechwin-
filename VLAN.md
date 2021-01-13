# ⛓ VLAN(Virtual LAN)

* 기존 LAN(_Local Area Network_)의 경우, LAN상의 모든 컴퓨터가 브로드캐스트(_broadcast_) 패킷을 받음으로서 트래픽(_traffic_)이 발생한다.

* VLAN은 논리적으로 구분된 가상의 LAN을 구현한 것이다. 다시 말해, 하나의 네트워크를 서브넷 단위로 나누어 각 서브넷에 속한 장비들끼리만 통신이 가능하도록 해준 것.

* 다른 VLAN에 속한 호스트 간에 통신을 하려면 반드시 라우터를 거쳐야 한다.

        -VLAN을 사용하면 네트워크가 분리되므로 혀용된 대상만 접근이 가능하여 보안문제를 해결할 수 있고, 트래픽을 감소시킬 수 있다.
        -또한, 장비의 추가 없이 차단된 LAN 환경을 구축할 수 있다.(비용 절감)

- - -
### **< VLAN 구성도 >**   
    -같은 식별자의 VLAN끼리만 통신가능(VLAN10 - VLAN10, VLAN20 - VLAN20)
<img src="https://user-images.githubusercontent.com/62328584/104273077-c1c1a400-54e1-11eb-90d6-cf10dcc24f5a.JPG" width="750px" height="300px"></img><br/>

<img src="https://user-images.githubusercontent.com/62328584/104273703-912e3a00-54e2-11eb-8e01-9a9e58496cd1.JPG" width="750px" height="300px"></img><br/>

<img src="https://user-images.githubusercontent.com/62328584/104274036-48c34c00-54e3-11eb-8145-988cd7bf86ba.JPG" width="750px" height="300px"></img><br/>

- - -   

### **< VLAN 트렁킹(_Trunking_) >**
* 여러개의 VLAN을 구축한 네트워크에서 VLAN들을 한번에 전송(하나의 통합 링크로)하는 방식을 말한다.

<img src="https://user-images.githubusercontent.com/62328584/104279376-8a58f480-54ed-11eb-879a-49ab0a9c5fb2.JPG" width="750px" height="300px"></img><br/>

    -스위치에는 여러 개의 VLAN이 있을 수 있는데 그에 따른 각각의 링크가 필요하다.
    -이때, 너무 많은 링크가 필요해지는 상황을 예방하기위해 트렁크 기능을 활용한다. 위의 사진에서 VLAN이 4개(A, B, C, D) 이기 때문에 스위치간 링크도 4개를 구현해야하지만, 트렁킹 설정으로 인해 단 하나의 링크만 있어도 되는 것이다.
    => 모든 패킷을 하나의 통합 링크를 통해 보내므로 각 패킷이 포함된 VLAN 정보를 알 수 없다. 따라서 패킷에 자신의 VLAN 정보를 넣어 보내는 방식을 사용함(Tagging).



### **< VTP(_VLAN Trunking Protocol_) >**   
* 스위치들 간에 VLAN 정보를 주고 받아 스위치들이 가지고 있는 VLAN 정보를 동기화시켜 주기 위한 프로토콜

    * 대부분의 Cisco Catalyst 시리즈 제품에서 사용할 수 있는 Cisco 독점 프로토콜









