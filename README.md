# 나의 포트폴리오
> ### 1. Yacht_dice 게임 만들기 (html,js,css)
> - __[『코드 보기』](https://github.com/kali1402/yacht_dice) [『플레이 해보기』](http://yacht.kro.kr/)__
> ### 2. 디스코드 프로그램에서 봇 만들기 (Python)
> - __[『코드 보기』](https://github.com/kali1402/bot)__
> ### 3. 삼일상업고등학교 점심메뉴 폰으로 알림성정 (js)
> - __[『코드 보기』](https://github.com/kali1402/samillunch-webview)__
> ### 4. 일자리 리스트 보여주는 앱 (js)
> - __[『코드 보기』](https://github.com/kali1402/Job_app)__
> ### 5. 3가지 종류의 뉴스 리스트 앱 (js)
> - __[『코드 보기』](https://github.com/kali1402/news_app)__
> ### 6. 계산기 (html,js,css)
> - __[『코드 보기』](https://github.com/kali1402/kali/blob/master/%EC%9E%90%EB%B0%94%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8%20%EC%97%B0%EC%8A%B5.html) [『플레이 해보기』](http://xn--989a00a691b.p-e.kr/)__
> ### 7. 신과함께 영화에서 감독,주연들 출력 (html,js,css)
> - __[『코드 보기』](https://github.com/kali1402/kali/blob/master/god.html)__
> ### 8. 검 강화하기 (html,js,css)
> - __깃허브 주소 X 미완성 추후 정리예정 [『플레이 해보기』](http://swordupgrade.kro.kr/)__

# IT배움터
> 1. 

# 프로그래밍 상식
> ## 1. 안드로이드 란?
>> __`안드로이드는 구글에서 만든 스마트폰용 운영체제입니다. 운영체제와 미들웨어, 사용자 인터페이스, 어플리케이션, MMS 서비스 등을 하나로 묶어 서비스를 제공하며 다양한 어플리케이션을 만들어 설치하면 실행될 수 있도록 구성된 어플리케이션 플랫폼이라고도 볼 수 있습니다. 많은 사람들이 iOS(애플 운영체제)에 견주어 스마트폰과 태블릿으로 안드로이드 운영체제를 사용하면서, 안드로이드는 세계 모바일 시장에서 가장 성공한 OS라는 평가를 받고있습니다. 안드로이드는 리눅스(Linux)를 기반으로 제작되었고 언어는 자바를 사용합니다.`__<br>
![](https://search.pstatic.net/common/?src=http%3A%2F%2Fblogfiles.naver.net%2F20130504_35%2Fg_m8494_1367629956733Wq5yx_JPEG%2F%25BE%25C8%25B5%25E5%25B7%25CE%25C0%25CC%25B5%25E5.jpg&type=sc960_832)[『사진 출처』](https://blog.naver.com/g_m8494/150167283271)
> ## 2. 안드로이드 명
>> [『사진 출처』](https://zetawiki.com/wiki/%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C_%EB%B2%84%EC%A0%84_%EB%AA%A9%EB%A1%9D) <br>
![](https://github.com/kali1402/-/blob/main/%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C%20%EB%AA%85.PNG?raw=true)<br><br>
> ## 3. HTTP
>> ![](https://search.pstatic.net/common/?src=http%3A%2F%2Fblogfiles.naver.net%2F20150120_18%2Fidea_mind_1421744811721wftA6_PNG%2F012015_0906_HTTP1.png&type=sc960_832)[『사진 출처』](https://blog.naver.com/idea_mind/220246518782)
>> ### Connectionless :
>>> __`서버에 요청을 하고 클라이언트가 응답을 받으면 연결을 끊음
응답을 받으면 연결이 끊어지기 때문에 접속 유지는 최소한으로 할 수 있다. 유저가 많은 웹서비스에서 많은 요청 처리를 가능하게 함
자원 하나에 하나의 연결을 만든다. 즉 서버에 요청하고 싶은 파일 20개가 있으면 20개의 요청을 보내야 한다는 뜻. 하지만 20개의 동일한 요청에 헤더파일이 중복해서 들어가 비효율적이다.(TCP는 연결을 위해서 3번의 패킷교환이 필요하며, 완전한 종료를 위해서 4번의 패킷교환이 이루어져야 한다.) 여기에는 상당히 많은 비용이 들어간다.`__
>> ### Stateless :
>>> __`응답을 받으면 연결을 끊어 버리기 때문에 클라이언트를 식별하지 못한다.
즉 통신이 끝나면 클라이언트의 상태를 유지하지 않는 특징
응답을 받으면 연결을 끊기 때문에 클라이언트를 기억하지 못한다. 한번 인증이 된 클라이언트라도 페이지에 리로딩(서버에 요청)을 보내면 새로운 인증을 수행해야한다. 각 요청은 서로 독립적이고 의존적이지 않으므로 각 각의 요청을 서버가 처리할 수 있게 이전 정보를 모두 제공해야한다.
하지만 웹 어플리케이션 상에서 서버가 클라이언트의 정보를 기억해야할 때가 있다.(현재 로그인을 했는지 안했는지, 내 장바구니 목록등)
이때 클라이언트 사이드에 쿠키를 저장해 서버가 클라이언트를 식별할 수 있도록한다. 하지만 쿠키는 클라이언트 사이드에 저장되는 만큼 보안에 취약하다.
반면 클라이언트의 정보를 서버사이드에서 저장하는 기술을 세션이라고 한다. 하지만 이도 동접수가 많은 웹사이트의 경우 서버 과부하가 되고 중간에서 세션정보가 해킹당할 수 있기 때문에 보안 문제가 있다.
보안성과 메모리 과부화 문제를 보완하기 위해 나온게 토큰이란 개념이다. 핵심은 보호 할 데이터를 토큰으로 치환해 원본 데이터 대신 토큰을 사용한다는 것이다. 중간에 토큰을 탈취해도 데이터에 대한 정보를 알 수 없다.
세션은 식별자가 http session에 한정 돼 토큰보다 제한된 범위로 활용 가능하지만 토큰은 고유 식별자를 토큰으로 만들어 클라이언트에게 전달되기 때문에 다양한 포맷(json,xml)구분 없이 폭 넓게 사용될 수 있다.`__<br>
>> ### Status Code :
>>> __`클라이언트가 서버에 요청을 하면 서버는 응답 코드를 숫자로 반환하는 특징`__<br>
>>> __`100–109 : 메세지 정도`__<br>
>>> __`200–206 : 요청 성공`__<br>
>>> __`300–305 : 리다이렉션`__<br>
>>> __`400–415 : 클라이언트에러`__<br>
>>> __`500–505 : 서버에러 (개발자 탓)`__<br>
>> ### Method : 
>>> __`클라이언트가 서버에 요청을 할 때 보내는 요청의 종류`__<br>
>>> __`GET : 서버에 리소스 요청`__ <br>
>>> __`POST : 서버에 입력데이터를 전송요청`__ <br>
>>> __`PUT : 서버에 정보업데이트 요청`__ <br>
>>> __`DELETE : 서버에 요청 url 리소스 삭제하도록 요청. 하지만 서버는 이를 무시할 수도 있다.`__ <br>
>>> __`HEAD : GET요청과 비슷하다. HTTP 헤더정보만 요청. 클라이언트는 해당 자원과 관련 없이 헤더만을 통해 정보를 가져올 수 있다.`__ <br>
>>> __`TRACE : 클라이언트와 목적지 서버 사이에 있는 HTTP Application의 요청/응답을 연속적으로 계속 따라가 자신이 보낸 메세지의 이상유무 파악하기 위한 요청. 서버는 응답 메세지 본문에 자신이 받은 요청 메세지를 넣어 응답. 진단 위해 사용`__ <br>
>>> __`OPTION : 서버에 특정 리소스가 어떤 메소드를 지원하는지 물어보는 요청`__
> ## 4. 객체지향언어(Object-Oriented Programming, OOP)란?
>> ![](https://image.shutterstock.com/image-vector/oop-arrows-concept-vector-illustration-260nw-409775206.jpg)[『사진 출처』](https://www.shutterstock.com/ko/search/object+oriented+programming)<br>
>> __`객체지향프로그래밍이라는 것은 컴퓨터 프로그래밍의 패러다임 중 하나입니다. 컴퓨터 프로그램을 명령어의 목록으로 보는 시각에서 벗어나 여러 개의 독립된 단위, 즉, "객체" 들의 모임으로 파악하고자 하는 것입니닫. 각각의 개체는 메시지를 주고 받고(Message Passing) 데이터를 처리할 수 있습니다.`__
> ## 5. DDL, DML, DCL, TCL
>> [『사진 출처』](https://brownbears.tistory.com/180)
>> ![](https://github.com/kali1402/-/blob/main/sql.PNG?raw=true)
> ## 6. 네트워크 명령어
>> ### 1. Tracert
>>> __지정된 호스트에 도달할 때까지 통과하는 경로의 정보와 지연시간을 추적__
>>> __Tracert -d host (d 옵션은 DNS reverse look-up을 시도하지 말라는 것)__
>> ### 2. Ping
>>> __호스트 사이에서 물리적인 연결을 수립하기 위해서 상태를 확인할 수 있는 명렁어__
>>> __ping [옵션] IP 주소__
>>> __옵션설명
>>> - -t : ctrl + C를 누를 때까지 특정 호스트로 ping 한다.
>>> - -a : IP주소를 호스트 이름으로 풀이한다.
>>> - -n count : 전달할 에코 요청 수(밀리초 단위)
>>> - -l size  : 버퍼크기를 지정한다.
>>> - -f : 패킷에 don't Fragment 플래그를 설정한다.
>>> - -i TTL : TTL(Time To Live)을 나타낸다.
>>> - -v TOS : Type of Service를 나타낸다.
>>> - -r count : 라우트를 레코드해서 홉을 카운트한다.
>>> - -s count : 홉 카운트데 대한 타임 스태프
>>> - -j host-list : 호스트 리스트를 갖고 있는 loose 라우트
>>> - -k host-list : 호스트 리스트를 갖고 있는 strict 라우트
>>> - -w timeout : 최대 응담 대기 시간(밀리초 단위)__
 
3) ARP(Address Resolrution Protocol)
- IP 주소 대 하드웨어 주소 맵을 보여준다.
  ARP -s IP주소 : ARP 맵에 해당 IP주소의 하드웨어 주소를 추가한다.

 

4) Netstat
- 현재 프로토콜의 상태와 연결을 나타낸다.
  netstat -ant 1 | findstr 192.168.1.10 : 192.168.1.10 과 매칭되는 목록을 1초마다 갱신해서 띄워준다.

 

5) Nbtstat
- IP 어드레스로 해석된 NetBIOS 컴퓨터 이름들의 목록을 보여 준다.

 

6) Ipconfig/Ifconfig
 ㄱ. ipconfig : 설치된 네트워크 카드에 대한 현재 구성을 나타낸다.
  ipconfig /All : 자세한 정보를 나타낸다.
  ipconfig /Batch[file] : ipconfig 요청에서 파일로 정보를 저장한다.
  ipconfig /renew-all : 모든 어댑터에 대한 DHCP 리스를 갱신한다.
  ipconfig /release-all : 모든 어댑터에 대한 DHCP 리스를 해제한다.
  ipconfig /renew N : 어댑터 N용의 IP 주소에 대한 리스를 갱신한다.
  ipconfig /release N : 어댑터 N용의 IP 주소에 대한 리스를 해제한다.
 ㄴ. ifconfig(Linux, Unix) : Network Interface 확인, 인터페이스 업다운, 설정환경 조절, 환경확인
  ifconfig eth0 down : 이더넷0 다운
  ifconfig eth0 up : 이더넷0 업
  ifconfig eth0:1 IP주소 : IP주소로 eth0:1이 활성화된다.(두대의 NIC를 설치한효과)
  ifconfig eth0:1 netmask 255.255.255.0 : 해당 인터페이스의 서브넷 마스크 변경

 

7) Nslookup
- 인터넷 서버 관리자나 또는 사용자가 호스트 이름을 입력하면, 그에 상응하는 인터넷 주소를 찾아주는 프로그램
   nslookup [-opt ...]             : 기본 서버를 사용하는 대화형 모드
   nslookup [-opt ...] - server    : 'server'를 사용하는 대화형 모드
   nslookup [-opt ...] host        : 기본 서버를 사용하는 'host'만 조회
   nslookup [-opt ...] host server : 'server'를 사용하는 'host'만 조회

 


8) route (라우팅 설정/확인하는 명령)
-명령어 구성 : route [-f] [-p] [-4|-6] command [destination] [MASK netmask] [gateway] [METRIC metric] [IF interface]
  -f           모든 게이트웨이 항목의 라우팅 테이블을 지웁니다. 명령 중
               하나와 함께 이 옵션을 사용하면 명령 실행 전에
               테이블이 지워집니다.
  -p           ADD 명령과 함께 이 옵션을 사용하면 시스템을 다시 부팅해도
               경로가 보존됩니다. 시스템을 다시 시작할 때 기본적으로 경로가
               보존되지 않습니다. 해당 영구 경로에 항상 영향을 주는
               다른 모든 명령에 대해서는 무시됩니다.
  -4           IPv4를 사용합니다.
  -6           IPv6을 사용합니다.
  command      수행할 명령
                 PRINT     경로를 출력합니다.
                 ADD       경로를 추가합니다.
                 DELETE    경로를 삭제합니다.
                 CHANGE    기존 경로를 수정합니다.
  destination  호스트를 지정합니다.
  MASK         다음 매개 변수가 'netmask' 값임을 지정합니다.
  netmask      이 경로 항목에 대한 서브넷 마스크 값을 지정합니다. 지정하지 않으면 기본값 255.255.255.255가 사용됩니다.
  gateway      게이트웨이를 지정합니다.
  interface    지정한 경로에 대한 인터페이스 번호입니다.
  METRIC       대상의 비용과 같은 메트릭을 지정합니다.



[『글 출처』](https://dinding.tistory.com/24)
> ## 7.
> ## 8.
