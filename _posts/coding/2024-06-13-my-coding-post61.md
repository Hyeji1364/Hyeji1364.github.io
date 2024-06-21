---
layout: post
title: useEffect / useLayoutEffect의 차이점
date: 2024-06-13 10:00 +0900
description: useEffect / useLayoutEffect의 차이점
image: ../assets/img/react06.png
category: React
tags: React useEffect useLayoutEffect
published: true
sitemap: true
---

# REACT

## 🍳 useEffect / useLayoutEffect의 차이점

리액트(React)에서 컴포넌트의 생명 주기 동안 특정 작업을 수행하기 위해 사용하는 두 가지 주요 훅이 있습니다.<br>
useEffect와 useLayoutEffect. 이 두 훅은 비슷한 역할을 하지만, 실행 타이밍과 방식에서 중요한 차이점이 있습니다. <br>
이 글에서는 useEffect와 useLayoutEffect의 차이점과 각각의 사용 사례에 대해 알아보겠습니다.<br>
이번 시간에는 리액트의 useEffect와 useLayoutEffect 차이점에 대해 알아보겠습니다.

### 💫 useEffect

`useEffect`는 비동기적으로 실행되며, 컴포넌트가 렌더링된 후에 실행됩니다.<br>
즉, 리액트가 컴포넌트의 UI를 업데이트하고 브라우저가 화면을 다시 그린 후에 useEffect 내부의 코드가 실행됩니다. <br>
이는 주로 데이터 가져오기, 구독 설정, 로그 기록 등 비동기 작업을 처리하는 데 사용됩니다.

```javascript
import React, { useState, useEffect } from "react";

function ExampleComponent() {
  const [data, setData] = useState(null);

  useEffect(() => {
    fetch("https://api.example.com/data")
      .then((response) => response.json())
      .then((data) => setData(data));
  }, []);

  return (
    <div>
      <p>{data ? JSON.stringify(data) : "Loading..."}</p>
    </div>
  );
}
```

위 예제에서 useEffect는 컴포넌트가 렌더링된 후 데이터를 가져오는 작업을 수행합니다. <br>
이는 UI가 초기 렌더링된 후에 비동기적으로 실행되므로, 화면에 깜빡임이 발생할 수 있습니다.
<br>

### 💫 useLayoutEffect

`useLayoutEffect`는 동기적으로 실행되며, 컴포넌트가 렌더링된 직후, 브라우저가 화면을 그리기 전에 실행됩니다. <br>
이 훅은 주로 DOM 조작이 필요하거나, 화면에 렌더링되기 전에 완료해야 하는 작업에 사용됩니다.<br>
useLayoutEffect는 컴포넌트가 렌더링된 후 곧바로 실행되므로, DOM 조작을 포함한 코드가 화면에 깜빡임 없이 적용됩니다.

```javascript
import React, { useState, useLayoutEffect, useRef } from "react";

function ExampleComponent() {
  const [width, setWidth] = useState(0);
  const divRef = useRef();

  useLayoutEffect(() => {
    const divWidth = divRef.current.offsetWidth;
    setWidth(divWidth);
  }, []);

  return (
    <div ref={divRef}>
      <p>Width: {width}px</p>
    </div>
  );
}
```

위 예제에서 `useLayoutEffect`는 컴포넌트가 렌더링된 후, 브라우저가 화면을 그리기 전에 div 요소의 너비를 측정하여 상태를 업데이트합니다. <br>
이 경우, 화면이 깜빡이는 현상이 발생하지 않습니다.

### 주요 차이점

##### 1. 실행 타이밍

- useEffect: 비동기적으로 실행되며, 컴포넌트가 렌더링되고 브라우저가 화면을 그린 후 실행됩니다.
- useLayoutEffect: 동기적으로 실행되며, 컴포넌트가 렌더링된 직후, 브라우저가 화면을 그리기 전에 실행됩니다.
  <br>

##### 2. 사용 목적

- useEffect: 비동기 작업, 데이터 가져오기, 구독 설정, 로그 기록 등 화면이 그려진 후에 실행해야 하는 작업에 적합합니다.
- useLayoutEffect: DOM 조작, 측정 작업 등 화면이 그려지기 전에 완료해야 하는 작업에 적합합니다.
  <br>

##### 3. 화면 깜빡임

- useEffect: DOM 조작 코드가 포함된 경우, 화면에 깜빡임이 발생할 수 있습니다.
- useLayoutEffect: DOM 조작 코드가 포함되어도 화면에 깜빡임이 발생하지 않습니다.

<br>

### 사용 시 주의사항

- 성능 고려: useLayoutEffect는 동기적으로 실행되므로, 렌더링 성능에 영향을 미칠 수 있습니다. 따라서, 실제로 필요한 경우에만 사용해야 합니다.
- 비동기 작업: 비동기 작업이나 브라우저가 그린 후에 실행해야 하는 작업은 useEffect를 사용하는 것이 좋습니다.
- 동기 작업: DOM 측정이나 조작과 같은 동기 작업은 useLayoutEffect를 사용하는 것이 적합합니다.

<br>

## 결론 ✨

`useEffect`와 `useLayoutEffect`는 리액트에서 컴포넌트의 생명 주기 동안 특정 작업을 수행하기 위한 강력한 도구입니다. <br>
이 두 훅은 실행 타이밍과 방식에서 차이가 있으며, 각각의 사용 목적에 따라 적절히 선택하여 사용해야 합니다. <br>
useEffect는 비동기 작업에, useLayoutEffect는 동기 작업에 적합합니다.<br>
이러한 차이점을 이해하고 올바르게 활용하면, 리액트 애플리케이션의 성능과 사용자 경험을 크게 향상시킬 수 있습니다.
