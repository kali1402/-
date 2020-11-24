# 목차
- __[『나의 포트폴리오』](https://github.com/kali1402/-#%EB%82%98%EC%9D%98-%ED%8F%AC%ED%8A%B8%ED%8F%B4%EB%A6%AC%EC%98%A4)__<br>
-- __[『나의 포트폴리오』](https://github.com/kali1402/-#%EB%82%98%EC%9D%98-%ED%8F%AC%ED%8A%B8%ED%8F%B4%EB%A6%AC%EC%98%A4)__<br>
-- __[『나의 포트폴리오』](https://github.com/kali1402/-#%EB%82%98%EC%9D%98-%ED%8F%AC%ED%8A%B8%ED%8F%B4%EB%A6%AC%EC%98%A4)__<br>
-- __[『나의 포트폴리오』](https://github.com/kali1402/-#%EB%82%98%EC%9D%98-%ED%8F%AC%ED%8A%B8%ED%8F%B4%EB%A6%AC%EC%98%A4)__<br>
-- __[『나의 포트폴리오』](https://github.com/kali1402/-#%EB%82%98%EC%9D%98-%ED%8F%AC%ED%8A%B8%ED%8F%B4%EB%A6%AC%EC%98%A4)__<br>
-- __[『나의 포트폴리오』](https://github.com/kali1402/-#%EB%82%98%EC%9D%98-%ED%8F%AC%ED%8A%B8%ED%8F%B4%EB%A6%AC%EC%98%A4)__<br>
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
### etc

- vscode 의 아래의 확장프로그램을 이용하면 styled-components 의 명령 및 색상을 보다 보기쉽게 관리 할 수 있다.
- `vscode-styled-components`

## 4. 리액트 (4)
## 개요

- 투두리스트를 만들어보자.

## 프로젝트 생성

- `npx create-react-app todo-list` 명령을 통해서 프로젝트를 생성해 준다.
- styped-components 와 react-icons 를  사용하므로 yarn add 명령을 통해서 해당 라이브러리를 설치해준다.
`yarn add react-icons styled-components`
- react-icons 는 프로젝트에 사용할 아이콘으로 해당 페이지에서 원하는 아이콘을 확인후 사용하면 된다.

    [React Icons](https://react-icons.netlify.com/#/icons/md)

## 필요한 컴포넌트

### Templete

- todolist 만들어줄 화면 구성

### Head

- todolist 상단에 현재 날짜 및 남은 할일 표기

### List

- 할일 목록

### Item

- 할일

### Add

- 할일 추가 버튼 및 텍스트 박스

## 컴포넌트 생성

### 기본 바탕 회색처리

- 특정 컴포넌트에 스타일을 주는게 아니라 전체 컴포넌트에 스타일 적용을 원하는경우 styled-components 의 createGlobalStyle 응 사용한다.

    ```jsx
    import React from 'react';
    import {createGlobalStyle} from 'styled-components';

    const GlobalStyle = createGlobalStyle`
      body {
        background: gray;
      }
    `;

    function App() {
      return (
        <>
          <GlobalStyle />
          <div>바탕화면이 회색 처리 되었나?</div>
        </>
      );
    }

    export default App;
    ```

### Templete 컴포넌트 생성

- 배경이 회색이기 때문에 해당 컴포넌트는 하얀색으로 한다.
- 컴포넌트를 화면 중앙에 위치시키려면 `margin: 0 auto;` 스타일을 적용해야 한다.
- 헤드, 리스트등 컴포넌트 위치를 좌우 정렬이 아닌 상하 정렬로 해야 하는데 그것을 위해서는 
`flex-direction`옵션을 `column` 으로 설정해야 한다.
( 요 옵션을 뺴먹면 컴포넌트 정렬이 위아래가 아닌 좌우로 된다. )
[https://developer.mozilla.org/ko/docs/Web/CSS/flex-direction](https://developer.mozilla.org/ko/docs/Web/CSS/flex-direction)

```jsx
import React from 'react';
import styled from 'styled-components';
import Head from './Head';
import List from './List';

const TemplateBody = styled.div`
  width: 512px;
  height: 768px;
  background: white;
  border-radius: 16px;
  display: flex;
  margin: 0 auto;

  flex-direction: column;
`;

function Template () {
  return (
    <TemplateBody>
      <Head />
      <List />
    </TemplateBody>
  );
}

export default Template;
```

### Head  컴포넌트 생성

- 날짜, 요일, 남아있는 할일수를 표기해줄 컴포넌트를 생성한다.
- 하단의 리스트와 구분이 필요하므로 border-bottom 스타일을 이용하여 구분선을 그어준다.

```jsx
import React from 'react';
import styled from 'styled-components';

const HeadBody = styled.div`
  color: black;
  border-bottom: 1px solid black;
  height: 200px;
  width: 100%;
  text-align: center;
`;

const TodoLeft = styled.div`
  color: red;
  padding-top: 30px;
`;

function Head () {
  return (
    <HeadBody>
      <h1>2020년 6월 17일</h1>
      <h3>수요일</h3>
      <TodoLeft>할일 1개 남음</TodoLeft>
    </HeadBody>
  );
}

export default Head;
```

### List 컴포넌트 생성

- 할일 목록을 보여줄 리스트를 생성한다.
- padding 을 넣어주지 않으면 텍스트가 벽에 붙어 이상하니 styled-components 설정시 padding 을 넣어주도록 하자.

```jsx
import React from 'react';
import styled from 'styled-components';

const ListBody = styled.div`
  width: 100%;
  overflow-y: auto;
  padding-left: 50px;
  padding-top: 50px;
`;

function List () {
  return (
    <ListBody>
      <div>할일 1</div>
      <div>할일 2</div>
      <div>할일 3</div>
    </ListBody>      
  );
}

export default List;
```

### Item 컴포넌트 생성

- 할일을 나타낼 item 컴포넌트를 만들어준다.
- check 화면은 checkbox 를 사용하지않고 div 로 원모양을 만들어 체크되었을때 MdDone 이미지가 원 안에 노출될 수 있도록 구현한다.
- check 되었을떄의 처리를 위해 done poprs 를 사용하고 체크시 텍스트 색상을 변경하도록 한다.
- ItemBody 에서 Remove 를 참조해서 사용하고 있기 때문에 Remove 는 ItemBody 보다 위에 있어야 코드 오류가 발생되지 않는다.

```jsx
import React, { useState } from 'react';
import styled, { css } from 'styled-components';
import { MdDone, MdDelete } from 'react-icons/md';

const Remove = styled.div`
  display: none;
  color: gray;
  font-size: 24px;
  cursor: pointer;
  &:hover {
    color: red;
  }
`;

const ItemBody = styled.div`
  display: flex;
  &:hover {
    ${Remove} {
      display: block;
    }
  }
	padding-top: 10px;
  padding-bottom: 10px;
`;

const CheckCircle = styled.div`
  width: 32px;
  height: 32px;  
  border: 1px solid silver;
  border-radius: 20px;
  cursor: pointer;
  font-size: 25px;
  align-items: center;
  justify-content: center;
  display: flex;
  ${props => props.done && css`
    border-color: black;
  `}
`;

const Text = styled.div`
  padding-left: 15px;
  font-size: 21px;
  color: black;
  width: 70%;
  ${props => props.done && css`
    color: silver;
  `}
`;

function Item () {

  const [ done, setDone ] = useState(false);

  const onToggle = () => {
    setDone(status => !status);
  }

  return (
    <ItemBody>
      <CheckCircle done={done} onClick={onToggle}>
        {done && <MdDone />}
      </CheckCircle>
      <Text done={done}>할일</Text>
      <Remove>
        <MdDelete />
      </Remove>      
    </ItemBody>
  );
}

export default Item;
```

### Add 컴포넌트 생성

- 할일을 추가할때 사용할 Add 컴포넌트를 추가해준다.
- 할일을 입력할 텍스트와 버튼을 구현해주면 된다.

```jsx
import React, {useState} from 'react';
import styled from 'styled-components';

const AddBody = styled.div`
  display: flex;
`;

const InputBox = styled.input`
  width: 180px;
  height: 30px;
  margin-left: 110px;
`;

const Button = styled.button`
  cursor: pointer;
  width: 80px;
  height: 36px;
  display: flex;
  justify-content: center;
  align-items: center;
`;

function Add () {
  return (
    <AddBody>
      <InputBox />
      <Button>할일등록</Button>
    </AddBody>
  );
}

export default Add;
```

## 데이터 작업

### 데이터 셋팅

- App.js 에 출력할 데이터를 넣어준다.
- 해당 데이터는 할일 추가, 삭제등으로 인해 변경사항이 반영되어야 하므로 useState 를 통해 생성해준다.

```jsx
const [todos, setTodos] = useState([
    {
      id: 1,
      checked: true,
      text: '출근하기'
    },
    {
      id: 2,
      checked: false,
      text: '퇴근하기'
    }
  ]);
```

- 할일 체크, 할일 추가, 할일 삭제시 사용될 함수를 선언후 하위 컴포넌트에 넘겨준다.

```jsx
// 할일 체크
const onToggle = (id) => {
    setTodos(todos.map(o => {
      const checked = o.id === id ? !o.checked : o.checked;
      
      return {
        ...o,
        checked
      }
    }));
  }

  // 할일 삭제
  const onRemove = (id) => {
    setTodos(todos.filter(o => o.id !== id));
  }
  
  // 할일 추가
  const onAdd = (text) => {
    const lastID = todos.map(o => o.id).sort((a, b) => {
      return b - a;
    })[0];

    const newTodo = {
      id: lastID + 1,
      checked: false,
      text
    };

    setTodos(todos.concat(newTodo));
  }
```

### 각 컴포넌트 별 props 처리

- Template 컴포넌트에서 넘겨받은 props 는 하위 컴포넌트로 그대로 넘겨준다.

```jsx
import React from 'react';
import styled from 'styled-components';
import Head from './Head';
import List from './List';
import Add from './Add';

const TemplateBody = styled.div`
  width: 512px;
  height: 768px;
  background: white;
  border-radius: 16px;
  display: flex;
  margin: 0 auto;

  flex-direction: column;
`;

function Template ({ todos, onToggle, onRemove, onAdd }) {
  return (
    <TemplateBody>
      <Head />
      <List todos={todos} onToggle={onToggle} onRemove={onRemove} />
      <Add onAdd={onAdd} />
    </TemplateBody>
  );
}

export default Template;
```

- List 컴포넌트에서는 넘겨받은 Todos 를 루프처리하고 역시 Item 컴포넌트에 넘겨받은 props 중 필요한 데이터를 넘겨준다.

```jsx
import React from 'react';
import styled from 'styled-components';
import Item from './Item';

const ListBody = styled.div`
  width: 100%;
  height: 400px;
  overflow-y: auto;
  padding-left: 50px;
  padding-top: 50px;
`;

function List ({ todos, onToggle, onRemove }) {
  return (
    <ListBody>
      {todos.map(o => (
        <Item key={o.id} id={o.id} checked={o.checked} onToggle={onToggle} onRemove={onRemove}>{o.text}</Item>
      ))}
    </ListBody>      
  );
}

export default List;
```

- Item 컴포넌트에서는 넘겨받은 클릭 및 일정제거 이벤트를 반영해준다.

```jsx
import React from 'react';
import styled, { css } from 'styled-components';
import { MdDone, MdDelete } from 'react-icons/md';

const Remove = styled.div`
  display: none;
  color: gray;
  font-size: 24px;
  cursor: pointer;
  &:hover {
    color: red;
  }
`;

const ItemBody = styled.div`
  display: flex;
  &:hover {
    ${Remove} {
      display: block;
    }
  }
  padding-top: 10px;
  padding-bottom: 10px;
`;

const CheckCircle = styled.div`
  width: 32px;
  height: 32px;  
  border: 1px solid silver;
  border-radius: 20px;
  cursor: pointer;
  font-size: 25px;
  align-items: center;
  justify-content: center;
  display: flex;
  ${props => props.done && css`
    border-color: black;
  `}
`;

const Text = styled.div`
  padding-left: 15px;
  font-size: 21px;
  color: black;
  width: 70%;
  ${props => props.done && css`
    color: silver;
  `}
`;

function Item ({ children, checked, onToggle, id, onRemove }) {
  return (
    <ItemBody>
      <CheckCircle done={checked} onClick={() => onToggle(id)}>
        {checked && <MdDone />}
      </CheckCircle>
      <Text done={checked}>{children}</Text>
      <Remove onClick={() => onRemove(id)}>
        <MdDelete />
      </Remove>      
    </ItemBody>
  );
}

export default Item;
```

- Add 컴포넌트에서는 추가되는 할일을 todos 에 추가하는 작업을 추가한다.

```jsx
import React, {useState} from 'react';
import styled from 'styled-components';

const AddBody = styled.div`
  display: flex;
`;

const InputBox = styled.input`
  width: 180px;
  height: 30px;
  margin-left: 110px;
`;

const Button = styled.button`
  cursor: pointer;
  width: 80px;
  height: 36px;
  display: flex;
  justify-content: center;
  align-items: center;
`;

function Add ({ onAdd }) {

  const [text, setText] = useState('');

  const onChange = (e) => {
    setText(e.target.value);
  }

  const addTodo = () => {
    onAdd(text);
  }

  return (
    <AddBody>
      <InputBox onChange={onChange} />
      <Button onClick={addTodo}>할일등록</Button>
    </AddBody>
  );
}

export default Add;
```

## 마치며
- 전체적인 구동이 정상적으로 되는지 확인한다.

## 5. 리액트 (5)
이번 시간에는 React를 통해서 API 연동하는 방법에 대해서 알아보도록 하겠습니다!
중요한 부분은 소스코드 주석을 통해서 최대한 전달하도록 하겠습니다.
이해 안되거나 설명이 부족한 부분은 참고링크를 확인해주세요~!

**[참고링크]**

[](https://react.vlpt.us/integrate-api/)

**[목차]**

## 1. 프로젝트 셋팅

- API 연동 전 프로젝트를 만들어줍니다.
- API 호출을 위해서 axios 모듈을 설치하겠습니다.

```bash
$ npx create-react-app api-integrate

$ yarn add axios

/* 설명 */
**axios 모듈을 통해서 하고 싶은 작업에 따라 아래와 같이 요청**

[REST API 제대로 알고 사용하고 싶으면 이곳을 클릭!](https://meetup.toast.com/posts/92)
****
GET: 데이터 조회
POST: 데이터 등록
PUT: 데이터 수정
DELETE: 데이터 제거
```

## 2. useReducer로 요청 상태 관리하기

첫번째 예제 입니다 Start~

- **폴더구조**

```jsx
ㄴ App.js - 부모컴포넌트
ㄴ Users.js - 자식컴포넌트

App.js에서 Users.js를 불러와서 렌더링을 시켜주면 됩니다!
```

- **Users.js**

```jsx
import React, { useEffect, useReducer } from 'react';
import axios from 'axios';

/* 
   [리듀서 함수 정의]
   넘어온 action.type에 따라서 object를 return 해주는 역할을 한다.
*/

function reducer(state, action) {
  switch (action.type) {
    case 'LOADING':
      return {
        loading: true,
        data: null,
        error: null
      };
    case 'SUCCESS':
      return {
        loading: false,
        data: action.data,
        error: null
      };
    case 'ERROR':
      return {
        loading: false,
        data: null,
        error: action.error
      };
    default:
      throw new Error(`Unhandled action type: ${action.type}`);
  }
}

function Users() {
  // State 정의
  /*
    위에서 만들어준 reducer 함수를 연결시켜주기 위해서
    useReducer함수 첫번째 인자로 reducer 함수를 넘겨준다.
    두번째 인자로는 초기값을 넣어준다.
  */
  const [state, dispatch] = useReducer(reducer, {
    loading: false,
    data: null,
    error: null
  });
  
  // API 함수 정의
  const fetchUsers = async () => {
    /* 
      state를 변경하기 위해선 무조건 dispatch 함수를 호출한다. 호출되면
      useReducer로 reducer를 연결시켜놨기 때문에 { type: 'LOADING' } 값을
      reducer함수에서 매개변수로 받을 수 있게 된다. 그리고 조건에 따라서 Object을 반환하고
      최종적으로 return된 정보를 State에 저장하게 된다. 상태가 변경이 되면 리렌더링을 한다.
    */
    dispatch({ type: 'LOADING' });
    try {
      
      // API 호출
      const response = await axios.get(
        'https://jsonplaceholder.typicode.com/users'
      );
      dispatch({ type: 'SUCCESS', data: response.data });
    } catch (e) {
      dispatch({ type: 'ERROR', error: e });
    }
  };
  
  // 첫 렌더링하기 전에 한번 호출됨
  useEffect(() => {
    fetchUsers();
  }, []);
  
  // 비구조할당 문법을 통해서 변수에 저장
  const { loading, data: users, error } = state; // state.data 를 users 키워드로 조회

  if (loading) return <div>로딩중..</div>;
  if (error) return <div>에러가 발생했습니다</div>;
  if (!users) return null;

  return (
    <>
      <ul>
        {users.map(user => (
          <li key={user.id}>
            {user.username} ({user.name})
          </li>
        ))}
      </ul>
      <button onClick={fetchUsers}>다시 불러오기</button>
    </>
  );
}

export default Users;
```

## 3. useAsync 커스텀 Hook 만들어서 사용하기

위에서는 한 파일에서 useReducer를 사용했다면 이번 예제는 useReducer파일을 분리하여 다른 컴포넌트에서도 재사용할 수 있도록 합니다. 

- **폴더구조**

```jsx
ㄴ App.js - 최상위 컴포넌트
ㄴ Users.js - 전체유저 컴포넌트
ㄴ User.js - 상세유저 컴포넌트
ㄴ UseAsync.js - useAsync 컴포넌트

Users.js와 User.js에서 API를 사용하기 때문에 
UseAsync.js를 import해서 사용하는 구조이다!

UseAsync.js를 위처럼 재활용하기 위해 컴포넌트로 분리

```

- **useAsync.js**

```jsx
import { useReducer, useEffect } from 'react';

// reducer 함수생성
function reducer(state, action) {
  switch (action.type) {
    case 'LOADING':
      return {
        loading: true,
        data: null,
        error: null
      };
    case 'SUCCESS':
      return {
        loading: false,
        data: action.data,
        error: null
      };
    case 'ERROR':
      return {
        loading: false,
        data: null,
        error: action.error
      };
    default:
      throw new Error(`Unhandled action type: ${action.type}`);
  }
}

// 1. 실행할 함수, 2, 렌더링조건, 3, API 호출여부
function useAsync(callback, deps = [], skip = false) {
  const [state, dispatch] = useReducer(reducer, {
    loading: false,
    data: null,
    error: false
  });
  
  // API 호출 
  const fetchData = async () => {
    // dispatch를 통해서 상태 갱신
    dispatch({ type: 'LOADING' });
    try {
      // 파라미터로 받은 함수를 여기서 실행
      const data = await callback();
      dispatch({ type: 'SUCCESS', data });
    } catch (e) {
      dispatch({ type: 'ERROR', error: e });
    }
  };

  useEffect(() => {
    if (skip) return;
    fetchData();
    // eslint 설정을 다음 줄에서만 비활성화
    // eslint-disable-next-line
  }, deps);
  
  // 마지막으로 상태와, fetchData함수를 배열에 담아서 return 한다.
  return [state, fetchData];
}

export default useAsync;
```

- **Users.js**

```jsx
import React, { useState } from 'react';
import axios from 'axios';
import useAsync from './useAsync';
import User from './User';

// useAsync 에서는 Promise 의 결과를 바로 data 에 담기 때문에,
// 요청을 한 이후 response 에서 data 추출하여 반환하는 함수를 따로 만들었습니다.
async function getUsers() {
  const response = await axios.get(
    'https://jsonplaceholder.typicode.com/users'
  );
  return response.data;
}

function Users() {
  const [userId, setUserId] = useState(null);
  // useAsync 컴포넌트에서 return해준 state와 함수를 상태에 저장시킨다.
  const [state, refetch] = useAsync(getUsers, [], true);
  const { loading, data: users, error } = state; // state.data 를 users 키워드로 조회

  if (loading) return <div>로딩중..</div>;
  if (error) return <div>에러가 발생했습니다</div>;
  if (!users) return <button onClick={refetch}>불러오기</button>;
  return (
    <>
      <ul>
        {users.map(user => (
          <li
            key={user.id}
            <!-- 
              클릭시 유저id를 State(userId)에 갱신
            -->
            onClick={() => setUserId(user.id)}
            style={{ cursor: 'pointer' }}
          >
            {user.username} ({user.name})
          </li>
        ))}
      </ul>
      <button onClick={refetch}>다시 불러오기</button>
      <!-- 
        State(userId)에 값이 있으면 User 컴포넌트 호출하면서 props로
        State(userId)를 넘긴다.
      -->
      {userId && <User id={userId} />}
    </>
  );
}

export default Users;
```

- **User.js**

```jsx
import React from 'react';
import axios from 'axios';
import useAsync from './useAsync';

async function getUser(id) {
  const response = await axios.get(
    `https://jsonplaceholder.typicode.com/users/${id}`
  );
  return response.data;
}

function User({ id }) {
  /*
    이 컴포넌트에서도 API를 사용하기 때문에 useAsync 컴포넌트를 불러온다.
    무한렌더링을 방지하기 위하여 () => getUser(id) 형태로 파라미터를 넘기고 있다.
    state값만 받아서 상태에 저장한다.
  */
  const [state] = useAsync(() => getUser(id), [id]);
  // useAsync 컴포넌트에서 return 해준 정보를 저장한다.
  const { loading, data: user, error } = state;

  if (loading) return <div>로딩중..</div>;
  if (error) return <div>에러가 발생했습니다</div>;
  if (!user) return null;

  return (
    <div>
      <h2>{user.username}</h2>
      <p>
        <b>Email:</b> {user.email}
      </p>
    </div>
  );
}

export default User;
```

## 4. react-async로 요청 상태 관리하기

`react-async`는 위 예제에서 만들었던 `useAsync`와 비슷한 함수가 들어있는 라이브러리입니다.

위 처럼 useAsync 컴포넌트를 만들지 않아도 해당 모듈을 사용해서 기능 구현이 가능합니다.

```bash
// 라이브러리를 설치해주세요
$ yarn add react-async
```

- **Users.js**

```jsx
import React, { useState } from 'react';
import axios from 'axios';

// react-async 라이브러리를 불러옵니다!
import { useAsync } from 'react-async';
import User from './User';

async function getUsers() {
  const response = await axios.get(
    'https://jsonplaceholder.typicode.com/users'
  );
  return response.data;
}

function Users() {
  const [userId, setUserId] = useState(null);
  /* 
    useAsync 함수에 첫번째 인자로 {}를 넘기는데
    promiseFn 속성에 실행할 API 함수를 넘겨주면 됩니다.
    그리고 실행이 완료되면 useAsync에서 data, error, isLoading, reload를 return
    해주고 그 값을 받아서 저장해주는 처리입니다.
  */
  const { data: users, error, isLoading, reload } = useAsync({
    promiseFn: getUsers
  });

  if (isLoading) return <div>로딩중..</div>;
  if (error) return <div>에러가 발생했습니다</div>;
  if (!users) return <button onClick={reload}>불러오기</button>;
  return (
    <>
      <ul>
        {users.map(user => (
          <li
            key={user.id}
            onClick={() => setUserId(user.id)}
            style={{ cursor: 'pointer' }}
          >
            {user.username} ({user.name})
          </li>
        ))}
      </ul>
      <button onClick={reload}>다시 불러오기</button>
      {userId && <User id={userId} />}
    </>
  );
}

export default Users;
```

- **User.js**

```jsx
import React from 'react';
import axios from 'axios';
import { useAsync } from 'react-async';

async function getUser({ id }) {
  const response = await axios.get(
    `https://jsonplaceholder.typicode.com/users/${id}`
  );
  return response.data;
}

function User({ id }) {
  /*
    첫번째 인자 : 실행할 함수
    두번째 인자 : id 변경되었을 때에도 함수를 실행하기 위해서 넘겨줌
    watch: id가 변경되었는지 계속 바라보면서 체킹!
  */
  const { data: user, error, isLoading } = useAsync({
    promiseFn: getUser,
    id,
    watch: id
  });

  if (isLoading) return <div>로딩중..</div>;
  if (error) return <div>에러가 발생했습니다</div>;
  if (!user) return null;

  return (
    <div>
      <h2>{user.username}</h2>
      <p>
        <b>Email:</b> {user.email}
      </p>
    </div>
  );
}

export default User;
```

결국 2개는 똑같은 기능을 지원합니다. 끝으로 정리.

- **useAsync 커스텀 Hook**
useAsync에 동작방법을 전부 이해했다면 필요한 기능들을 커스텀하면서 유연하게 추가 및 수정할 수 있음.
Hook을 직접 만들어야 되기 때문에 처음 만드는데 시간이 좀 소요될 것 같음.
하지만 한번 만들면 재활용할 수 있음.
- **react-async 라이브러리**
다양한 옵션기능을 사용할 수 있음
너무 많은 옵션으로 헷갈릴 수 있음.
Hook을 직접 만들지 않아도 사용할 수 있어서 굉장히 편리함.

## 6. 리액트 (6)

useState 말고도 useReducer 을 통해서 상태관리를 할 수 있다.

useReducer 의 장점은 상태 업데이트 로직을 컴포넌트에서 분리 할 수 있다는 것이다.

useReducer 의 개념은 redux 에서도 사용되는 개념이기 때문에 redux 를 배우기 전에 useReduce 먼저 숙제하도록 하자.

 javascript 의 reduce 함수는 합계를 더해주는 용도로 많이 사용되나 react 의 reduce 개념은 액션을 받아 새로운 상태를 반환해 주는 용도로 사용된다.

 그래서 reduce 함수는 현재상태 (state) 와 action 을 파라미터로 받는다.

 기존에 만들었던 Counter.js 컴포넌트에 useReducer 을 적용해보도록 하자.

```jsx
import React, { useReducer } from 'react';

function reducer (state, action) {  
  switch(action.type) {
    case 'PLUS':
      return state + 1;
    case 'MINUS':
      return state - 1;
    default:
      return state;
  }
}

function Counter () {
  const [number, dispatch] = useReducer(reducer, 0);

  const plus = () => {
    dispatch({ type: 'PLUS'});
  };

  const minus = () => {
    dispatch({type: 'MINUS'});
  };

  return (
    <>
      <h1>{number}</h1>
      <button onClick={plus}>+1</button>
      <button onClick={minus}>-1</button>
    </>
  );
};

export default Counter;
```

 위의 코드에서 보는것처럼 useReducer 은 reducer 을 첫번쨰 인자로 받고 두번쨰 인자는 상태의 초기값을 받는다.

 그리고 상태값을 변경해주고 싶을때는 dispatch 를 통해서 액션을 넘겨주어 새로운 상태를 반환해준다.
( 액션은 type 을 가진 객체이어야 하며 type 외의 값은 원하는 값으로 셋팅해주면 된다 )

 그럼 이제 Counter.js 파일에 셋팅된 useReducer 을 다른 파일로 옮겨 상태관리를 해보자.

reducers 라는 이름의 폴더를 만들고 그 하위에 Counter.js 파일을 생성한다.

해당 파일에는 아까 components/Conter.js 에서 생성했던 reducer 함수를 옮겨서 넣어준다.

추가로 상단에 초기값을 설정하는 initialState 를 선언해서 number 의 초기값을 넣어주도록 하자.

```jsx
// reducers/Counter.js

// 초기값 설정
export const initialState = {
  number: 0
};

const Reducer = (state, action) => {
  switch(action.type) {
    case 'PLUS':
      return state + 1;
    case 'MINUS':
      return state - 1;
    default:
      return state;
  }
};

export default Reducer;
```

이제 compoents/Conter.js 파일에서 해당 Reducer 함수를 호출해서 사용해주면 된다.

```jsx
import React, { useReducer } from 'react';
import Reducer, {initialState} from '../reducers/Counter';

function Counter () {
  const [number, dispatch] = useReducer(Reducer, initialState.number);

  const plus = () => {
    dispatch({ type: 'PLUS'});
  };

  const minus = () => {
    dispatch({type: 'MINUS'});
  };

  return (
    <>
      <h1>{number}</h1>
      <button onClick={plus}>+1</button>
      <button onClick={minus}>-1</button>
    </>
  );
};

export default Counter;
```

 기존 useState 를 사용할 때에는 상태 관리를 위해 최상위 컴포넌트 에서 이벤트 함수를 만들어 자식 컴포넌트 에 props 로 보내야 했지만 useReducer 을 사용함으로 인해서 원하는 컴포넌트 파일에서 import 로 해당 reducer 파일을 불러서 사용할 수 있게끔 되었다.
 
## 7. 리액트 (7)
## 개요

 백앤드 express  개발을 하면서 라우터 개념에 대해 어느정도 이해하고 있을것이다.

router 는 백앤드와 동일하게 특정 페이지로 연결해주는 역할을 한다.

react 에서 router 가 필요한 이유는 spa 의 특징 떄문인데, 페이지 이동시 mpa 처럼 페이지를 이동하는게 아니라 노출되는 페이지 안에 다른 페이지를 출력해주는 처리가 필요하기 떄문에 router 처리가 필요하다.

## 설치

```jsx
yarn add react-router-dom
```

## 적용

- src/index.js 에서 `BrowserRouter` 컴포넌트를 호출한 후 App 을 해당 컴포넌트로 감싸주면 된다.

```jsx
import { BrowserRouter } from 'react-router-dom';

ReactDOM.render(
  <BrowserRouter>
    <App />
  </BrowserRouter>,
  document.getElementById('root')
);
```

- 이제 주소별 호출될 페이지를 만들어 보자.

### Home.js

```jsx
import React from 'react';

function Home () {
  return (
    <div>
      <h1>Home</h1>
      <p>홈 화면입니다.</p>
    </div>
  );
};

export default Home;
```

### User.js

```jsx
import React from 'react';

function User () {
  return (
    <div>
      <h1>User</h1>
      <p>사용자 리스트 페이지 입니다.</p>
      <ul>
        <li>로니</li>
        <li>카리스</li>
        <li>초비</li>
        <li>써니</li>
        <li>어빙</li>
        <li>카렌</li>
        <li>칼리</li>
      </ul>
    </div>
  );
};

export default User;
```

### App.js

- App.js 에서 위에 만들어둔 페이지를 호출할 주소를 셋팅해준다.
- 만들어둔 Home, User 컴포넌트를 불어와서 Route 안에 설정해주면 된다.
- exact 라고 추가된 부분은 라우터 경로가 인식되는 조건이 완전이 같은게 아니라 포함되는 조건이기 때문에 / 는 /user 에 포함되는 조건이라 user 접속시 / 에 설정한 컴포넌트도 같이 노출되는 문제가 있는데 이를 막기위해 포함조건이 아니라 동일 조건으로 변경해주는 옵션이다.

```jsx
import React from 'react';
import { Route } from 'react-router-dom';
import Home from './Home';
import User from './User';

function App() {
  return (
    <div>      
     <Route path="/" component={Home} exact />
     <Route path="/user" component={User} />
    </div>
  );
}

export default App;
```

- 이제 웹페이지에서 주소 변경시 생성한 페이지대로 정상 노출되는지 확인하면 된다.

## Link

- html 의 a 태그와 같이 페이지를 이동하는 기능을 라우터를 통해 구현할 수 있는데 link 를 사용한다.
- 사용방법은 아래의 코드를 참고하자.

```jsx
// app.js

import React from 'react';
import { Route, Link } from 'react-router-dom';
import Home from './Home';
import User from './User';

function App() {
  return (
    <div>
      <ul>
        <li>
          <Link to="/">Home</Link>
          </li>
        <li>
          <Link to="/user">User</Link>          
        </li>
      </ul>
      <hr />
     <Route path="/" component={Home} exact />
     <Route path="/user" component={User} />
    </div>
  );
}

export default App;
```

- 링크 클릭시 상단의 주소가 잘 변경되는지, 원하는 페이지의 정보가 잘 노출되는지 확인하면 된다.
## 8. 리액트 (8)
## 개요

- 이제 리엑트 개발에 필요한 api, router, redux 등을 배웠으니 해당 기능을 이용한 사용자 조회 페이지 만들기를 진행해보자.
- api 호출은 백앤드 api 를 만들지 않고 json-server 기능을 이용해 데이터를 호출해 사용한다.

## 프로젝트 설치

```jsx
npx create-react-app users-test
```

## 호출 데이터 셋팅

- json-server 를 통해 데이터를 호출할 것이기 때문에 루트에 data.json 을 생성한 후 데이터를 넣어준다.

[Json-Server](https://www.notion.so/Json-Server-9c916769ec5d4bc6a5f091e75500a778)

- json-server 설치

```jsx
yarn add json-server -g
```

- 데이터 셋팅

```jsx
// data.json

{
  "users": [
    {
      "id": 1,
      "name": "서상권",
      "english_name": "rony",
      "description": "안녕하세요. 로니 입니다."
    },
    {
      "id": 2,
      "name": "이다훈",
      "english_name": "karis",
      "description": "안녕하세요. 카리스 입니다."
    }
  ]
}
```

- json-server 실행 후 postman 에서 데이터가 정상적으로 조회되는지 확인한다.
( [http://localhost:4000/users](http://localhost:4000/users) )

```jsx
json-server --watch data.json --port 4000
```

## react 모듈 설치

- 개발에 필요한 axios, redux 등의 리액트 모듈을 설치해준다.

```jsx
yarn add 
				axios 
				redux 
				react-redux 
				redux-saga 
				react-router-dom 
				redux-logger 
```

## Api 생성

- 만들어둔 users 를 조회할 api 를 생성한다.
- 해당 api 는 axois 를 이용하여 호출하도록 한다.
- src/api/user.js 파일 생성

```jsx
// src/api/user.js

import axios from 'axios';

export const getUsers = async () => {
  const res = await axios.get('http://localhost:4000/users');
  return res.data;
}
```

## 상태관리 (store)

### modules/user.js

- 이제 위의 데이터를 처리해주기 위해 store 를 만들어준다.
- src 하위에 modules 폴더를 만들어주고 user.js 파일을 생성한다.
- 여기에서 호출할 액션,  다른 파일에서 호출할 액션 생성 함수, 리듀서를 만들어준다.

```jsx
// src/modules/user.js

import { call, put, takeEvery } from 'redux-saga/effects';

// api 호출
import * as userAPI from '../api/user';

// 액션 타입선언
const GET_USERS = 'user/GET_USERS';
const GET_USERS_SUCCESS = 'user/GET_USERS_SUCCESS';
const GET_USERS_ERROR = 'user/GET_USERS_ERROR';

// 액션생성함수 선언.
// 실제 호출은 getUsers 만 하고 success, error 은 getUsersSaga 함수에서 호출함.
export const getUsers = () => ({ type: GET_USERS });

// saga 함수 생성
function* getUsersSaga () {
  try {
    const users = yield call(userAPI.getUsers);
    yield put({
      type: GET_USERS_SUCCESS,
      data: users
    });
  } catch (err) {
    yield put({
      type: GET_USERS_ERROR,
      error: true,
			data: err
    });
  }
}

// 생성된 saga 함수를 액션에 매칭해준다.
export function* usersSaga () {
  yield takeEvery(GET_USERS, getUsersSaga);
}

// 초기상태 선언
const initialState = {
  users: {
    loading: false,
    data: null,
    error: null
  }
};

// 리듀서 생성
const user = (state = initialState, action) => {
  switch (action.type) {
    case GET_USERS:
      return {
        ...state,
        users: {
          loading: true,
          data: null,
          error: null
        }
      }
    case GET_USERS_SUCCESS:
      return {
        ...state,
        users: {
          loading: false,
          data: action.data,
          error: null
        }
      }
    case GET_USERS_ERROR:
      return {
        ...state,
        users: {
          loading: false,
          data: null,
          error: action.error
        }
      }
    default:
      return state;
  } 
}

export default user;
```

### modules/index.js

- 이제 rootReducer, rootSaga 작업을 해준다.

```jsx
import { combineReducers } from 'redux';
import user, { usersSaga } from './user';
import { all } from 'redux-saga/effects';

// 리듀서 합치기
const rootReducer = combineReducers({
  user
});
// saga 합치기
export function* rootSaga () {
  yield all([
    usersSaga()
  ]);
}

export default rootReducer;
```

### src/index.js

- 이제 index.js 파일에서 store 를 만들고 rootReducer, rootSaga 를 스토어에 적용해준다.

```jsx
import React from 'react';
import ReactDOM from 'react-dom';
import './index.css';
import App from './App';
import * as serviceWorker from './serviceWorker';

// 필요모듈 호출
import { createStore, applyMiddleware } from 'redux';
import { Provider } from 'react-redux';
import logger from 'redux-logger';
import createSagaMiddleware from 'redux-saga';
import rootReducer, { rootSaga } from './modules';

// sagaMiddleware 생성
const sagaMiddleware = createSagaMiddleware();

// store 생성
const store = createStore(
  rootReducer,
  applyMiddleware(
    sagaMiddleware,
    logger
  )
);

// rootSaga 실행
sagaMiddleware.run(rootSaga);

// App 을 Provider 로 감싸준 후 store 적용
ReactDOM.render(
  <Provider store={store}>
    <App />
  </Provider>,
  document.getElementById('root')
);

// If you want your app to work offline and load faster, you can change
// unregister() to register() below. Note this comes with some pitfalls.
// Learn more about service workers: https://bit.ly/CRA-PWA
serviceWorker.unregister();
```

## 사용자 리스트 컴포넌트 만들기

- 상태관리 설정이 끝났기 때문에 사용자 리스트를 보여줄 컴포넌트를 생성한다.
- 컴포넌트는 디자인을 보여줄 컴포넌트와 상태관리적용을 해줄 컴포넌트로 나눠서 작업한다.

### components/UserList.js

- 사용자리스트를 출력해줄 컴포넌트를 생성한다.

```jsx
// src/components/UserList.js

import React from 'react';

function UserList ({ users }) {
  return (
    <ul>
      {users.map(user => (
        <li key={user.id}>
          {user.name}
        </li>
      ))}
    </ul>
  );
};

export default UserList;
```

### containers/UserListContainer.js

- 이제 사용자 리스트 처리를 위한 UserListContainer.js 을 생성한다.
- 컨테이너 컴포넌트의 역할은 관련 상태를 조회하고 상태에 맞게 화면 출력을 해주는 역할을 한다.

```jsx
import React, { useEffect } from 'react';
import UserList from '../components/UserList';
import { useSelector, useDispatch } from 'react-redux';
import { getUsers } from '../modules/user';

function UserListContainer () {

  const { loading, data, error } = useSelector(state => state.user.users);
  const dispatch = useDispatch();

  useEffect(() => {
    dispatch(getUsers());
  }, [dispatch]);

  if (loading) return <div>로딩중...</div> 
  if (error) return <div>에러!</div>
  if (!data) return null;
  
  return (
    <UserList users={data} />
  );
};

export default UserListContainer;
```

### src/App.js

- App.js 에서 컨테이너컴포넌트를 호출한 후 데이터가 잘 출력되는지 확인한다.

```jsx
import React from 'react';
import UserListContainer from './containers/UserListContainer';

function App() {
  return (
    <UserListContainer />
  );
}

export default App;
```

### 어떻게 user 정보를 호출했는가..

- UserListConrainer 에서 modules/user 에 있는 getUsers 함수를 dispatch 함으로써 해당 액션이 호출되었다.
- `GET_USERS` 액션이 호출되게 되면 modules/user 에 takeEvery 로 설정한 사가 함수가 실행되게 되므로 결국에 getUsersSaga 함수가 호출되어 user api 를 호출해 데이터를 받아오게 된다.
- getUsersSaga 함수실행을 통해 데이터를 받아오게 되면 yield put 으로 GET_USERS_SUCCESS 액션을 발생시키므로 관련로직은 user 리듀서에 의해 상태를 업데이트 해주게 된다.

## 사용자 상세 만들기

### src/api/user.js

- 사용자 상세를 조회하는 api 를 추가한다.
- REST API 규칙에 따라 get 방식으로 호출주소 뒤에 id 를 붙여서 조회하면 된다.

```jsx
export const getUserDetail = async (id) => {
  const res = await axios.get(`http://localhost:4000/users/${id}`);
  return res.data;
}
```

### src/modules/user.js

- 해당 api 를 호출할 액션 및 액션생성 함수, 리듀서 처리를 진행한다.

```jsx
// 사용자 상세 액션 타입 선언
const GET_USER_DETAIL = 'user/GET_USER_DETAIL';
const GET_USER_DETAIL_SUCCESS = 'user/GET_USER_DETAIL_SUCCESS';
const GET_USER_DETAIL_ERROR = 'user/GET_USER_DETAIL_ERROR';

// 액션생성함수 선언.
export const getUserDetail = (id) => ({ type: GET_USER_DETAIL, data: id });

// saga 함수 생성
function* getUserDetailSaga (action) {
	const id = action.data;

  try {
		// yield call 로 api 호출시 파라미터는 두번째 인자로 넘겨주면 된다.
    const user = yield call(userAPI.getUserDetail, id);
    yield put({
      type: GET_USER_DETAIL_SUCCESS,
      data: user,
			meta: id
    });
  } catch (err) {
    yield put({
      type: GET_USER_DETAIL_ERROR,
      error: true,
      data: err,
			meta: id
    });
  }
}

// 생성된 saga 함수를 하나의 함수로 만들어줌.
export function* usersSaga () {
  yield takeEvery(GET_USERS, getUsersSaga);
  yield takeEvery(GET_USER_DETAIL, getUserDetailSaga);
}

// 리듀서에 사용자 상세 추가
const user = (state = initialState, action) => {
  switch (action.type) {
    case GET_USER_DETAIL:
      return {
        ...state,
        user: {
          loading: true,
          data: null,
          error: null
        }
      }
    case GET_USER_DETAIL_SUCCESS:
      return {
        ...state,
        user: {
          loading: false,
          data: action.data,
          error: null
        }
      }
    case GET_USER_DETAIL_ERROR:
      return {
        ...state,
        user: {
          loading: false,
          data: null,
          error: action.error
        }
      }
    default:
      return state;
  } 
}
```

### src/components/UserDetail.js

- 사용자 상세 화면을 보여줄 컴포넌트를 생성한다.

```jsx
import React from 'react';

function UserDetail ({ user }) {
  return (
    <>
      <h1>{user.name} 님</h1>
      <div>
        영어이름 : {user.english_name}
      </div>
      <div>
        소개 : {user.description}
      </div>
    </>
  );
};

export default UserDetail;
```

### src/containers/UserDetailContainer.js

- 사용자 처리를 위한 컨테이너 컴포넌트를 생성해준다.

```jsx
import React, { useEffect } from 'react';
import UserDetail from '../components/UserDetail';
import { useSelector, useDispatch } from 'react-redux';
import { getUserDetail } from '../modules/user';

// 사용자 아이디를 props 로 받아온다.
function UserDetailContainer ({ userID }) {

  const { loading, data, error } = useSelector(state => state.user.user);
  const dispatch = useDispatch();

  // dispatch 시에 userID 를 넘겨주어야 하고, 
  // 해당 값의 변경이 있는경우 재로딩 하기 위헤 useEffect 의 두번째 인자에 해당 값을 넣어준다.
  useEffect(() => {
    dispatch(getUserDetail(userID));
  }, [userID, dispatch]);

  if (loading) return <div>로딩중...</div>
  if (error) return <div>에러발생!</div> 
  if (!data) return null;

  return (
    <>
      <UserDetail user={data} />
    </>
  );
};

export default UserDetailContainer;
```

이제 뭘 해줘야 하지...?

사용자 리스트의 특정 사용자 클릭시 사용자 상세화면이 출력되게 처리해주면 된다.

기존에는 App.js 에서 UserListContainer 컴포넌트를 호출하여 데이터를 출력해주었지만 이제 출력해야 할 화면이 2개 이상이 되었기 때문에 page 컴포넌트를 만들어서 해당 페이지 컴포넌트에서 유저 컴포넌트를 불어오는 방식으로 작업을 진행한다.

## 라우터적용

- 먼저 pages 폴더를 생성 해준 후 해당 폴더 하위로 사용자리스트를 보여줄 페이지와 사용자 상세를 보여줄 페이지를 생성해준다.

### src/pages/UserListPage.js

```jsx
import React from 'react';
import UserListContainer from '../containers/UserListContainer';

function UserListPage () {
  return (
    <UserListContainer />
  );
};

export default UserListPage;
```

### src/pages/UserDetailPage.js

- 해당 컴포넌트에서는 UserDetailContainer 에 userID 값을 넘겨주는 처리가 추가된다.

```jsx
import React from 'react';
import UserDetailContainer from '../containers/UserDetailContainer';

function UserDetailPage ({ match }) {
  const { id } = match.params;

  return (
    // 넘어오는 값이 문자열로 넘어오기 때문에 숫자로 변환해주어야 함.
    <UserDetailContainer userID={parseInt(id, 10)} />
  );
};

export default UserDetailPage;
```

### src/App.js

- 이제 App.js 에서 해당 페이지의 라우트 처리를 한다.

```jsx
import React from 'react';
import { Route } from 'react-router-dom';
import UserListPage from './pages/UserListPage';
import UserDetailPage from './pages/UserDetailPage';

function App() {
  return (
    <>
      <Route path="/" component={UserListPage} exact />
      <Route path="/:id" component={UserDetailPage} />
    </>
  );
}

export default App;
```

### src/components/UserList.js

- 이제 특정 사용자 클릭시 페이지 처리를 위해 사용자 리스트 컴포넌트로 이동후 Link 처리를 추가한다.

```jsx
import React from 'react';
import { Link } from 'react-router-dom';

function UserList ({ users }) {
  return (
    <ul>
      {users.map(user => (
        <li key={user.id}>
          <Link to={`/${user.id}`} >{user.name}</Link>
        </li>
      ))}
    </ul>
  );
};

export default UserList;
```

### src/index.js

- 해당 처리가 잘 작동하기 위해서는 index.js 의 Privider 를 BrowserRouter 로 감싸주는 처리를 해주어야 한다.

```jsx
import { BrowserRouter } from 'react-router-dom';

ReactDOM.render(
  <BrowserRouter>
    <Provider store={store}>
      <App />
    </Provider>
  </BrowserRouter>,
  document.getElementById('root')
);
```

- 이제 페이지 리스팅이 잘 되는지... 
사용자 상세로 페이지 이동이 잘 되는지 확인해보자.

## 홈으로 이동

- 사용자 상세에서 사용자 리스트로 이동하는 버튼을 만들어보자.
- 라우트 컴포넌트에서 제공받는 history 를 사용하면 원하는 페이지로 이동할 수 있다.
`history.push('/')`
- 그런데.. 홈으로 이동을 붙일 UserDetail 컴포넌트는 라우트로 호출되는 컴포넌트가 아니기 때문에 바로 history 객체를 사용할 수 없고 withRouter 을 사용하여 처리를 해야 한다.
- 사용방법은 history 를 사용해줄 컴포넌트에서 withRouter 를 불러온 뒤 export default 처리할때 withRouter 로 감싸주면 된다. 아래의 코드를 참고하자.

```jsx
// src/components/UserDetail.js

import React from 'react';
import { withRouter } from 'react-router-dom';

function UserDetail ({ user, history }) {
  
  // 홈으로 이동.
  const goHome = () => {
    history.push('/users');
  }
  
  return (
    <>
      <h1>{user.name}</h1>
      <div>
        영어이름 : {user.english_name}
      </div>
      <div>
        소개 : {user.description}
      </div>
      <button onClick={goHome}>홈으로</button>
    </>    
  );
};

// withRouter 로 내보내는 컴포넌트를 감싸준다.
export default withRouter(UserDetail);
```

## reducer refactoring

- 중복되는 코드가 많아서 코드가 길어지고 보기 불편하다.
- 중복되는 코드를 재사용가능한 함수로 변경해서 사용하도록 하자.

### lib/utils.js

```jsx
import { call, put } from 'redux-saga/effects';

// 재사용할 사가함수
export const actionSaga = (api, success, error) => {
  return function* (action) {
    try {
      const data = yield call(api, action.data);

      yield put({User
        type: success,
        data
      } );
    } catch (err) {
      yield put({
        type: error,
        error: err
      });
    }
  }
}

// 재사용할 리듀서
export const handleActions = (type, key) => {
  const [SUCCESS, ERROR] = [`${type}_SUCCESS`, `${type}_ERROR`];

  return (state, action) => {
    switch (action.type) {
      case type:
        return {
          ...state,
          [key]: {
            loading: true,
            data: null,
            error: null
          }
        }
      case SUCCESS:
        return {
          ...state,
          [key]: {
            loading: false,
            data: action.data,
            error: null
          }
        }
      case ERROR:
        return {
          ...state,
          [key]: {
            loading: false,
            data: null,
            error: action.error
          }
        }
      default:
        return state;
    }
  }
}
```

### modues/user.js

```jsx
import { handleActions } from '../lib/utils';

// 사가 함수를 통해 api 호출해주던부분을 없애고 userSaga 에 바로 작업을 해준다.
export function* userSaga () {
  yield takeEvery(GET_USERS, actionSaga(userAPI.getUserList, GET_USERS_SUCCESS, GET_USERS_ERROR));
	yield takeEvery(GET_USER_DETAIL, sagaAction(userAPI.getUserDetail, GET_USER_DETAIL_SUCCESS, GET_USER_DETAIL_ERROR));
}

// utils 에 만들어둔 handleActions 를 호출하여 리듀서를 간단하게 변경해준다.
export default function user (state = initialState, action) {
  switch (action.type) {
    case GET_USERS:
    case GET_USERS_SUCCESS:
    case GET_USERS_ERROR:
      return handleActions(GET_USERS, 'users')(state, action);
		case GET_USER_DETAIL:
    case GET_USER_DETAIL_SUCCESS:
    case GET_USER_DETAIL_ERROR:
      return handleAction(GET_USER_DETAIL, 'user')(state, action);
    default:
      return state;
  }
}
```

## 사용자 삭제

- 그럼 이제 사용자 삭제를 만들어보자.
- 사용자 리스트의 사용자 이름 옆에 삭제 버튼을 위치하기 위해 UserList 컴포넌트에서 출력하는 형식을 styled-components 를 이용하여 테이블 형식으로 변경하도록 하겠다.
- 삭제 버튼 클릭시 이벤트 처리할 삭제함수는 UserListContainer 에서 받아오도록 한다.
사실 UserList 컴포넌트에서 바로 처리해도 되지만 상태관리는 container 컴포넌트에서 하기로 했으니 실제 dispatch 는 container 컴포넌트에서 처리하도록 하자.

### src/components/UserList.js

```jsx
// src/components/UserList.js

import React from 'react';
import { Link } from 'react-router-dom';
import styled from 'styled-components';

// 테이블 스타일을 설정한다.
const StyledTable = styled.table`
  border: 1px solid black;
  margin-top: 30px;
  margin-left: 30px;
  border-collapse: collapse;
  width: 300px;
  th {
    border: 1px solid black;
    text-align: center;
    height: 50px;
    background-color: silver;
  }
  td {
    border: 1px solid black;
    text-align: center;
    height: 30px;
  }
`;

// props 로 사용자 삭제 함수를 뱓아와서 처리한다.
function UserList ({ users, onClick }) {

  // 삭제하는 사용자의 id 값을 받아오기 위해 버튼에 value 속성을 넣어 id 를 지정해주고
  // 클릭 함수에서 해당 값을 받아온다.
  // value 값은 문자열이기 떄문에 숫자형으로 변경해주도록 하자.
  const deleteUser = (e) => {
    onClick(parseInt(e.target.value, 10));
  }
  
  return (
    <>
      <StyledTable>
        <thead>
          <tr>
            <th colSpan="2">USER LIST</th>
          </tr>          
        </thead>
        <tbody key='tbody'>
          {users.map(user => (
            <tr key={user.id}>
              <td width="200px">
                <Link to={`/users/${user.id}`}>{user.name}</Link>
              </td>
              <td>
                <button onClick={deleteUser} value={user.id}>삭제</button>
              </td>
            </tr>
          ))}
        </tbody>
      </StyledTable>
    </> 
  );
};

export default UserList;
```

### UserListContainer.js

- 삭제 이벤트를 실행해줄 함수를 만들어준다.

```jsx
// 삭제는 실수로 데이터를 지우는걸 방지하기 위해 confirm 으로 체크를 해주도록 한다.
// dispatch 해주는 userDelete 는 modules/user.js 에 생성해주어야 한다.
const onClick = (id) => {
  if (window.confirm('정말 삭제하시겠습니까?')) {
    dispatch(userDelete(id));
  }
}
```

### src/modules/user.js

- 포인트는 기존에 액션타입을 만들때 기본타입+성공타입+실패타입을 만들었지만 삭제는 기본타입만 생성한다.
- 왜냐하면 삭제 후 성공을 반환하는게 아니라 사용자 삭제후 다시 사용자 정보를 불러와서 보여줄 것이기 때문에 삭제 성공, 실패 타입은 굳이 만들어 줄 필요가 없다.
- sagaAction 에서 두번의 api 호출을 해주어야 하기 때문에 기존 3개의 인자를 받던부분을 4개의 인자를 받는것으로 변경작업을 진행한다.
기존 : action , 성공 실행 액션, 실패 실행 액션
변경 : aciion, action2, 성공 실행액션, 실패 실행 액션
- 삭제후 성공실행 액션은 사용자 정보를 불러와서 보여주어야 하기 때문에 GET_USERS_SUCCESS, GET_USERS_ERROR 를 사용한다.

```jsx
// 액션 타입 생성
const USER_DELETE = 'user/USER_DELETE';

// 외부에서 호출해 줄 액션 생성함수 생성
export const userDelete = (id) => ({ type: USER_DELETE, data: id });

export function* userSaga () {
  yield takeEvery(GET_USERS, sagaAction(userAPI.getUserList, '', GET_USERS_SUCCESS, GET_USERS_ERROR));
  yield takeEvery(GET_USER, sagaAction(userAPI.getUserDetail, '', GET_USER_SUCCESS, GET_USER_ERROR));

  // userSaga 에 사용자 삭제 로직을 추가한다.
  yield takeEvery(USER_DELETE, sagaAction(userAPI.deleteUser, userAPI.getUserList, GET_USERS_SUCCESS, GET_USERS_ERROR));
}
```

### src/api/user.js

- api 에 사용자 삭제호출을 추가한다.

```jsx
// 사용자 삭제
export const deleteUser = async (id) => {
  const res = await axios.delete(`http://localhost:4000/users/${id}`);
  return res.data;
}
```

### src/lib/uitls.js

- sagaAction 함수의 인자를 4개로 변경해주었기 때문에 해당 함수를 수정해주어야 한다.

```jsx
export const sagaAction = (api, second_api, success, error) => {
  return function* (action) {
    try {
      let data = yield call(api, action.data);

			// 두번째 api 호출이 있는경우 해당 api 실행.
      if (second_api) {
        data = yield call(second_api);
      }
  
      yield put({
        type: success,
        data
      });
    } catch (err) {
      yield put({
        type: error,
        error: err
      });
    }
  }
}
```

자... 이제 사용자 삭제가 정상적으로 구동되는지 체크해보도록 하자.

## 사용자 정보 수정

- 사용자 정보 수정은 사용자 상세 화면에서 정보를 수정하는 것으로 진행한다.
- 사용자 삭제와 마찬가지를 dispatch 처리는 컨테이너컴포넌트에서 진행하고 관련 함수를 UserDetail 컴포넌트에 넘겨서 데이터를 받는것으로 한다.

### src/api/user.js

- 사용자 정보 업데이트 api 를 먼저 추가한다.
- 참고로 사용자 정보 업데이트에서 받아오는 데이터를 객체로 받아와야 하기 때문에 기존에 받아오던 id 값도 객체로 받아서 처리될 수 있도록 변경하는 작업을 같이 진행한다.

```jsx
import axios from 'axios';

// 사용자 리스트 조회.
export const getUserList = async () => {
  const res = await axios.get('http://localhost:4000/users');
  return res.data;
}

// 사용자 상세
export const getUserDetail = async ({ id }) => {
  const res = await axios.get(`http://localhost:4000/users/${id}`);
  return res.data;
}

// 사용자 삭제
export const deleteUser = async ({ id }) => {
  const res = await axios.delete(`http://localhost:4000/users/${id}`);
  return res.data;
}

// 사용자정보 수정
export const updateUser = async ({ id, english_name, description, name }) => {  
  const res = await axios.put(`http://localhost:4000/users/${id}`, { english_name, description, name });
  return res.data;
}
```

### src/modules/user.js

- 사용자 업데이트 상태관리 로직을 추가한다.
- 사용자 삭제와 마찬가지로 사용자 업데이트 로직이 돌고난 후 사용자 상세를 다시 호출할 것을 참고한다.
( 사용자 상태 업데이트 → 사용자 상세 조회 )

```jsx
// 액션 타입 추가
const USER_UPDATE = 'user/USER_UPDATE';

// 다른 컴포넌트에서 호출해 줄 액션 생성함수 추가.
export const userUpdate = (id, english_name, description, name) => ({ type: USER_UPDATE, data: { id, english_name, description, name } });

// userSaga 에 해당 액션 추가
export function* userSaga () {
  yield takeEvery(GET_USERS, sagaAction(userAPI.getUserList, '', GET_USERS_SUCCESS, GET_USERS_ERROR));
  yield takeEvery(GET_USER_DETAIL, sagaAction(userAPI.getUserDetail, '', GET_USER_DETAIL_SUCCESS, GET_USER_DETAIL_ERROR));
  yield takeEvery(USER_DELETE, sagaAction(userAPI.deleteUser, userAPI.getUserList, GET_USERS_SUCCESS, GET_USERS_ERROR));
  yield takeEvery(USER_UPDATE, sagaAction(userAPI.updateUser, userAPI.getUserDetail, GET_USER_DETAIL_SUCCESS, GET_USER_DETAIL_ERROR));
}
```

### src/container/UserDetailContainer.js

- 사용자 상태를 업데이트 해주는 userUpdate 함수를 호출해준다.

```jsx
import { getUser, userUpdate } from '../modules/user';

// 사용자 상태 업데이트 dispatch
const setUpdate = ({ id, english_name, description, name }) => {
  dispatch(userUpdate(id, english_name, description, name));
}

return (
		// userDetail 컴포넌트에 props 로 전달.
    <UserDetail user={data} userUpdate={setUpdate} />
  );
```

### src/components/UserDetail.js

- 화면구성을 위해 테이블로 화면을 변경해주고 업데이트 해줄 상태를 input, textarea 로 바꿔준다.
- 사용자가 수정가능한 항목을 영어이름, 소개로 잡았으나 이름도 상태값이기 때문에 업데이트 함수에 값을 넘겨주는걸 빼먹지 않도록 주의하자.
- 태그에 값을 담을때는 기존 html 에서 처럼 value 값에 넣는게 아니라 `defaultValue` 안에 담아온 상태값을  넣어주면 된다.

```jsx
import React, { useState } from 'react';
import { withRouter } from 'react-router-dom';
import styled from 'styled-components';

const StyledTable = styled.table`
  border: 1px solid black;
  margin-top: 30px;
  margin-left: 30px;
  border-collapse: collapse;
  width: 300px;
  th {
    border: 1px solid black;
    text-align: center;
    height: 50px;
    background-color: silver;
  }
  td {
    border: 1px solid black;
    text-align: center;
    height: 30px;
  }
  input {
    width: 210px;
  }
  textarea {
    width: 210px;
    height: 100px;
    margin: 5px;
  }
  button {
    margin-left: 5px;
    margin-right: 5px;
  }
`;

function UserDetail ({ user, history, userUpdate }) {
  const [userInfo, setUserInfo] = useState(user);
  const goHome = () => {
    history.push('/users');
  }

  const userInfoUpdate = (e) => {
    setUserInfo({
      ...userInfo,
      [e.target.name]: e.target.value
    });
  }

  // 업데이트
  const updateData = () => {
    userUpdate(userInfo);
  }
  
  return (
    <>
      <StyledTable>
        <thead>
          <tr>
            <th colSpan="2">사용자상세</th>
          </tr>          
        </thead>
        <tbody>
          <tr>
            <td>이름</td>
            <td>
            <input type="text" name="name" defaultValue={userInfo.name} onChange={userInfoUpdate} />
            </td>
          </tr>
          <tr>
            <td>영어이름</td>
            <td>
              <input type="text" name="english_name" defaultValue={userInfo.english_name} onChange={userInfoUpdate} />
            </td>
          </tr>
          <tr>
            <td>소개</td>
            <td>
              <textarea name="description" defaultValue={userInfo.description} onChange={userInfoUpdate}></textarea>
            </td>
          </tr>
          <tr>
            <td colSpan="2">
              <button onClick={goHome}>사용자리스트 바로가기</button>
              <button onClick={updateData}>수정</button>
            </td>
          </tr>
        </tbody>
      </StyledTable>
    </>    
  );
};

export default withRouter(UserDetail);
```

## 사용자 정보 등록

- 사용자 정보 등록을 구현해 보자.
- 사용자 정보 등록 화면을 만드려다보니 해당 화면이 사용자 상세와 너무 유사하다.
- 사용자 등록 버튼 클릭시 사용자 상세 컴포넌트를 불러와서 해당 정보를 넣어주는걸로 처리를 진행해보자.

### src/api/user.js

- 일단 사용자 등록 api 를 만들어준다.

```jsx
// 사용자 추가
export const createUser = async ({ name, english_name, description }) => {
  const res = await axios.post('http://localhost:4000/users', { name, english_name, description });
  return res.data;
}
```

### src/modules/user.js

- 사용자 액션 및 상태값도 추가한다.
- 사용자 추가후 사용자 리스트 목록을 불러오도록 처리한다.

```jsx
// 액션타입 추가
const USER_CREATE = 'user/USER_CREATE';

// 액션 호출 함수 추가.
export const createUser = (name, english_name, description) => ({ type: USER_CREATE, data: { name, english_name, description } });

// userSaga 에 추가
export function* userSaga () {
  yield takeEvery(GET_USERS, sagaAction(userAPI.getUserList, '', GET_USERS_SUCCESS, GET_USERS_ERROR));
  yield takeEvery(GET_USER_DETAIL, sagaAction(userAPI.getUserDetail, '', GET_USER_DETAIL_SUCCESS, GET_USER_DETAIL_ERROR));
  yield takeEvery(USER_DELETE, sagaAction(userAPI.deleteUser, userAPI.getUserList, GET_USERS_SUCCESS, GET_USERS_ERROR));
  yield takeEvery(USER_UPDATE, sagaAction(userAPI.updateUser, userAPI.getUserDetail, GET_USER_DETAIL_SUCCESS, GET_USER_DETAIL_ERROR));
  yield takeEvery(USER_CREATE, sagaAction(userAPI.createUser, userAPI.getUserList, GET_USERS_SUCCESS, GET_USERS_ERROR));
}
```

### src/components/UserList.js

- 이제 사용자 리스트 컴포넌트에서 사용자 추가 버튼 클릭시 UserDetail 컴포넌트를 불러오는 처리를 붙인다.

```jsx
import React, { useState } from 'react';
import { Link } from 'react-router-dom';
import styled from 'styled-components';
import UserDetail from './UserDetail';

const StyledTable = styled.table`
  border: 1px solid black;
  margin-top: 30px;
  margin-left: 30px;
  border-collapse: collapse;
  width: 300px;
  th {
    border: 1px solid black;
    text-align: center;
    height: 50px;
    background-color: silver;
  }
  td {
    border: 1px solid black;
    text-align: center;
    height: 30px;
  }
  input {
    width: 210px;
  }
  textarea {
    width: 210px;
    height: 100px;
    margin: 5px;
  }
`;

function UserList ({ users, onClick, onCreate }) {
  // UserDetail 컴포넌트에 user 로 넣어줄 값을 셋팅한다.
  // 사실... UserDetail 컴포넌트에서 defaultProps 로 셋팅을 할거라 굳이 안넣어도 되긴하다.
  const initinalUserInfo = {
    name: '',
    english_name: '',
    description: ''
  };
  // UserDetail 컴포넌트를 노출시킬 여부를 useState 를 통해 셋팅해준다.
  const [addUser, setAddUser] = useState(false);  
  const deleteUser = (e) => {
    onClick(parseInt(e.target.value, 10));
  }
  
  return (
    <>
      <StyledTable>
        <thead>
          <tr>
            <th colSpan="2">USER LIST</th>
          </tr>          
        </thead>
        <tbody key='tbody'>
          {users.map(user => (
            <tr key={user.id}>
              <td width="200px">
                <Link to={`/users/${user.id}`}>{user.name}</Link>
              </td>
              <td>
                <button onClick={deleteUser} value={user.id}>삭제</button>
              </td>
            </tr>
          ))}
          <tr>
            <td colSpan="2">
							{/* 사용자 추가버튼 클릭할때마다 addUser 값을 변경해주는 로직을 넣는다.  */}
              <button onClick={() => setAddUser(!addUser)}>사용자 추가</button>
            </td>
          </tr>
        </tbody>
      </StyledTable>

      {/* 사용자 추가 컴포넌트를 셋팅한다. */}
      { addUser ? <UserDetail onCreate={onCreate} user={initinalUserInfo} /> : null }      
    </> 
  );
};

export default UserList;
```

### src/components/UserDetail.js

- 이제 UserDetail 컴포넌트에서 defaultProps 설정해주어야 한다.
( 해당 컴포넌트를 등록, 상세 모두 사용하게 됨으로 인해 props 가 안넘어오는 경우가 있어 필요한 셋팅이다. )

```jsx
import React, { useState } from 'react';
import { withRouter } from 'react-router-dom';
import styled from 'styled-components';

const StyledTable = styled.table`
  border: 1px solid black;
  margin-top: 30px;
  margin-left: 30px;
  border-collapse: collapse;
  width: 300px;
  th {
    border: 1px solid black;
    text-align: center;
    height: 50px;
    background-color: silver;
  }
  td {
    border: 1px solid black;
    text-align: center;
    height: 30px;
  }
  input {
    width: 210px;
  }
  textarea {
    width: 210px;
    height: 100px;
    margin: 5px;
  }
  button {
    margin-left: 5px;
    margin-right: 5px;
  }
`;

function UserDetail ({ user, history, userUpdate, onCreate }) {
  const [userInfo, setUserInfo] = useState(user);
  // 현재 등록으로 사용중인지 수정으로 사용중인지 모드를 통해 셋팅해준다.
  const mode = userInfo.id ? 'EDIT' : 'ADD';  
  const goHome = () => {
    history.push('/users');
  }
  const userInfoUpdate = (e) => {
    setUserInfo({
      ...userInfo,
      [e.target.name]: e.target.value
    });
  }
  // 모드에 따라 수정 또는 등록을 진행한다.
  const actionData = () => {
    if (mode === 'ADD') {
      if (!userInfo.name || !userInfo.english_name || !userInfo.description) {
        window.alert('사용자 정보를 모두 입력해 주십시오.');
        return false;
      }
      
      onCreate(userInfo);

      // 등록시에는 값 초기화를 진행해주어야 한다.
      setUserInfo({
        name: '',
        english_name: '',
        description: ''
      });
    } else {
      userUpdate(userInfo);
    } 
  }
  
  return (
    <>
      <StyledTable>
        <thead>
          <tr>
            <th colSpan="2">
              { mode === 'ADD' ? '사용자추가' : '사용자상세' }
            </th>
          </tr>          
        </thead>
        <tbody>
          <tr>
            <td>이름</td>
            <td>
            <input type="text" name="name" value={userInfo.name} onChange={userInfoUpdate} />
            </td>
          </tr>
          <tr>
            <td>영어이름</td>
            <td>
              <input type="text" name="english_name" value={userInfo.english_name} onChange={userInfoUpdate} />
            </td>
          </tr>
          <tr>
            <td>소개</td>
            <td>
              <textarea name="description" onChange={userInfoUpdate} value={userInfo.description}></textarea>
            </td>
          </tr>
          <tr>
            <td colSpan="2">              
              { mode === 'EDIT' ? <button onClick={goHome}>사용자리스트 바로가기</button> : null }
              <button onClick={actionData}>{mode === 'ADD' ? '사용자 등록' : '수정'}</button>
            </td>
          </tr>
        </tbody>
      </StyledTable>
    </>    
  );
};

UserDetail.defaultProps = {
  user: {
    name: '',
    english_name: '',
    description: ''
  },
  userUpdate: null,
  onCreate: null
}

export default withRouter(UserDetail);
```
# 프로그래밍 상식
> ## 1. 안드로이드 란?
>> __`안드로이드는 구글에서 만든 스마트폰용 운영체제입니다. 운영체제와 미들웨어, 사용자 인터페이스, 어플리케이션, MMS 서비스 등을 하나로 묶어 서비스를 제공하며 다양한 어플리케이션을 만들어 설치하면 실행될 수 있도록 구성된 어플리케이션 플랫폼이라고도 볼 수 있습니다. 많은 사람들이 iOS(애플 운영체제)에 견주어 스마트폰과 태블릿으로 안드로이드 운영체제를 사용하면서, 안드로이드는 세계 모바일 시장에서 가장 성공한 OS라는 평가를 받고있습니다. 안드로이드는 리눅스(Linux)를 기반으로 제작되었고 언어는 자바를 사용합니다.`__<br>
![](https://search.pstatic.net/common/?src=http%3A%2F%2Fblogfiles.naver.net%2F20130504_35%2Fg_m8494_1367629956733Wq5yx_JPEG%2F%25BE%25C8%25B5%25E5%25B7%25CE%25C0%25CC%25B5%25E5.jpg&type=sc960_832)
> ## 2. 안드로이드 명
>> ![](https://github.com/kali1402/-/blob/main/%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C%20%EB%AA%85.PNG?raw=true)<br><br>
> ## 3. HTTP
>> ![](https://search.pstatic.net/common/?src=http%3A%2F%2Fblogfiles.naver.net%2F20150120_18%2Fidea_mind_1421744811721wftA6_PNG%2F012015_0906_HTTP1.png&type=sc960_832)
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
>> ![](https://image.shutterstock.com/image-vector/oop-arrows-concept-vector-illustration-260nw-409775206.jpg)<br>
>> __`객체지향프로그래밍이라는 것은 컴퓨터 프로그래밍의 패러다임 중 하나입니다. 컴퓨터 프로그램을 명령어의 목록으로 보는 시각에서 벗어나 여러 개의 독립된 단위, 즉, "객체" 들의 모임으로 파악하고자 하는 것입니닫. 각각의 개체는 메시지를 주고 받고(Message Passing) 데이터를 처리할 수 있습니다.`__
> ## 5. DDL, DML, DCL, TCL
>> ![](https://github.com/kali1402/-/blob/main/sql.PNG?raw=true)
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
>> ### + 리눅스 명령어
>> ![](https://www.stevenjlee.net/wp-content/uploads/2020/05/isnefnt32wn21-740x889.jpg)
> ## 7. OSI 7계층
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
> ## 8. HTML, CSS는 프로그래밍 언어가 아니다.
>> ### HTML은 프로그래밍 언어가 아니다. Hyper Text Mark up Language, 한마디로 마크업 언어이다(mark up = 표시하다)
>>> __프로그래밍 언어란, 컴퓨터에서 실행 될 프로그램을 만들기 위해 사람의 문자로 만들어 진 수단이다.__<br>
>>> __-파이썬, 자바스크립트, 자바, C언어 등이 대표적이다. 이들은 사람의 생각을 컴퓨터가 연산 처리 할 수 있도록 그 내용을 문자로 전달하는 수단이다.__<br>
>>> __그러나 HTML은 단독으로 프로그램을 만들 수 없다. HTML은 컴퓨터에게 어떤것이 \<Title>인지, \<Body>,\<Main>인지 구분할 수 있게 하는 언어이다. 말 그대로 Mark up(표시)하는 언어이다. HTMl을 보기 좋게 꾸며주는 CSS또한 마찬가지이다.__<br>
>>> __정리하자면, HTML은 컴퓨터에게 구획을 나누어 인식시켜주는 Mark up 언어이고, CSS는 사람이 보기 좋게 디자인을 변경시켜주는 언어이다.__<br>
>> ![](https://miro.medium.com/max/700/0*rCoIWITij3nvAziF.jpg)
