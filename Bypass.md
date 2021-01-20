# 🔌 Bypass
* 방화벽, IPS, QOS 등의 시스템에 장애가 발생해도 네트워크
트래픽을 자동으로 우회(Bypass)시켜 중단 없는 서비스가 가능하도록 하는 기능

* 네트워크장비에 장애 상황이 발생 하면 Bypass 기능의 작동으로 기존의 Network Path를 대신하는 path가 생성되어 중단 없이 Networking이 가능하도록 한다.

<img src="https://user-images.githubusercontent.com/62328584/105119765-58124d00-5b14-11eb-8db6-f6889883cf4d.JPG" width="300px" height="400px"></img><br/>
<img src="https://user-images.githubusercontent.com/62328584/105119842-76784880-5b14-11eb-85db-18698168ebd8.JPG" width="300px" height="400px"></img><br/>

- - -
### **< 광스위치를 이용한 Bypass 구현 >**

**Bypass 구성도**

<img src="https://user-images.githubusercontent.com/62328584/105120225-31a0e180-5b15-11eb-829d-75c17b0d6570.jpg" width="500px" height="400px"></img><br/>

**광스위치 연결 모습**

<img src="https://user-images.githubusercontent.com/62328584/105120441-93f9e200-5b15-11eb-8856-21b6648ee02a.jpg" width="550px" height="450px"></img><br/>

        모든 11, 12번 포트에 연결됐다는 불이 들어온 걸 알 수 있다.
        ▶ 가운데 장비(192.168.0.3)전원이 ON인 상태

**ping 테스트**

-제일 위의 장비(192.168.0.2)에서 가장 아래 장비(192.168.0.4)로 ping 전송(192.168.0.3 - **ON**)

<img src="https://user-images.githubusercontent.com/62328584/105120792-3d40d800-5b16-11eb-9a41-3834b32253a6.png" width="500px" height="300px"></img><br/>


<img src="https://user-images.githubusercontent.com/62328584/105121048-c48e4b80-5b16-11eb-948d-acfc145ac06e.jpg" width="550px" height="450px"></img><br/>

        가운데 장비의 11, 12번 포트에 전원이 끊긴 모습.
        ▶ 가운데 장비(192.168.0.3)전원이 OFF인 상태

-제일 위의 장비(192.168.0.2)에서 가장 아래 장비(192.168.0.4)로 ping 전송(192.168.0.3 - **OFF**)

<img src="https://user-images.githubusercontent.com/62328584/105121218-0dde9b00-5b17-11eb-89a1-4c41b7793172.png" width="500px" height="300px"></img><br/>

▶**네트워크를 구성한 세 장비 중 한 장비의 전원이 OFF상태여도 무사히 통신이 됨을 알 수 있다.**



