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

## 1. 리액트 (1) 
## 정의

- 부모 컴포넌트가 자식 컴포넌트에게 주는 값
- 자식 컴포넌트에서는 props 를 받아서 쓸수 있으나 값을 직접 수정할 수는 없다.

## 사용법

### 부모컴포넌트에서..

- html 태그의 attribute 사용하는것과 같이 사용하면 된다.
- 예를 들어 Hello 라는 컴포넌트를 호출하고 있다면 
`<Hello name='rony' />`
와 같이 name 이라는 props 에 rony 라는 값을 담아 넘길수 있다.

```jsx
import React, { useState } from 'react';
import Hellow from './components/Hellow';
import Wrapper from './components/Wrapper';

function App() {
  return (
    <>
      <Wrapper>
        <Hellow name="rony" color="red" />
        <Hellow color="blue" />
      </Wrapper>      
    </>    
  );
}

export default App;
```

### 자식 컴포넌트에서..

- 부모 컴포넌트에서 넘어온 값은 props 라는 변수에 할당되어있기 때문에 props 안의 값을 불러서 사용하면 된다.
- 예를 들어 위의 예제에서 넘겨준 name 에 rony 라는 값을 받아서 쓰려면 [props.name](http://props.name) 으로 값을 받아 쓰면 된다.
- 혹시 해당 props 가 넘어오지 않는경우에 defaultProps 를 설정해주면 값이 넘어오지않는경우 해당 값을 사용하게 된다.

```jsx
import React from 'react';

function Wrapper ({ children }) {
  const style = {
    border: '2px solid black',
    padding: 16
  }
  return (
    <div style={style}>{children}</div>
  );
}

export default Wrapper;
```

```jsx
import React from 'react';

function Hellow ({ color, name }) {
  return (
    <div style={{color: color}}>안녕하세요. {name}</div>
  );
}

Hellow.defaultProps = {
  name: 'noname'
};

export default Hellow;
```

## children

- children 은 컴포넌트 사이에 넘어가는 값이라고 보면된다.
- 예를 들어 아래와 같은 버튼 컴포넌트가 있다고 했을때 해당 컴포넌트 사이에 위치한 `삭제` 라는 값이 props 의children 으로 넘어가게 된다.

```jsx
// 부모 컴포넌트에서..
<Button>삭제</Button>

// 자식 컴포넌트에서..
function Button (props) {
	return (
		<button>{props.children}</button>
	);
}
```

## 2. 리액트 (2) 
## useState 란?

- 동적인 데이터를 다루는 경우 사용한다.
- useState 를 상단에서 불러와 주고 state 에 값을 담고 setState 에 변경할 값을 담아주는 방식으로 처리한다.

## +, - 버튼 클릭으로 숫자를 증감시키는 기능 구현

### Counter.js

```jsx
import React from 'react';

function Counter () {
  return (
    <div>
      <h1>0</h1>
      <button>+1</button>
      <button>-1</button>
    </div>
  );
}

export default Counter;
```

### App.js

```jsx
import React, { useState } from 'react';
import Counter from './components/Counter';

function App() {
  return (
    <>
      <Counter /> 
    </>    
  );
}

export default App;
```

### 차증감 구현

- 버튼 클릭시 숫자값을 변경하기 위해서는 useState 를 불러온 후 해당 state 변수에 값을 담는 처리를 해주어야 한다.
- 여기서는 number 라는 값을 state 값으로 정한다.

```jsx
// useState 선언
import React, { useState } from 'react';

function Counter () {

  // number 값을 선언하고 초기값을 넣어준다.
  const [ number, setNumber ] = useState(0);

  // 버튼 클릭시 number 값을 증가시킬 이벤트 구현
  const plus = () => {
    setNumber(currentNumber => currentNumber + 1);
  }

  // 버튼 클릭시 number 값 감소시킬 이벤트 구현
  const minus = () => {
    setNumber(currentNumber => currentNumber -1);
  }

  // 버튼 태그의 onClick 에 위에서 생성한 이벤트 함수를 넣어준다.
  return (
    <div>
			{/* 출력하는 숫자는 셋팅된 number 변수값을 뿌려준다. */}
      <h1>{number}</h1>
      <button onClick={plus}>+1</button>
      <button onClick={minus}>-1</button>
    </div>
  );
}

export default Counter;
```

## 3. 리액트 (3)
## styled-components 란?

- styled-components 는 css 파일을 별도로 생성하지 않고 javascript 파일 안에서 컴포넌트 형식으로 css 를 적용할 수 있는 방법을 말한다.
- components 이기 때문에 props 를 통한 값 전달이 가능하다.
- css 파일을 별도로 만들지 않기 때문에 클래스 네임 중복 등의 문제에서 벗어날 수 있다.

## 사용법

### 설치

- `yarn add styled-components`
위의 명령을 통해 styled-components 를 설치하여 사용 가능하다.

### example

```jsx
import React from 'react';
import styled, {css} from 'styled-components';

const Circle = styled.div`
  width: 5rem;
  height: 5rem;
  background: ${props => props.color};
  border-radius: 50%;
  ${props => props.huge && css`
    width: 10rem;
    height: 10rem;
  `}
`;

function App() {
  return (
    <>
      <Circle color="black" />
      <Circle color="blue" huge />
    </>    
  );
}

export default App;
```

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/68401e23-0968-412e-bf52-1e1f181dfd4e/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/68401e23-0968-412e-bf52-1e1f181dfd4e/Untitled.png)

### etc

- vscode 의 아래의 확장프로그램을 이용하면 styled-components 의 명령 및 색상을 보다 보기쉽게 관리 할 수 있다.
- `vscode-styled-components`
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
> ## 6. 네트워크 명령어 - 윈도우
>> [『글 출처』](https://dinding.tistory.com/24)
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
>> ### + 리눅스 명령어[『사진 출처』](https://www.stevenjlee.net/2020/05/23/%EB%94%B0%EB%9D%BC%ED%95%98%EA%B8%B0-%EA%B8%B0%EB%B3%B8-%EB%A6%AC%EB%88%85%EC%8A%A4linux-%EB%AA%85%EB%A0%B9%EC%96%B4-%EC%9A%94%EC%95%BD-%EB%AA%A8%EC%9D%8C/)<br>
>> ![](https://www.stevenjlee.net/wp-content/uploads/2020/05/isnefnt32wn21-740x889.jpg)
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
>>
>> ![](https://lh3.googleusercontent.com/proxy/2IklZi7pYuLBo4S5Nkt_DE7ByCZn77jZAy98MMI2EqqSY-V6lY7B6hrJcAbKrivJ02--KAMywvmts--cUOcoXl15Nj1vBYNZoOj5iEXH_tWOOO_xnjHjKoDuoaPwBnAXXFx9P6i8rya7P6GIkfUprhGn19CQk4u72xC3A1o)
>> [『사진 출처』](http://wiki.hash.kr/index.php/OSI_7_%EA%B3%84%EC%B8%B5)
> ## 8. HTML, CSS는 프로그래밍 언어가 아니다.
>> [『글 출처』](https://medium.com/@yjk9313/html%EC%9D%B4-%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D-%EC%96%B8%EC%96%B4%EA%B0%80-%EC%95%84%EB%8B%8C-%EC%9D%B4%EC%9C%A0-e7ccdf2ea24b)
>> ### HTML은 프로그래밍 언어가 아니다. Hyper Text Mark up Language, 한마디로 마크업 언어이다(mark up = 표시하다)
>>> __프로그래밍 언어란, 컴퓨터에서 실행 될 프로그램을 만들기 위해 사람의 문자로 만들어 진 수단이다.__<br>
>>> __-파이썬, 자바스크립트, 자바, C언어 등이 대표적이다. 이들은 사람의 생각을 컴퓨터가 연산 처리 할 수 있도록 그 내용을 문자로 전달하는 수단이다.__<br>
>>> __그러나 HTML은 단독으로 프로그램을 만들 수 없다. HTML은 컴퓨터에게 어떤것이 \<Title>인지, \<Body>,\<Main>인지 구분할 수 있게 하는 언어이다. 말 그대로 Mark up(표시)하는 언어이다. HTMl을 보기 좋게 꾸며주는 CSS또한 마찬가지이다.__<br>
>>> __정리하자면, HTML은 컴퓨터에게 구획을 나누어 인식시켜주는 Mark up 언어이고, CSS는 사람이 보기 좋게 디자인을 변경시켜주는 언어이다.__<br>
>> [『사진 출처』](https://medium.com/@yjk9313/html%EC%9D%B4-%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D-%EC%96%B8%EC%96%B4%EA%B0%80-%EC%95%84%EB%8B%8C-%EC%9D%B4%EC%9C%A0-e7ccdf2ea24b)<br>
>> ![](https://miro.medium.com/max/700/0*rCoIWITij3nvAziF.jpg)
