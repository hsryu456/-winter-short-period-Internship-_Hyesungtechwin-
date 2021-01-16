# 🔌 POE(_Power over Ethernet_)
* 이더넷 전원 장치(PoE)는 IEEE 802.3af 및 802.3at 표준에 의해 정의된 네트워킹 기능으로 네트워크 장비에 따로 전원은 연결하지 않고, UTP케이블을 이용해서 데이터와 전력을 전송하는 기술을 의미 한다.

        -PoE를 사용하면 기존 데이터 연결 상에서 이더넷 케이블을 통해 네트워크 장치에 전원을 공급할 수 있음.

* POE장비(인젝터 등)나 POE스위치 등을 이용하여 구현할 수 있다.

* POE를 이용하면 **별도의 전원없이** 네트워크 케이블 하나로 장비를 사용할 수 있기 때문에 배선정리도 좋고 설치도 간편하다.

* PoE 허브를 사용하면 보다 다양한 네트워크 장비를 하나로 묶을 수 있다.

<img src="https://user-images.githubusercontent.com/62328584/104693433-fd13db00-574c-11eb-888c-891d7f08f020.JPG" width="500px" height="300px"></img><br/>

- - -
### **< POE 구성 >**
▶ **전원 소싱 장비(PSE)**: UTP 케이블을 통해 PD에게 전원을 공급 하는 장치. 대부분의 PSE는 네트워크 스위치이거나 PoE가 아닌 스위치와 함께 사용하는 PoE 인젝터이다.

    -하나의 PSE 포트는 802.3af 규격일 때 최대 15.4W의 전력을 공급할 수 있고 802.3at 규격일 때 최대 30W의 전력을 공급할 수 있다.
    -PSE는 Endspan PSE와 Midspan PSE가 있다. 

▶ **전원 장치(PD)**: PSE로부터 전원을 공급 받는 장치. PD의 대표적인 예로는 VoIP 전화, 무선 액세스 포인트 및 IP 카메라 등이 있다.
    
    -PD는 Endspan PSE와 Midspan PSE가 모두 지원 될 수 있도록 설계되어야 한다.

<img src="https://user-images.githubusercontent.com/62328584/104694989-5d0b8100-574f-11eb-8c67-b937c28bf7ee.JPG" width="800px" height="350px"></img><br/>

* 많은 전원 공급 장치에는 선택적인 외부 전원 공급 장치를위한 보조 전원 커넥터가 있다. 설계에 따라 장치 전원의 일부, 없음 또는 전체를 보조 포트에서 공급할 수 있다.

        -보조 포트도 PoE 공급 전원이 실패 할 경우 백업 전원으로 작동하기도함.

        
### **< POE 실습 >**

<img src="https://user-images.githubusercontent.com/62328584/104698080-22581780-5754-11eb-8745-53c4af08c9d7.jpg" width="750px" height="350px"></img><br/>
▶ 광스위치의 6번 포트에 카메라를 연결한 모습

<img src="https://user-images.githubusercontent.com/62328584/104697904-cee5c980-5753-11eb-81b4-5592e193a54a.PNG" width="750px" height="350px"></img><br/>
▶ 2번 포트로 연결된 컴퓨터로 결과 확인.

    광스위치(PSE)와 연결한 카메라(PD)에 전원이 공급되고 있음을 알 수 있다.
