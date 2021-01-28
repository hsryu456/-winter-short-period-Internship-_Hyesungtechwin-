# 📑 MAC address table
* MAC address와 장비 포트 간의 mapping 관계를 식별하는 테이블

* 정적 MAC address와 동적 MAC address로 구분

      ▶정적 MAC address: 사용자가 설정하며 가장 높은 우선 순위를 갖는다.

      ▶동적 MAC address: 데이터 프레임을 전달하는 동안 장비에 의해 학습되며 제한된 시간 내에 적용된다.

1. 장비가 전달한 데이터 프레임을 수신하면 먼저 데이터 프레임의 소스 MAC address를 확인하고 수신 포트와의 mapping 관계를 설정한다.
2. 대상 MAC address에 따라 MAC address 테이블을 확인한다. 항목에 도달하면 장비는 해당 포트에서 데이터 프레임의 프레임을 만든다.

       그렇지 않은 경우, 장비는 자체 브로드 캐스트 도메인 내에서 데이터 프레임을 브로드 캐스트한다.

* 동적 MAC address가 전달 데이터 프레임에서 장시간 학습되지 않으면 장비는 이를 MAC address table에서 삭제한다.

* MAC address 테이블의 동작은 두 단계로 나뉜다.

       1. MAC address에 대한 액세스
       2. MAC address table 전달 또는 필터링

* 사용자 MAC address 및 포트 mapping에 의해 생성된 정적설정, MAC address 및 포트 mapping에 의해 동적학습을 수행하고 MAC address 테이블을 정기적으로 업데이트한다.
- - -
### **< 동적학습 >**

<img src="https://user-images.githubusercontent.com/62328584/106082464-17db4c00-615e-11eb-8501-d0572baff9f8.jpg" width="600px" height="400px"></img><br/>

       위 그림의 토폴로지 환경은 장비에 연결된 2개의 호스트이다. 호스트1(PC1)은 장비의 1/5포트에, 호스트3(PC3)은 장비의 1/6에 연결

* 초기 상태에서는 MAC address table에 학습된 address 매핑 항목이 없음

<img src="https://user-images.githubusercontent.com/62328584/106107917-e167f600-618a-11eb-8670-c54a2f7262ef.JPG" width="600px" height="200px"></img><br/>

1. 호스트1이 호스트3에 정보를 전송하면 장비는 포트 1/5에서 메시지의 소스 MAC address 00-01-11-11-11-11을 수신한다. 장비의 MAC address 테이블은 MAC address 00-01-11-11-11-11 및 포트 1/5 매핑 항목을 추가.

2. 동시에 장비는 정보를 보낼 대상 MAC address인 00-01-33-33-33-33을 확인한다. 이때 MAC address 00-01-11-11-11-11 및 포트 1/5 매핑 테이블 항목만 00-01-33-33-33-33에 해당하는 포트 매핑이 없으므로 장비의 각 포트에 정보를 브로드캐스트 할 수 있다.(장비의 모든 포트가 기본 VLAN에 속한다고 가정)

3. 포트 1/6에 위치한 호스트3은 호스트1에 응답한다. 이때 장비의 1/6 포트는 호스트3에서 정보를 수신하고 MAC address 테이블 00-01-33-33-33-33 및 포트 1/6에 매핑 테이블이 장비의 MAC address 테이블에 추가된다.

4. 현재 MAC address 테이블의 내용은 MAC address 00-01-11-11-11-11 동적은 포트 1/5에 해당하며 MAC address는 00-01-33-33-33-33 동적은 포트 1에 해당한다. 호스트1과 호스트3 사이의 통신 시간이 지나면 장비는 호스트1과 호스트3에서 보낸 정보를 절대로 받지 않으며 장비의 MAC address 테이블에 저장된 MAC address 매핑 항목을 삭제한다.

<img src="https://user-images.githubusercontent.com/62328584/106108902-43752b00-618c-11eb-802d-e79d861fc73a.jpg" width="600px" height="150px"></img><br/>