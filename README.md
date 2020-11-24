
> ## 7. OSI 7계층
>> [『글 출처』](https://reakwon.tistory.com/59)
>> ### 물리계층(Physical Layer)
>>> __7계층 중 최하위 계층입니다. 주로 전기적, 기계적, 기능적인 특성을 이용해 데이터를 전송하게 됩니다. 데이터는 0과 1의 비트열, 즉 On, Off의 전기적 신호 상태로 이루어져있지요.__<br>
>>> __이 계층은 단지 데이터를 전달하기만 합니다. 어떤 에러가 있는지 등 그런 기능에는 전혀 관여하지 않습니다.__<br>
>> ### 데이터링크 계층(Data-Link Layer)
>>> __물리 계층에서 송수신되는 정보의 오류와 흐름을 관리하여 안전한 정보의 전달을 수행할 수 있도록 도와주는 역할을 합니다.__<br>
>>> __데이터 링크 계층의 데이터 전송은 Point-To-Point 간 입니다.__<br>
>>> __안전한 정보의 전달이라는 것은 오류나 재전송하는 기능을 갖고 있다는 이야기죠. 또한 우리가 언젠가 한번 들었을 MAC주소를 갖고 있습니다. 그래서 통신을 할 수 있지요.__<br>
>>> __이 계층에서 부르는 데이터의 단위는 프레임(Frame)이라고 합니다.__<br>
>> ### 네트워크 계층(Network Layer)
>>> __네트워크 계층은 네트워크에서 아주 중요합니다.__<br>
>>> __중요한 기능 중 한가지는 바로 라우팅이라고 하는데요. 목적지까지 가장 안전하고 빠르게 데이터를 보내는 기능을 말합니다. 따라서 최적의 경로를 설정해야하지요.__<br>
>>> __이런 라우팅 기능을 맡고 있는 계층이 네트워크 계층입니다.__<br>
>>> __또한 어느 컴퓨터에게 데이터를 전송할지 주소를 갖고 있어서 통신을 합니다. 우리가 자주 듣는 IP 주소가 바로 네트워크 계층 헤더에 속해있습니다.__<br>
>>> __네트워크 계층에서 부르는 데이터 단위는 패킷(Packet)이라고 합니다.__<br>
>> ### 전송 계층(Transport Layer)
>>> __전송 계층 역시 네트워크에서 중요한 계층입니다. 전송 계층은 양 끝단의 사용자들이 신뢰성있는 데이터를 주고 받게 해주는 역할을 합니다.__<br>
>>> __송신자와 수신자 간의 신뢰성있고 효율적인 데이터를 전송하기 위하여 오류검출 및 복구, 흐름제어와 중복검사 등을 수행합니다.__<br>
>>> __중요한 것은 데이터 전송을 위해서 Port 번호가 사용이 됩니다. 대표적인 프로토콜로는 TCP와 UDP가 있습니다. 이 계층에서 사용하는 데이터 단위는 세그먼트(Segment)라고 합니다.__<br>
>> ### 세션 계층(Session Layer)
>>> __세션 계층은 응용 프로세스가 통신을 관리하기 위한 방법을 정의합니다.__<br>
>>> __이 계층은 세션을 만들고 없애는 역할을 하고 있지요.__<br>
>> ### 표현 계층(Presentation Layer)
>>> __데이터를 어떻게 표현할 지 정하는 역할을 하는 계층으로 일종의 확장자라고 이야기하면 편하겠네요.__<br>
>>> __표현 계층은 세가지의 기능을 갖고 있습니다.__<br>
>>> __1. 송신자에서 온 데이터를 해석하기 위한 응용계층 데이터 부호화, 변화__<br>
>>> __2. 수신자에서 데이터의 압축을 풀수 있는 방식으로 된 데이터 압축__<br>
>>> __3. 데이터의 암호화와 복호화__<br>
>>> __MIME 인코딩이나 암호화 등의 동작이 표현계층에서 이루어집니다. EBCDIC로 인코딩된 파일을 ASCII 로 인코딩된 파일로 바꿔주는 것이 한가지 예이지요.__<br>
>> ### 응용 계층(Application Layer)
>>> __사용자와 가장 가까운 계층이 바로 응용 계층입니다. 우리가 사용하는 응용 서비스나 프로세스가 바로 응용계층에서 동작합니다.__<br>

>> [『사진 출처』](http://wiki.hash.kr/index.php/OSI_7_%EA%B3%84%EC%B8%B5)
>> ![](https://lh3.googleusercontent.com/proxy/2IklZi7pYuLBo4S5Nkt_DE7ByCZn77jZAy98MMI2EqqSY-V6lY7B6hrJcAbKrivJ02--KAMywvmts--cUOcoXl15Nj1vBYNZoOj5iEXH_tWOOO_xnjHjKoDuoaPwBnAXXFx9P6i8rya7P6GIkfUprhGn19CQk4u72xC3A1o)
> ## 8.
