# 💬 ICMP

* TCP/IP에서 IP 패킷을 처리할 때 발생되는 문제를 알려주는 프로토콜

* 네트워크 컴퓨터 위에서 돌아가는 운영체제에서 오류 메시지(Requested service is not available 등)를 전송받는 데 주로 쓰인다.

* 인터넷 프로토콜의 주요 구성원 중 하나로 인터넷 프로토콜에 의존하여 작업을 수행한다.   
프로토콜 번호 1로 할당되고 시스템 사이에 데이터를 교환하지 않거나 최종 사용자에 적용되지 않는다는 점에서 TCP, UDP와는 다르다.

* 인터넷 프로토콜 버전 4(IPv4) 용 ICMP는 ICMPv4로 알려져 있고, 유사하게 IPv6은 ICMPv6이다.

* IP에는 오로지 패킷을 목적지에 도달시키기 위한 내용들로만 구성되어 있다. 따라서 정상적으로 목적지 호스트에 도달하는 경우에는 IP에서 통신이 성공하고 종료되므로 아무런 문제가 없다.

      전달해야 할 호스트가 꺼져 있거나, 선이 단절된 경우와 같은 비정상적인 경우에 패킷 전달을 의뢰한 출발지 호스트에 이러한 사실을 알려야하지만,   
      IP에는 그러한 에러에 대한 처리 방법이 명시되어있지 않다.  
      => ICMP를 이용하여 개선

* ICMP는 해당 호스트가 없거나, 서버 프로그램이 없는 등의 에러 상황이 발생할 경우 IP헤더에 기록되어 있는 출발지 호스트로 이러한 에러에 대한 상황을 보내주는 역할을 수행하게 된다.

* 통신 유무 확인 시 자주 쓰는 윈도우의 ping 같은 경우도 ICMP 프로토콜을 이용한 방법이다.

* ICMP 사용(활용) 명령어로는 Echo Request (ICMP 질의메세지 요청)와 Echo Reply (ICMP 응답메세지 요청)가 있다.

* IP(Internet Protocol)와 하나의 쌍을 이루며 동작

 - - -
### **< ICMP 계층 위치 >**

<img src="https://user-images.githubusercontent.com/62328584/108009786-c3353d80-7046-11eb-8d6f-a08d80901fef.JPG" width="400px" height="350px"></img><br/>

* ICMP는 IP의 상위계층의 프로토콜 처럼 행동하나, 결국 ICMP는 IP 계층의 일부이며  IP 데이터그램의 데이터 부분에 포함되어 전달한다.   

 
### **< ICMP 패킷 헤더 구조 >**

<img src="https://user-images.githubusercontent.com/62328584/108005027-e528c300-703a-11eb-83a4-0c85e73dde9e.JPG" width="600px" height="250px"></img><br/>

▶ ICMP Type : ICMP 메세지 구별

▶ ICMP Code : 메세지 내용에 대한 추가 정보 (ICMP TYPE에 대한 상세 정보)

▶ ICMP Cehcksum : ICMP의 값이 변조 여부를 확인 

▶ ICMP 메세지1, 메세지2 : ICMP TYPE에 따라 내용이 가변적으로 들어가는 내용


### **< ICMP Error Reporting 메시지 >**

<img src="https://user-images.githubusercontent.com/62328584/108005477-2b325680-703c-11eb-821d-43f6edfcd9a0.JPG" width="600px" height="300px"></img><br/>

1. Destination Unreachable (Type 3)

> 해당 목적지에 도달할 수 없음을 의미

> 목적지 도달 불가 사유에 따라 다양한 Code로 구성되어 있다.


    Code 1(Host Unreachable) : 최종 단계의 라우터가 목적지 호스트로 패킷 전송에 실패한 경우

    Code 2(Protocol Unreachable) : 목적지 호스트에서 특정 프로토콜을 사용할 수 없는 경우

    Code 3(Port Unreachable) : 목적지 호스트에 해당 UDP포트가 열려있지 않는 경우

    (TCP의 경우에 포트가 열려있지 않으면 TCP RST 패킷을 반환한다)

    Code 4(Fragmentation needed and don't fragment was set) : IP 패킷의 단편화가 반드시 필요하지만 IP 헤더의 Don't fragment 플래그가 설정되어 단편화할 수 없는 경우 라우터에 의해 반환된다.



2. Redirection (Type 5)

> 라우팅 경로가 잘못되어 새로운 경로를 이전 경유지 또는 호스트에게 알려주는 메시지

> ICMP Redirect 공격 시 이용하는 메시지



3. Time Exceeded (Type 11)

> 타임아웃이 발생하여 IP패킷이 폐기되었음을 알리는 메시지이며 타임아웃 사유는 Code를 통해 알 수 있다.

   
    Code 0(Time To Live exceeded in Transit) : IP 패킷이 최종 목적지에 도달하기 전에 TTL값이 0이 되어 해당 패킷이 폐기되었음을 알리는 메시지.

    Code 1(Fragment reassembly time exceeded) : IP 패킷 재조합 과정에서 타임아웃이 발생하여 해당 IP 데이터그램이 모두 폐기되었음을 알리는 메시지. 일반적으로 IP 데이터그램의 일부 단편이 전송과정에서 손실될 경우 재조합 과정에서 실패하여 발생한다.
