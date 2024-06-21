---
layout: post
title: 메모이제이션
date: 2024-06-20 10:00 +0900
description: 메모이제이션
image: ../assets/img/react10.png
category: React
tags: React 메모이제이션
published: true
sitemap: true
---

# REACT

## 메모이제이션 : memo, useMemo, useCallback

리액트에서 성능 최적화를 위해 메모이제이션을 활용하는 방법은 중요합니다. <br>
메모이제이션이란 컴퓨터 프로그램이 동일한 계산을 반복해야 할 때, 이전에 계산한 값을 메모리에 저장함으로써 동일한 계산의 반복 수행을 제거하여 프로그램 속도를 빠르게 하는 기술입니다. <br>
리액트에서는 memo, useMemo, useCallback 세 가지 주요 메모이제이션 도구를 제공합니다.

<br>

### 💛 memo

리액트의 `memo`는 고차 컴포넌트(Higher Order Component)로, 컴포넌트의 결과를 메모이제이션합니다.<br>
즉, 동일한 props로 컴포넌트가 다시 렌더링되는 것을 방지하여 불필요한 렌더링을 줄입니다.
<br>

예시 :

```javascript
import React, { memo } from "react";

const MyComponent = ({ value }) => {
  console.log("Rendering MyComponent");
  return <div>{value}</div>;
};

export default memo(MyComponent);
```

위 예시에서 MyComponent는 동일한 props가 전달되면 다시 렌더링되지 않습니다. memo를 사용함으로써 컴포넌트의 성능을 최적화할 수 있습니다.

<br>

### 💛 useMemo

`useMemo`는 값의 메모이제이션을 위해 사용됩니다. <br>
복잡한 계산을 수행하는 함수의 결과를 메모이제이션하여 불필요한 재계산을 방지합니다. <br>
첫 번째 인자로 전달된 함수의 반환 값을 메모이제이션하고, 두 번째 인자로 전달된 의존성 배열이 변경될 때만 함수를 다시 실행합니다.

예시 :

```javascript
import React, { useMemo } from "react";

const MyComponent = ({ items }) => {
  const sortedItems = useMemo(() => {
    console.log("Sorting items");
    return items.sort((a, b) => a - b);
  }, [items]);

  return (
    <ul>
      {sortedItems.map((item) => (
        <li key={item}>{item}</li>
      ))}
    </ul>
  );
};
```

위 예시에서 `items`가 변경될 때만 `sortedItems`가 다시 계산됩니다. 이를 통해 불필요한 정렬 작업을 피할 수 있습니다.

<br>

### 💛 useCallback

`useCallback`은 함수의 메모이제이션을 위해 사용됩니다. 첫 번째 인자로 전달된 함수를 메모이제이션하고, 두 번째 인자로 전달된 의존성 배열이 변경될 때만 함수를 다시 생성합니다. 주로 자식 컴포넌트에 콜백 함수를 전달할 때 유용합니다.

```javascript
import React, { useState, useCallback } from "react";

const MyButton = ({ onClick }) => <button onClick={onClick}>Click me</button>;

const MyComponent = () => {
  const [count, setCount] = useState(0);

  const handleClick = useCallback(() => {
    setCount((prevCount) => prevCount + 1);
  }, []);

  return (
    <div>
      <p>Count: {count}</p>
      <MyButton onClick={handleClick} />
    </div>
  );
};
```

위 예시에서 handleClick 함수는 count 상태가 변경될 때만 새로 생성됩니다. 이를 통해 MyButton 컴포넌트가 불필요하게 다시 렌더링되는 것을 방지할 수 있습니다.

## 결론

리액트에서 메모이제이션을 활용하면 불필요한 렌더링과 계산을 줄여 성능을 최적화할 수 있습니다. <br> memo는 컴포넌트 자체를 메모이제이션하고, useMemo는 값의 계산 결과를 메모이제이션하며, useCallback은 함수를 메모이제이션합니다. <br>
각 도구를 적절히 사용하여 효율적인 리액트 애플리케이션을 개발할 수 있습니다.
