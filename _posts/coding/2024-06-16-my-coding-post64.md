---
layout: post
title: 리액트의 생명 주기 함수와 생명 주기 메서드
date: 2024-06-15 10:00 +0900
description: SPA와 Router
image: ../assets/img/react08.png
category: React
tags: React SPA Router
published: true
sitemap: true
---

# REACT

## 생명 주기 함수와 생명주기 메서드

이번시간에는 생명 주기 함수(LifeCycle)와 생명주기 메서드에 대해 알아보겠습니다.

리액트(React)에서 컴포넌트는 생성부터 소멸까지 일련의 과정을 거치게 됩니다. <br>
이를 컴포넌트의 생명 주기(LifeCycle)라고 합니다. <br>
컴포넌트는 생명 주기마다 특정 함수를 가지고 있으며, 이를 생명주기 메서드라고 부릅니다. <br>
이러한 메서드를 사용하면 컴포넌트의 특정 시점에 원하는 동작을 실행할 수 있습니다.<br>
이번 글에서는 리액트 컴포넌트의 생명 주기와 각 단계에서 사용되는 주요 메서드들에 대해 알아보겠습니다.

<br>

### 생명주기 메서드란 ❔

생명주기 메서드는 컴포넌트가 브라우저에 나타나고, 업데이트되며, 사라질 때 호출되는 함수들입니다. <br>
컴포넌트의 생명 주기는 크게 세 단계로 나눌 수 있습니다. <br>
생성, 업데이트, 소멸. 각 단계마다 호출되는 메서드들이 있으며, 이 메서드들을 사용하여 특정 시점에 원하는 작업을 수행할 수 있습니다.

<br>

### 1. 생성 단계

생성 단계는 컴포넌트가 처음으로 인스턴스화되고, DOM에 삽입되기 전후의 과정을 포함합니다. <br>
이 단계에서는 다음과 같은 메서드들이 호출됩니다.

##### constructor(props)

- 컴포넌트의 초기 상태를 설정하고, 필요한 초기화를 수행합니다.
- this.state를 초기화하거나 인스턴스 변수들을 설정할 수 있습니다.

<br>

##### getDerivedStateFromProps(props, state)

- props로부터 상태를 갱신할 필요가 있을 때 호출됩니다.
- 정적 메서드로, 인스턴스의 this에 접근할 수 없습니다.
  <br>

##### render()

- 컴포넌트의 UI를 렌더링합니다.
- 이 메서드는 순수 함수처럼 동작하며, 부작용(side effects)을 일으키지 않아야 합니다.
  <br>

##### componentDidMount()

- 컴포넌트가 처음 DOM에 삽입된 직후에 호출됩니다.
- 이 메서드에서 네트워크 요청이나 DOM 조작 등의 작업을 수행할 수 있습니다.

<br>

### 2. 업데이트 단계

업데이트 단계는 컴포넌트의 props나 state가 변경되어 리렌더링이 필요할 때 발생합니다. 이 단계에서는 다음과 같은 메서드들이 호출됩니다.

##### 2-1. getDerivedStateFromProps(props, state)

생성 단계에서와 마찬가지로, props로부터 상태를 갱신할 필요가 있을 때 호출됩니다.

##### 2-2. shouldComponentUpdate(nextProps, nextState)

- 컴포넌트가 리렌더링할지 여부를 결정합니다.
- 기본적으로 true를 반환하며, 성능 최적화를 위해 필요한 경우에만 사용합니다.

##### 2-3. render()

컴포넌트의 UI를 다시 렌더링합니다.

##### 2-4. getSnapshotBeforeUpdate(prevProps, prevState)

- DOM이 업데이트되기 직전에 호출됩니다.
- 이 메서드에서 반환된 값은 componentDidUpdate에서 세 번째 인자로 전달됩니다.

##### 2-5. componentDidUpdate(prevProps, prevState, snapshot)

- 컴포넌트의 업데이트가 완료된 후에 호출됩니다.
- 이전 props와 상태, 그리고 getSnapshotBeforeUpdate에서 반환된 값을 사용할 수 있습니다.

<br>

### 3. 소멸 단계

소멸 단계는 컴포넌트가 DOM에서 제거될 때 발생합니다. 이 단계에서는 다음과 같은 메서드가 호출됩니다.

##### 3-1. componentWillUnmount()

- 컴포넌트가 DOM에서 제거되기 직전에 호출됩니다.
- 이 메서드에서 타이머를 정리하거나, 네트워크 요청을 취소하는 등의 정리 작업을 수행할 수 있습니다.

<br>

### 생명 주기 메서드의 예시 🍳

다음은 리액트 클래스형 컴포넌트에서 생명 주기 메서드를 사용하는 예시입니다.

```javascript
import React, { Component } from "react";

class MyComponent extends Component {
  constructor(props) {
    super(props);
    this.state = {
      data: null,
    };
    console.log("constructor");
  }

  static getDerivedStateFromProps(nextProps, prevState) {
    console.log("getDerivedStateFromProps");
    return null;
  }

  componentDidMount() {
    console.log("componentDidMount");
    // 데이터 가져오기 등의 작업을 수행
    this.setState({ data: "Fetched Data" });
  }

  shouldComponentUpdate(nextProps, nextState) {
    console.log("shouldComponentUpdate");
    return true;
  }

  getSnapshotBeforeUpdate(prevProps, prevState) {
    console.log("getSnapshotBeforeUpdate");
    return null;
  }

  componentDidUpdate(prevProps, prevState, snapshot) {
    console.log("componentDidUpdate");
  }

  componentWillUnmount() {
    console.log("componentWillUnmount");
    // 타이머 정리 등
  }

  render() {
    console.log("render");
    return <div>{this.state.data ? this.state.data : "Loading..."}</div>;
  }
}

export default MyComponent;
```

## 결론 🍸

리액트의 생명 주기 메서드는 컴포넌트가 생성, 업데이트, 소멸되는 과정에서 특정 작업을 수행할 수 있게 해줍니다. <br>
이를 통해 컴포넌트의 다양한 시점에서 필요한 작업을 효율적으로 관리할 수 있습니다.<br<
생명 주기 메서드를 잘 이해하고 활용하면, 더욱 안정적이고 유지보수하기 쉬운 리액트 애플리케이션을 개발할 수 있습니다.
