

> ## 6. 네트워크 명령어 - 윈도우
>> ### 1. Tracert
>>> __지정된 호스트에 도달할 때까지 통과하는 경로의 정보와 지연시간을 추적__
>>> __Tracert -d host (d 옵션은 DNS reverse look-up을 시도하지 말라는 것)__
>> ### 2. Ping
>>> __호스트 사이에서 물리적인 연결을 수립하기 위해서 상태를 확인할 수 있는 명렁어__
>>> __ping [옵션] IP 주소__
>>> __옵션설명__
>>> - __-t : ctrl + C를 누를 때까지 특정 호스트로 ping 한다.__
>>> - __-a : IP주소를 호스트 이름으로 풀이한다.__
>>> - __-n count : 전달할 에코 요청 수(밀리초 단위)__
>>> - __-l size  : 버퍼크기를 지정한다.__
>>> - __-f : 패킷에 don't Fragment 플래그를 설정한다.__
>>> - __-i TTL : TTL(Time To Live)을 나타낸다.__
>>> - __-v TOS : Type of Service를 나타낸다.__
>>> - __-r count : 라우트를 레코드해서 홉을 카운트한다.__
>>> - __-s count : 홉 카운트데 대한 타임 스태프__
>>> - __-j host-list : 호스트 리스트를 갖고 있는 loose 라우트__
>>> - __-k host-list : 호스트 리스트를 갖고 있는 strict 라우트__
>>> - __-w timeout : 최대 응담 대기 시간(밀리초 단위)__
>> ### 3. ARP(Address Resolrution Protocol)
>>> __IP 주소 대 하드웨어 주소 맵을 보여준다.__
>>> __ARP -s IP주소 : ARP 맵에 해당 IP주소의 하드웨어 주소를 추가한다.__
>> ### 4. Netstat
>>> __현재 프로토콜의 상태와 연결을 나타낸다.__
>>> __netstat -ant 1 | findstr 192.168.1.10 : 192.168.1.10 과 매칭되는 목록을 1초마다 갱신해서 띄워준다.__
>> ### 5. Nbtstat
>>> __IP 어드레스로 해석된 NetBIOS 컴퓨터 이름들의 목록을 보여 준다.__
>> ### 6. Ipconfig/Ifconfig
>>> - __ipconfig : 설치된 네트워크 카드에 대한 현재 구성을 나타낸다.__<br>
>>> - __ipconfig /All : 자세한 정보를 나타낸다.__<br>
>>> - __ipconfig /Batch[file] : ipconfig 요청에서 파일로 정보를 저장한다.__<br>
>>> - __ipconfig /renew-all : 모든 어댑터에 대한 DHCP 리스를 갱신한다.__<br>
>>> - __ipconfig /release-all : 모든 어댑터에 대한 DHCP 리스를 해제한다.__<br>
>>> - __ipconfig /renew N : 어댑터 N용의 IP 주소에 대한 리스를 갱신한다.__<br>
>>> - __ipconfig /release N : 어댑터 N용의 IP 주소에 대한 리스를 해제한다.__<br>
>>> - __ifconfig(Linux, Unix) : Network Interface 확인, 인터페이스 업다운, 설정환경 조절, 환경확인__<br>
>>> - __ifconfig eth0 down : 이더넷0 다운__<br>
>>> - __ifconfig eth0 up : 이더넷0 업__<br>
>>> - __ifconfig eth0:1 IP주소 : IP주소로 eth0:1이 활성화된다.(두대의 NIC를 설치한효과)__<br>
>>> - __ifconfig eth0:1 netmask 255.255.255.0 : 해당 인터페이스의 서브넷 마스크 변경__<br>
>> ### 7. Nslookup
>>> __인터넷 서버 관리자나 또는 사용자가 호스트 이름을 입력하면, 그에 상응하는 인터넷 주소를 찾아주는 프로그램__<br>
>>> - __nslookup [-opt ...]             : 기본 서버를 사용하는 대화형 모드__<br>
>>> - __nslookup [-opt ...] - server    : 'server'를 사용하는 대화형 모드__<br>
>>> - __nslookup [-opt ...] host        : 기본 서버를 사용하는 'host'만 조회__<br>
>>> - __nslookup [-opt ...] host server : 'server'를 사용하는 'host'만 조회__<br>
>> ### 8. route (라우팅 설정/확인하는 명령)
>>> __명령어 구성 : route [-f] [-p] [-4|-6] command [destination] [MASK netmask] [gateway] [METRIC metric] [IF interface]__<br>
>>> - __-f__<br>
>>> __모든 게이트웨이 항목의 라우팅 테이블을 지웁니다. 명령 중__<br>
>>> __하나와 함께 이 옵션을 사용하면 명령 실행 전에__<br>
>>> __테이블이 지워집니다.__<br><br>
>>> - __-p__<br>
>>> __ADD 명령과 함께 이 옵션을 사용하면 시스템을 다시 부팅해도__<br>
>>> __경로가 보존됩니다. 시스템을 다시 시작할 때 기본적으로 경로가__<br>
>>> __보존되지 않습니다. 해당 영구 경로에 항상 영향을 주는__<br>
>>> __다른 모든 명령에 대해서는 무시됩니다.__<br><br>
>>> - __-4__<br>
>>> __IPv4를 사용합니다.__<br><br>
>>> - __-6__<br>
>>> __IPv6을 사용합니다.__<br>
>>> __command      수행할 명령__<br>
>>> __PRINT     경로를 출력합니다.__<br>
>>> __ADD       경로를 추가합니다.__<br>
>>> __DELETE    경로를 삭제합니다.__<br>
>>> __CHANGE    기존 경로를 수정합니다.__<br>
>>> __destination  호스트를 지정합니다.__<br>
>>> __MASK         다음 매개 변수가 'netmask' 값임을 지정합니다.__<br>
>>> __netmask      이 경로 항목에 대한 서브넷 마스크 값을 지정합니다. 지정하지 않으면 기본값 255.255.255.255가 사용됩니다.__<br>
>>> __gateway      게이트웨이를 지정합니다.__<br>
>>> __interface    지정한 경로에 대한 인터페이스 번호입니다.__<br>
>>> __METRIC       대상의 비용과 같은 메트릭을 지정합니다.__<br>
>>> [『글 출처』](https://dinding.tistory.com/24)<br>
>> 리눅스 명령어[『사진 출처』](https://www.stevenjlee.net/2020/05/23/%EB%94%B0%EB%9D%BC%ED%95%98%EA%B8%B0-%EA%B8%B0%EB%B3%B8-%EB%A6%AC%EB%88%85%EC%8A%A4linux-%EB%AA%85%EB%A0%B9%EC%96%B4-%EC%9A%94%EC%95%BD-%EB%AA%A8%EC%9D%8C/)<br>
>> ![](https://www.stevenjlee.net/wp-content/uploads/2020/05/isnefnt32wn21-740x889.jpg)
> ## 7.
> ## 8.
