# 👨‍💻 In-Band Management(IBM)

* Telnet 프로그램을 통하여 장비에 로그인하거나 SSH를 통하여 장비 설정 관리가능.

* 장비에서 제공하는 In-Band Management는 장비에 연결된 다른 장비도 장비 관리 기능을 가질 수 있도록 한다.

* 장비 설정이 변경되어 In-Band Management가 실효됐을 경우, Out of Band Management를 통하여 장비를 설정, 관리할 수 있다.

<img src="https://user-images.githubusercontent.com/62328584/105784724-b334bb80-5fbc-11eb-9ec6-bb81f7edba4a.JPG" width="550px" height="450px"></img><br/>

- - -
### **< Telnet 장비 관리 >**

_Telnet 접속을 통한 장비 관리_

1. IP 주소 설정
2. Telnet client의 host IP는 소속된 장비의 VLAN 접속구의 IP와 같은 네트워크에 있음
3. (2항을 만족하지 못할 시) Telnet은 라우터 등 장비를 통하여 장비의 IP에 접근한다.
