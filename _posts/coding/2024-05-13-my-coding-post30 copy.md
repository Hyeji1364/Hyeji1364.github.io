---
layout: post
title: 반응형 웹디자인
date: 2024-05-21 10:00 +0900
description: 리액트 훅
image: ../assets/img/blogcss.gif
category: coding
tags: React
published: true
sitemap: true
---

## React
오늘은 리액트 훅에 대해 알아보는 시간을 가지겠습니다.

### React hook
리액트 훅(React Hooks)은 함수형 컴포넌트에서 상태와 생명주기 기능을 사용할 수 있게 해주는 기능입니다. <br>
React 16.8 버전에서 도입되었으며, 클래스형 컴포넌트에서 제공하던 기능을 함수형 컴포넌트에서도 손쉽게 사용할 수 있도록 해줍니다.<br>

### 주요 리액트 훅

01. useState
- 상태를 선언하고 관리할 수 있게 해주는 훅입니다.
- 상태값과 상태를 갱신하는 함수를 반환합니다.

````jsx
import React, { useState } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}
````

02. useEffect
- 사이드 이펙트를 처리하는 훅입니다. 데이터 가져오기, 구독 설정, DOM 업데이트 등 여러 작업을 수행할 수 있습니다.
- 컴포넌트가 렌더링될 때마다 실행됩니다. 의존성 배열을 통해 실행 조건을 제어할 수 있습니다.

````jsx
mport React, { useEffect, useState } from 'react';

function Example() {
  const [count, setCount] = useState(0);

  useEffect(() => {
    document.title = `You clicked ${count} times`;
  }, [count]); // count가 변경될 때만 effect를 실행

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}
````

03. useContext
- React Context API를 쉽게 사용할 수 있게 해주는 훅입니다.
- context를 구독하고, context의 현재 값을 반환합니다.

````jsx
import React, { useContext } from 'react';

const MyContext = React.createContext();

function MyComponent() {
  const value = useContext(MyContext);

  return <div>{value}</div>;
}
````

04. useReducer
- useState의 대체 훅으로, 복잡한 상태 로직을 관리할 때 유용합니다.
- reducer 함수를 통해 상태 업데이트 로직을 캡슐화합니다.

````jsx
import React, { useReducer } from 'react';

const initialState = { count: 0 };

function reducer(state, action) {
  switch (action.type) {
    case 'increment':
      return { count: state.count + 1 };
    case 'decrement':
      return { count: state.count - 1 };
    default:
      throw new Error();
  }
}

function Counter() {
  const [state, dispatch] = useReducer(reducer, initialState);

  return (
    <div>
      <p>Count: {state.count}</p>
      <button onClick={() => dispatch({ type: 'increment' })}>+</button>
      <button onClick={() => dispatch({ type: 'decrement' })}>-</button>
    </div>
  );
}
````
05. useRef

- DOM 요소나 컴포넌트 인스턴스에 접근할 수 있게 해주는 훅입니다.
- 렌더링 간에 유지되는 변경 가능한 값을 관리할 때도 사용됩니다.

````jsx
import React, { useRef, useEffect } from 'react';

function TextInputWithFocusButton() {
  const inputEl = useRef(null);

  const onButtonClick = () => {
    inputEl.current.focus();
  };

  return (
    <div>
      <input ref={inputEl} type="text" />
      <button onClick={onButtonClick}>Focus the input</button>
    </div>
  );
}
````

06. 기타 훅
- useMemo: 성능 최적화를 위해 메모이제이션된 값을 반환합니다.
- useCallback: 성능 최적화를 위해 메모이제이션된 콜백 함수를 반환합니다.
- useLayoutEffect: DOM이 그려진 직후에 동기적으로 실행되는 훅입니다.
- useDebugValue: 커스텀 훅을 디버깅할 때 유용한 값을 설정할 수 있습니다.

07. 커스텀 훅
- 리액트 훅을 조합하여 커스텀 훅을 만들 수 있습니다. 이를 통해 코드의 재사용성을 높이고 로직을 분리할 수 있습니다.

````jsx
import { useState, useEffect } from 'react';

function useFetch(url) {
  const [data, setData] = useState(null);
  const [loading, setLoading] = useState(true);

  useEffect(() => {
    fetch(url)
      .then((response) => response.json())
      .then((data) => {
        setData(data);
        setLoading(false);
      });
  }, [url]);

  return { data, loading };
}

// 사용 예시
function App() {
  const { data, loading } = useFetch('https://api.example.com/data');

  if (loading) return <div>Loading...</div>;

  return (
    <div>
      <pre>{JSON.stringify(data, null, 2)}</pre>
    </div>
  );
}
````
리액트 훅은 함수형 컴포넌트에서 상태와 생명주기 메서드를 사용하기 쉽게 만들어주며, 코드의 가독성과 유지보수성을 높여줍니다!😀



