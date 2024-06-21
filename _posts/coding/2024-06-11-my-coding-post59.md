---
layout: post
title: React - 함수형 vs 클래스형 컴포넌트
date: 2024-06-11 10:00 +0900
description: React - 함수형 vs 클래스형 컴포넌트
image: ../assets/img/react05.png
category: React
tags: React
published: true
sitemap: true
---

# REACT

## 🍳 함수형 vs 클래스형 컴포넌트

이번 시간에는 함수형 컴포넌트와 클래스형 컴포넌트에 대해 설명하겠습니다. <br>

리액트(React)에서 `컴포넌트`는 사용자 인터페이스를 구성하는 기본 단위입니다. <br>
컴포넌트는 크게 두 가지 유형으로 나눌 수 있습니다. 함수형 컴포넌트와 클래스형 컴포넌트. <Br>
이 두 가지 유형의 컴포넌트는 기능적으로 비슷하지만, 작성 방법과 사용하는 기능에서 차이가 있습니다. <br>
이 글에서는 함수형 컴포넌트와 클래스형 컴포넌트의 차이점과 각각의 장단점을 살펴보겠습니다.

### 💛 함수형 컴포넌트

함수형 컴포넌트는 함수 기반으로 작성된 컴포넌트입니다. <br>
코드가 짧고 직관적이며, 현재 대부분의 리액트 개발자들이 함수형 컴포넌트를 선호하고 있습니다.
<br>

- 간결한 코드: 함수형 컴포넌트는 단순한 자바스크립트 함수를 사용하여 작성됩니다. 코드가 짧고 간결하여 가독성이 높습니다.
- Hooks 사용: 함수형 컴포넌트는 리액트 훅(Hooks)을 사용하여 상태(state)와 생명 주기(lifecycle) 기능을 구현할 수 있습니다. 이는 클래스형 컴포넌트에서 사용되던 복잡한 문법을 대체합니다.
- 성능: 함수형 컴포넌트는 클래스형 컴포넌트에 비해 메모리 사용량이 적고, 렌더링 성능이 더 우수한 경우가 많습니다.

```javascript
import React, { useState, useEffect } from "react";

function MyComponent() {
  const [count, setCount] = useState(0);

  useEffect(() => {
    document.title = `Count: ${count}`;
  }, [count]);

  return (
    <div>
      <p>{count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}
```

### 💛 클래스형 컴포넌트

클래스형 컴포넌트는 리액트의 초기 버전에서 주로 사용되던 방식으로, ES6 클래스 문법을 사용하여 작성됩니다. <br>
함수형 컴포넌트의 등장 이후로는 덜 사용되지만, 여전히 이해하고 있는 것이 중요합니다.
<br>

- 명시적인 구조: 클래스형 컴포넌트는 명시적인 구조를 가지고 있어, 상태와 생명 주기 메서드를 직관적으로 사용할 수 있습니다.
- 상태와 생명 주기: 클래스형 컴포넌트에서는 state 객체와 다양한 생명 주기 메서드(`componentDidMount`, `componentDidUpdate`, `componentWillUnmount`)를 통해 상태와 컴포넌트의 생명 주기를 관리할 수 있습니다.

```javascript
import React, { Component } from "react";

class MyComponent extends Component {
  constructor(props) {
    super(props);
    this.state = {
      count: 0,
    };
  }

  componentDidMount() {
    document.title = `Count: ${this.state.count}`;
  }

  componentDidUpdate() {
    document.title = `Count: ${this.state.count}`;
  }

  incrementCount = () => {
    this.setState({ count: this.state.count + 1 });
  };

  render() {
    return (
      <div>
        <p>{this.state.count}</p>
        <button onClick={this.incrementCount}>Increment</button>
      </div>
    );
  }
}
```

### 주요 차이점

##### 1. 작성 방식

- 함수형 컴포넌트: 단순한 함수로 작성.
- 클래스형 컴포넌트: ES6 클래스 문법으로 작성.

<br>

##### 2. 작성 방식

- 함수형 컴포넌트: useState 훅을 사용하여 상태 관리.
- 클래스형 컴포넌트: state 객체와 setState 메서드를 사용하여 상태 관리.

<br>

#### 3. 생명 주기 관리

- 함수형 컴포넌트: useEffect 훅을 사용하여 생명 주기 관리.
- 클래스형 컴포넌트: 다양한 생명 주기 메서드를 사용하여 생명 주기 관리.

### 결론 💞

함수형 컴포넌트와 클래스형 컴포넌트는 각각의 장단점이 있지만, 현대 리액트 개발에서는 `함수형 컴포넌트` 가 더 많이 사용됩니다. <br>
함수형 컴포넌트는 코드가 간결하고 가독성이 높으며, 리액트 훅을 통해 강력한 기능을 제공하기 때문입니다. <br>
클래스형 컴포넌트는 여전히 이해하고 있어야 하지만, 새로운 프로젝트나 코드베이스에서는 함수형 컴포넌트를 사용하는 것이 권장됩니다.<br>

<br>

이 글을 통해 함수형 컴포넌트와 클래스형 컴포넌트의 차이점과 각각의 특징을 이해할 수 있었기를 바랍니다. 두 가지 방식 모두 리액트의 강력한 도구이며, 상황에 따라 적절히 선택하여 사용할 수 있습니다.
