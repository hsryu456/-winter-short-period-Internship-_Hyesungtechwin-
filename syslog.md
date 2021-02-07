# 💬 Syslog

* 로깅 메세지 프로그램의 표준.

* Syslog는 다양한 프로그램들이 생성하는 메세지들을 저장하고, 메세지들을 이용해서 다양한 분석 등이 가능하도록 로그 메세지들을 제공한다. 

      프로그램 뿐만 아니라 device와 같은 장비들도 Syslog를 사용할 수 있도록 제공.
      관리자는 device 장비에서의 로그 메세지들을 통해 문제사항이나, 성능 등을 확인할 수 있다.

* 컴퓨터 시스템의 관리, 보안 알림 뿐만 아니라 일반적인 정보, 분석, 디버깅 메세지 등을 제공해준다. 프린터나 라우터와 같은 다양한 장비 뿐만 아니라 다양한 플랫폼을 지원한다.

      이런 이유로 syslog는 중앙 저장소에 다양한 타입의 시스템들의 로그 데이터의 저장소로 사용됨.

* Syslog에서는 메세지를 생성해내는 주체(facility)에 따라 다음과 같이 나눈다.

      auth, authpriv, daemon, cron, ftp, lpr, kern, mail, news, syslog, user, uucp, local0.. local7

<img src="https://user-images.githubusercontent.com/62328584/106685338-8c553580-660b-11eb-8655-b1d05869e95e.JPG" width="600px" height="450px"></img><br/>
      
* 메세지의 우선순위 / 메세지 중요도(level)에 따라 다음과 같이 나뉘어 진다.

      Emergency, Alert, Critical, Error, Warning, Notice, Info or Debug

      Emergency = 응급상황, 시스템 전면중단 -우선순위1
      Alert = 즉각적인 조치가 필요  -우선순위2
      Critical = 하드웨어 등의 심각한 오류발생  -우선순위3
      Error = 일반적인 에러/ 오류   -우선순위4
      Warning = 경고 메세지 -우선순위5
      Notice = 에러나 오류는 아니나, 관리자의 조치가 필요   -우선순위6
      Info = 의미 있는 정보 관련 메시지 -우선순위7
      Debug = 디버깅용 메시지   -우선순위8
      * = 모든 상황의 메세지    -우선순위9

      ▶각 우선순위들은 포함관계를 나타낸다.
      ex)
      -9단계인 *는 모든 메시지를 의미함.(1부터 9까지의 모든 상황을 포함.)   
      -8단계인 debug는 1부터 8까지의 상황을 모두 포함한다. 

- - -
### **< syslog 실습  >**

* Visual Syslog Server 이용하여 연결한 장비의 로그를 가져온다.

<img src="https://user-images.githubusercontent.com/62328584/107006398-6a5adf00-67d4-11eb-8266-1e2d2f4c8c42.jpg" width="750px" height="500px"></img><br/>

       광다중화장치에 광모듈(SFP) 하나를 삽입해놓은 상태


<img src="https://user-images.githubusercontent.com/62328584/107006616-bdcd2d00-67d4-11eb-9aa0-39417c97c094.png" width="750px" height="500px"></img><br/>

       장비에 아무런 변화가 없는 상황에서 Log 확인

<img src="https://user-images.githubusercontent.com/62328584/107006747-f4a34300-67d4-11eb-8a7e-a86948f770da.png" width="750px" height="300px"></img><br/>

      -장비와 연결된 컴퓨터(192.168.0.197)를 로그 서버로 등록   
      -Syslog Level은 Info로 설정. 우선순위7의 메세지로 장비에 의미있는 변화를 감지하여 그 정보를 띄운다.

<img src="https://user-images.githubusercontent.com/62328584/107007062-5c598e00-67d5-11eb-8e2d-85c81274a880.png" width="750px" height="300px"></img><br/>

      Visual Syslog Server 프로그램의 설정에서 UDP, TCP 포트 설정

<img src="https://user-images.githubusercontent.com/62328584/107007230-9460d100-67d5-11eb-8621-eb535b1bf994.png" width="750px" height="300px"></img><br/>

<img src="https://user-images.githubusercontent.com/62328584/107007298-ac385500-67d5-11eb-8c63-76dbd19b356d.png" width="750px" height="150px"></img><br/>

      TCP, UDP의 514번 포트가 무사히 활성됐음을 알 수 있다.

<img src="https://user-images.githubusercontent.com/62328584/107007421-dd188a00-67d5-11eb-9112-169919eb6b0e.png" width="750px" height="350px"></img><br/>

      광모듈을 제거했을 때 발생한 로그 메세지

<img src="https://user-images.githubusercontent.com/62328584/107007542-033e2a00-67d6-11eb-9a7a-be4095d0d4c3.png" width="850px" height="800px"></img><br/>

      Visual Syslog Server 프로그램에서 확인한 로그

<img src="https://user-images.githubusercontent.com/62328584/107007918-7fd10880-67d6-11eb-8af7-a3c0a16a28c4.png" width="850px" height="800px"></img><br/>

      광모듈을 삽입했을 때 발생하는 로그

<img src="https://user-images.githubusercontent.com/62328584/107008070-adb64d00-67d6-11eb-86dc-2ac0f36d6260.png" width="750px" height="500px"></img><br/>

      Visual Syslog Server 프로그램에서 확인한 로그

<img src="https://user-images.githubusercontent.com/62328584/107008176-d2122980-67d6-11eb-8641-42544e5312a3.png" width="750px" height="500px"></img><br/>

      -Visual Syslog Server 프로그램의 Rotation기능.   
      -지정한 위치에 미리 설정해놓은 크기(사진 상으로 1MB)의 로그파일이 저장된다.
      -설정한 크기보다 커지면 다음 rotation 파일을 생성하여 이후 발생하는 로그 메세지를 저장한다.

