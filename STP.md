# 🔌 STP(_Spanning Tree Protocol_)

* 두 노드 사이에 활성된 경로가 두 개 이상 존재할 경우 브리지 루프가 발생할 수 있다.

      브리지 또는 스위치 장비들의 기본 특성이, 들어오는 프레임 입력 포트를 제외하고 그 프레임을 복사하여 다른 모든 포트로 보내기 때문에 발생

<img src="https://user-images.githubusercontent.com/62328584/106420613-5777a000-649e-11eb-9c86-61716e1d419e.JPG" width="550px" height="450px"></img><br/>

* 브리지 루프는 몇 가지 문제를 야기시킨다.

      1. 브로드캐스팅 폭풍(Broadcasting Storm)

     <img src="https://user-images.githubusercontent.com/62328584/106420827-ce149d80-649e-11eb-95d2-17f981d96d4f.JPG" width="550px" height="450px"></img><br/>

     
     <img src="https://user-images.githubusercontent.com/62328584/106421647-68c1ac00-64a0-11eb-9e90-04460ffc61b0.JPG" width="550px" height="350px"></img><br/>

        ▶R1이 SW1으로 Broadcast 프레임을 보냈다고 가정했을 때, 스위치는 같은 VLAN에 있는 모든 포트로 브로드캐스팅한다. SW1 -> SW2, SW2 -> SW3, SW3 -> SW1 ... 이 결과 Broadcast 프레임의 Looping 현상이 발생.

      2. MAC address 테이블 불안정

        ▶Looping이 발생하게 되면 프레임이 계속 돌기 때문에 확정적인 MAC address 테이블을 정할 수 없다.

      3. 중복 수신

        ▶단일 프레임의 여러 복사본을 수신하게 된다.

* 이러한 Looping을 방지하기 위한 목적으로 사용하는 것이 STP 이다.

      convergence time이 길다는 단점(장애 발생시 대체 경로 발생시 까지 오래 걸린다.)을 해결하기 위해 RSTP가 많이 쓰인다. 
