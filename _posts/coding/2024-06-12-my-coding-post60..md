---
layout: post
title: React - side-Effect, useEffect, useState
date: 2024-06-12 10:00 +0900
description: React - side-Effect, useEffect, useState
image: ../assets/img/react01.png
category: React
tags: React
published: true
sitemap: true
---

# REACT

## 🍳 React - side-Effect, useEffect, useState

이번 시간에는 리액트의 Side-Effect, useEffect, useState에 대해 알아보겠습니다.

### 💫 Side-Effect

Side-Effect(부수 효과)는 함수가 실행되면서 함수 외부에 존재하는 값이나 상태를 변경시키는 행위를 말합니다. <br>
예를 들어, 데이터 가져오기, DOM 조작, 로깅, 타이머 설정 등이 이에 해당합니다. <br>
이러한 부수 효과는 애플리케이션의 일관성을 유지하고 버그를 방지하기 위해 주의 깊게 관리해야 합니다. <br>
리액트에서는 부수 효과 처리를 위해 `useEffect` 훅을 제공합니다.

<br>

### useEffect

`useEffect`는 함수형 컴포넌트에서 부수 효과를 수행하기 위해 사용하는 훅입니다. <br>
useEffect는 컴포넌트가 렌더링될 때마다 특정 작업을 실행하도록 설정할 수 있습니다. <br>
이는 클래스형 컴포넌트의 생명 주기 메서드(`componentDidMount`, `componentDidUpdate`, `componentWillUnmount`)와 유사한 역할을 합니다.

```javascript
import React, { useState, useEffect } from "react";

function Timer() {
  const [count, setCount] = useState(0);

  useEffect(() => {
    const timer = setInterval(() => {
      setCount((prevCount) => prevCount + 1);
    }, 1000);

    // Cleanup function to clear the interval
    return () => clearInterval(timer);
  }, []);

  return (
    <div>
      <p>{count} seconds have passed.</p>
    </div>
  );
}
```

위 예제에서 useEffect는 컴포넌트가 마운트될 때마다 1초마다 count를 증가시키는 타이머를 설정합니다. <br>
두 번째 인자인 빈 배열 []은 이 효과가 한 번만 실행되고, 컴포넌트가 언마운트될 때 정리되도록 합니다. <br>
이는 타이머를 정리하고 메모리 누수를 방지합니다.

<br>

### useState

`useState`는 함수형 컴포넌트에서 상태(state)를 관리하게 해주는 훅입니다. <br>
컴포넌트 내부에서 상태를 선언하고, 그 상태를 업데이트할 수 있는 함수를 반환합니다. <br>
이를 통해 상태가 변경될 때마다 컴포넌트가 다시 렌더링되도록 할 수 있습니다.

```javascript
import React, { useState } from "react";

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>{count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}
```

위 예제에서 useState(0)는 count라는 상태 변수와 setCount라는 상태를 업데이트하는 함수를 반환합니다.<br>
버튼을 클릭할 때마다 setCount를 호출하여 count를 증가시키고, 이에 따라 컴포넌트가 다시 렌더링됩니다.

<br>

### useState와 useEffect의 결합

`useState`와 `useEffect`를 결합하면 컴포넌트의 상태와 부수 효과를 손쉽게 관리할 수 있습니다. <br>
이는 컴포넌트가 렌더링될 때마다 원하는 작업을 수행하고, 상태 변화에 따라 적절한 업데이트를 할 수 있게 합니다.

```javascript
import React, { useState, useEffect } from "react";

function DataFetcher() {
  const [data, setData] = useState(null);
  const [loading, setLoading] = useState(true);

  useEffect(() => {
    fetch("https://api.example.com/data")
      .then((response) => response.json())
      .then((data) => {
        setData(data);
        setLoading(false);
      });
  }, []);

  if (loading) {
    return <div>Loading...</div>;
  }

  return (
    <div>
      <pre>{JSON.stringify(data, null, 2)}</pre>
    </div>
  );
}
```

이 예제는 데이터 가져오기 작업을 수행하는 컴포넌트를 보여줍니다. useEffect는 컴포넌트가 마운트될 때 데이터를 가져오고, 이를 data 상태에 저장합니다. 데이터를 가져오는 동안 loading 상태를 true로 설정하여 로딩 메시지를 표시합니다. 데이터가 로드되면 loading을 false로 설정하고 데이터를 화면에 표시합니다.

<br>

### 결론 ✨

리액트의 `useState`와 `useEffect` 훅은 함수형 컴포넌트에서 상태와 부수 효과를 관리하는 강력한 도구입니다. <br>
useState는 상태 관리를 간단하게 만들고, useEffect는 컴포넌트의 생명 주기 동안 특정 작업을 수행할 수 있게 합니다. <br>
이 두 훅을 적절히 결합하면 복잡한 애플리케이션에서도 상태와 부수 효과를 효율적으로 관리할 수 있습니다.
