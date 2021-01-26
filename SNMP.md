# 👨‍💻 SNMP(_Simple Network Management Protocol_)
* IP 네트워크상의 장치로부터 정보를 수집 및 관리하며, 또한 정보를 수정하여 장치의 동작을 변경하는 데에 사용되는 인터넷 표준 프로토콜이다. SNMP를 지원하는 대표적인 장치에는 라우터, 스위치, 서버, 워크스테이션, 프린터, 모뎀 랙 등이 포함된다.

* 네트워크에서 장치를 관리하기 위해 TCP/IP 프로토콜을 사용하는 framwork.

* SNMP 정보를 사용하여 장비 정보 검색, 파라미터 수정, 상태 모니터링, 네트워크 고장을 발견할 수 있다.

- - -
### **< 개요 및 기본개념 >**
* SNMP는 일반적으로, 하나 이상의 관리 컴퓨터("매니저(Manager)"라고 함)는 컴퓨터 네트워크에서 호스트나 장치들의 그룹을 관리하거나 감시하고, 에이전트에 정보를 요청하고 획득, 관리한다.

* 관리를 받는 각각의 시스템은 에이전트(Agent)라는 이름의 소프트웨어 구성 요소를 실행하여 SNMP를 통해 정보를 매니저로 전달한다.

▶ SNMP 관리 네트워크는 3가지 구성 요소를 이룬다.

     -매니지드 디바이스
     -에이전트: 매니지드 디바이스 위에 실행되는 소프트웨어
     -네트워크 관리국(Network management station, NMS): 매니저 위에 실행되는 소프트웨어

* 매니지드 디바이스는 SNMP 인터페이스를 구현하는 네트워크 노드로서, 노드에 특화된 정보에 대한 읽기 전용 또는 읽기/쓰기 접근을 허용한다.

* 에이전트는 관리되는 디바이스(네트워크 장치)에 상주하는 네트워크 관리 소프트웨어 모듈이다. 각 장비의 규격에 따라 장비의 정보를 수집, 저장한다. NMS의 요청을 받고 처리하며 경보가 발생하면 NMS에 알린다. (SNMP 네트워크의 피 관리자)

* 네트워크 관리국(NMS)은 매니지드 디바이스를 감시하고 제어하는 애플리케이션들을 실행한다. (SNMP 네트워크의 관리자)

<img src="https://user-images.githubusercontent.com/62328584/105144181-329b3880-5b40-11eb-89e3-d48c1fa90246.JPG" width="400px" height="400px"></img><br/>

### **< 동작 원리 >**
<img src="https://user-images.githubusercontent.com/62328584/105144537-b9501580-5b40-11eb-90b2-2eaf0d5ab7c8.JPG" width="800px" height="400px"></img><br/>

▶ SNMP에서는 총 4가지 메시지를 사용한다.

***메세지*** | 내용
-- | --
***Get*** | 가장 기본적인 SNMP 요청 메시지로, 매니저에서 에이전트로 특정 정보를 요청하기 위해 사용
***Get-next*** | Get과 같은 역할, **MIB**의 계층적 구조를 파악하여 모든 정보를 가져올 때 사용
***Set*** | 매니저에서 에이전트로 특정 값을 설정하기 위해 사용
***Trap*** | 에이전트에서 매니저로 전달해야 할 정보가 발생했을 경우 매니저에게 정보를 전달하기 위해 사용 

- - -
## 👨‍💻 MIB(_Management Information Base_)

* NMS에서 관리하는 특정 정보와 자원, 객체들은 트리구조를 가진다. 

* 망관리를 위해 사용되는 체계화(Hierarchically)된 관리 정보(Management Information)
     - 관리정보를 계층적 구조로 보관 관리하게 됨. 망 관리자원 정보를 구조화시킨 관리객체들의 집합

* MIB는 망관리용 프로토콜인 SNMP 등에 의해 읽혀짐

* 각 에이전트는 자체 MIB 라이브러리를 가지고 있으며 대상의 권한에 따라 NMS를 읽고 쓸 수 있다.

### **< 관리 대상(Managed Node) >**

* 망에서 관리되는 장치(관리대상객체)들
     - 통상, 정적 또는 동적 정보로서 관리된다.
     - 관리장치(NMS)가 그 내용을 얻고 변경한다.

* 관리되는 모든 자원들은 항상 객체로서 표현된다.
     - 바로 이 객체를 모아 놓은 조직적인 저장소가 MIB.

     모든 네트워크 장비들은 MIB 트리를 제공한다.

* 각각의 관리객체들은 **OID**(Object IDentifier)라는 번호를 통해 식별하고 접근하려 관리한다.

<img src="https://user-images.githubusercontent.com/62328584/105264839-0df0a080-5bd4-11eb-8c18-dda36985652d.JPG" width="800px" height="400px"></img><br/>

       ▶표현의 예
     1.3.6.1.2.1.1 -> {iso(1).org(3).dod(6).internet(1).mgmt(2).mib-2(1).system(1)}


▶ **mib-2 {1.3.6.1.2.1} 내의 객체**

  ※ SNMP에서 MIB 내의 객체들에 대해 주요한 11개의 범주로 나눌 수 있다.

  ㅇ **System (1) :** 장치의 이름, 위치, 기타 묘사 등 시스템의 전반적인 정보   

     - sysDescr(1), sysObjectID(2), sysUpTime(3), sysContact(4), sysName(5), sysLocation(6), sysService(7)

  ㅇ **Interface (2) :** 망과의 인터페이스 및 각 인터페이스에서의 트래픽 통계   

     - ifNumber(1), ifTable(2)
  ㅇ **AT (3) :** 주소 변환(Address Translation)   

     - atTable(1)

  ㅇ **IP (4) :** IP Packet들의 통계

     - ipFowarding(1), ipDefaultTTL(2), ipInReceives(3), ...

  ㅇ **ICMP (5) :** 수신된 ICMP 메세지들에 대한 통계

     - icmpInMsgs(1), icmpInErrors(2), ...

  ㅇ **TCP (6) :** TCP 매개변수, 통계 등

     - tcpRtoAlgorithm(1), tcpRtoMin(2), ...

  ㅇ **UDP (7) :** UDP 트래픽 통계

     - udpInDatagrams(1), udpNoPorts(2), ...

  ㅇ **EGP (8) :** EGP 트래픽 통계

     - egpInMsgs(1), egpInErrors(2), ...

  ㅇ **transmission (10) :** 매체에 특화된 MIB와 관련되어 Reserved

  ㅇ **SNMP (11) :** SNMP 관련 트래픽 통계
