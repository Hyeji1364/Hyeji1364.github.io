---
layout: post
title: state vs props
date: 2024-06-19 10:00 +0900
description: React의 state와 props
image: ../assets/img/react10.png
category: React
tags: React state props
published: true
sitemap: true
---

# REACT

## state와 props

리액트(React)에서 state와 props는 컴포넌트의 렌더링 결과물에 영향을 주는 두 가지 중요한 개념입니다. <br>
이 두 객체는 리액트 애플리케이션에서 데이터 흐름을 관리하고, 컴포넌트 간의 상호작용을 정의하는 데 사용됩니다. <br>
이번 글에서는 state와 props의 차이점과 사용 방법에 대해 알아보겠습니다.

<br>

### 💛 Props: 부모 컴포넌트에서 자식 컴포넌트로 전달되는 값

`props`는 부모 컴포넌트에서 자식 컴포넌트로 값을 전달할 때 사용됩니다. <br>
마치 함수의 매개변수처럼, props는 컴포넌트에 데이터를 전달하는 역할을 합니다. <br>
이를 통해 부모 컴포넌트는 자식 컴포넌트에 필요한 데이터를 전달하고, 자식 컴포넌트는 이를 받아서 화면에 렌더링할 수 있습니다.
<br>

예시 :

```javascript
import React from "react";

function ChildComponent(props) {
  return <p>{props.message}</p>;
}

function ParentComponent() {
  return <ChildComponent message="Hello, World!" />;
}
```

위 예제에서, ParentComponent는 ChildComponent에 message라는 props를 전달합니다. ChildComponent는 props.message를 받아서 화면에 "Hello, World!"라는 문구를 렌더링합니다.

<br>

#### 주요 특징

- props는 읽기 전용입니다. 자식 컴포넌트는 전달받은 props를 변경할 수 없습니다.
- 부모 컴포넌트는 자식 컴포넌트에 여러 개의 props를 전달할 수 있습니다.
- props를 통해 컴포넌트 간에 데이터가 전달됩니다.

<br>

### 💛 State: 컴포넌트 내에서 관리되는 변경 가능한 데이터

`state`는 컴포넌트 내에서만 값이 이동하는 변경 가능한 데이터입니다.<br>
마치 함수 내에 선언된 변수처럼, state는 컴포넌트 내부에서 관리되고, 해당 컴포넌트의 상태를 나타냅니다. <br>
state가 변경되면, 리액트는 자동으로 해당 컴포넌트를 다시 렌더링하여 변경된 내용을 반영합니다.

<br>

예시 :

```javascript
import React, { useState } from "react";

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}
```

위 예제에서, `Counter` 컴포넌트는 `count`라는 state를 가지고 있으며, `setCount` 함수를 통해 count를 변경할 수 있습니다. <br>
버튼을 클릭하면 count가 증가하고, 컴포넌트는 새로운 count 값을 반영하여 다시 렌더링됩니다.

<br>

#### 주요 특징

- state는 컴포넌트 내에서만 관리됩니다.
- state는 변경 가능하며, 변경될 때마다 컴포넌트가 다시 렌더링됩니다.
- state는 주로 사용자 입력이나 네트워크 요청 등의 동적 데이터를 관리하는 데 사용됩니다.

<br>

### Props와 State의 차이점

#### 1. 데이터 흐픔

- props: 부모 컴포넌트에서 자식 컴포넌트로 데이터가 전달됩니다.
- state: 컴포넌트 내에서만 데이터가 이동합니다.

#### 2. 변경 가능성

- props: 읽기 전용으로, 자식 컴포넌트에서 변경할 수 없습니다.
- state: 변경 가능하며, 컴포넌트 내에서 자유롭게 업데이트할 수 있습니다.

#### 3. 역할

- props: 컴포넌트 간에 데이터를 전달하고, 상호작용을 정의합니다.
- state: 컴포넌트의 동적 데이터를 관리하고, 사용자 인터페이스의 변화를 처리합니다.

<br>

### 결론

리액트에서 state와 props는 컴포넌트의 렌더링 결과물에 영향을 주는 중요한 개념입니다. <br>
props는 부모 컴포넌트에서 자식 컴포넌트로 데이터를 전달하는 역할을 하며, state는 컴포넌트 내에서 관리되는 변경 가능한 데이터를 나타냅니다. <br>
이 두 개념을 잘 이해하고 활용하면, 리액트 애플리케이션의 데이터 흐름을 효과적으로 관리하고, 사용자 인터페이스를 동적으로 업데이트할 수 있습니다. <br>
리액트의 강력한 기능을 최대한 활용하기 위해서는 state와 props의 차이점을 명확히 이해하고, 적절히 사용하는 것이 중요합니다.
