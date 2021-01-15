# 👨‍💻 SSH(_Secure SHell_)

* 네트워크 상의 다른 컴퓨터에 로그인하거나 원격 시스템에서 명령을 실행하고 다른 시스템으로 파일을 복사할 수 있도록 해 주는 응용 프로그램 또는 그 프로토콜

* 기존의 rsh, rlogin, 텔넷 등을 대체하기 위해 설계되었으며, 강력한 인증 방법 및 안전하지 못한 네트워크에서 안전하게 통신을 할 수 있는 기능을 제공한다.

* 기본적으로는 22번 포트를 사용한다.

* SSH는 암호화 기법을 사용하기 때문에 통신이 노출된다고 하더라도 이해할 수 없는 암호화된 문자로 보인다.

<img src="https://user-images.githubusercontent.com/62328584/104535830-3cadca80-565a-11eb-9454-e1842efa55b6.JPG" width="700px" height="250px"></img><br/>

- - -
### **< TELNET과 SSH >**

* TELNET을 사용할 경우, 일반 문자열이 출력되었을 때 별도의 암호화가 되지 않음
<img src="https://user-images.githubusercontent.com/62328584/104536705-dcb82380-565b-11eb-8d64-83cb60ab3dd8.JPG" width="700px" height="350px"></img><br/>

* 반면, SSH의 경우 일반 문자열이 암호화되어 식별할 수 없는 내용의 패킷으로 전송된다.
<img src="https://user-images.githubusercontent.com/62328584/104536772-0c672b80-565c-11eb-914c-328b3a1b6ae2.JPG" width="700px" height="350px"></img><br/>

### **< Private Key, Public Key >**
* SSH는 다른 컴퓨터와 통신을 하기 위해 접속을 할 때 우리가 일반적으로 사용하는 비밀번호의 입력을 통한 접속을 하지 않음

 * 기본적으로 SSH는 한 쌍의 Key를 통해 접속하려는 컴퓨터와 인증 과정을 거친다.

        ▶ Private Key
        ▶ Public Key

▶ *Public Key*: 단어 뜻 그대로 공개되어도 비교적 안전한 Key. Public Key를 통해 메시지를 전송하기 전 암호화. Public Key로 암호화는 가능하지만 복호화는 불가능. 

▶ *Private Key*: 외부에 노출이 되어서는 안되는 Key로 사용자의 컴퓨터 내부에 저장하게 되어있음. Private Key를 통해 암호화된 메시지를 복호화 할 수 있음.

<img src="https://user-images.githubusercontent.com/62328584/104537334-205f5d00-565d-11eb-935a-bbfd6d63f881.JPG" width="700px" height="200px"></img><br/>
