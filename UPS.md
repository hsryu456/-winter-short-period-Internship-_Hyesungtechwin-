# ⛓ UPS(_Uninterruptible Power Supply_)
* **무정전 전원 공급장치**라고도 불리며, 상용 전원에서 일어날 수 있는 전원 장애를 극복하여 좋은 품질의 안정된 교류 전력을 공급하는 장치이다. UPS에는 크게 오프라인과 온라인(line-interactive)의 두 가지 종류가 있다.

* 요즘은 절체 응답속도가 빠르고, 순간정전 상황에 강한 온라인 방식 채용

▶ 오프라인: 전원 장애가 있을 때 유휴 상태에 진입시킨 다음, 거의 즉시 효용 전력에서 자체 전력으로 전환한다.

▶ 온라인: 효용 전력 실패에 대한 문제와 모든 전력 문제를 보호한다.

        설계방식에 따라 여러 유형으로 나뉠 수 있고, 고유한 특징을 가진다.
        ex) 스탠바이 (Standby), 라인 인터액티브 (Line Interactive), 스탠바이 온라인 혼합형 (Standby on-line hybrid), 스탠바이-페로 (Standby-Ferro), 이중변환 온라인 (Double Conversion On-Line), 델타 변환 온라인 (Delta Conversion On-Line)

- - -
### **< UPS 시스템의 구성요소 >**
<img src="https://user-images.githubusercontent.com/62328584/105002397-93f5d580-5a74-11eb-934b-8bda8eaf7c20.JPG" width="500px" height="300px"></img><br/>

**-정류기(Rectifier) / 인버터(Inverter)**

* 정류기는 AC 전원을 DC로 변환하여 축전지 및 인버터에 전력을 공급하는 역할.   
* 반면, 인버터는 변환된 DC 전원을 다시 안정된 AC로 변환하여 부하에 공급.
* AC → DC → AC 변환하면 상용전원에 비하여 정전압, 정주파수의 질 좋은 전원이 된다고 한다.

**-축전지(Battery)**

* 평상시에 정류기에서 받은 DC 전력을 모아뒀다가 정전 시 혹은 정류기의 고장 시 부하에 전력을 공급하는 역할.

**-동기절체 스위치(Static Transfer Switch)**

* 부하에 공급하는 전원을 끊김 없이 절체해주는 역할.
* UPS시스템 내부 고장 시 상용전원으로 Bypass하고, 고장 복구 후에는 다시 UPS선로 측으로 선로를 변경하는 역할. (OFF-LINE방식에서는 반대)

**-유지 보수 스위치(Maintenance Bypass Switch)**

* 주로 MBS라는 약자로 많이 불리며, UPS의 인위적인 유지 보수 및 점검이 필요할 때 상용전원에 Bypass하는 기능을 한다.

**-AVR(Automatic Voltage Regulator)**

* 자동전압조정기, 혹은 자동변압기라고도 불린다.
* +/- 15% 이상의 불안정한 전압변동을 +/-2%로 일정하게 출력하며, 주로 방송장비, 의료기기, 연구소, 군부대 등의 정전압이 요구되는 고가 장비에 사용된다.
* 상용전원 사용 시 고품질의 전력을 부하에 입력해 주기 위한 장비.

- - -
### **< UPS 시스템의 동작원리 >**
▶ 온라인 방식

**1. 정상동작**
<img src="https://user-images.githubusercontent.com/62328584/105004424-4cbd1400-5a77-11eb-9246-48139537d1e1.JPG" width="500px" height="300px"></img><br/>
* 정류기에서 DC로 변환된 전력은 축전지에서 자연적으로 방전된 부분을 충전해주고, 인버터 측으로 전력을 공급.

* 인버터에서 변환된 AC 전력은 고조파나 서지, 노이즈 등이 없는 정전압, 정주파수이다.

**2. 정전 혹은 정류기 고장 시 동작**
<img src="https://user-images.githubusercontent.com/62328584/105004670-a1608f00-5a77-11eb-8dab-7f8462ea6187.JPG" width="500px" height="300px"></img><br/>
* 정전이 나거나 정류기 고장 시에는 축전지에 저장되어 있던 전력을 부하에 공급

**3. 고장 시 절체 동작**
<img src="https://user-images.githubusercontent.com/62328584/105004880-e5ec2a80-5a77-11eb-83fe-74ce3640862d.JPG" width="500px" height="300px"></img><br/>
* 축전지에 저장된 전력을 모두 사용했거나, 정류기 혹은 인버터 등에만 고장이 생겼을 경우에는 동기절체스위치가 자동으로 (전력의 끊김 없이) 작동하며, 상용전원을 부하에 공급한다.
* 동기절체스위치 전단에 달린 AVR이 전력의 품질을 높여줌.

**4. 유지 보수 시 동작**
<img src="https://user-images.githubusercontent.com/62328584/105005018-1764f600-5a78-11eb-861c-336b70b8569e.JPG" width="500px" height="300px"></img><br/>
* 정류기, 축전지, 인버터 등의 UPS 시스템 유지 및 보수 시에 동작은 다음과 같다.

        3번의 고장 시 동작 상태에서 유지보수 스위치를 CLOSE하여 부하에 Bypass로 전력을 공급하는 선로를 만들어주고, 출력스위치를 OPEN하여 UPS 선로를 완전하게 분리한다.
        모든 유지 및 보수 작업이 완료되면 1번의 상태로 정상동작합니다.


### **< 교통신호기용 UPS 설치 모습 >**
<img src="https://user-images.githubusercontent.com/62328584/105005681-fbae1f80-5a78-11eb-9c94-5660ddd358f1.JPG" width="500px" height="300px"></img><br/>

