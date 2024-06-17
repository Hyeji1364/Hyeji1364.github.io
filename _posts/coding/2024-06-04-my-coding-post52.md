---
layout: post
title: Javascript Property
date: 2024-06-04 10:00 +0900
description: Javascript Property
image: ../assets/img/javascript16.png
category: Javascript
tags: Javascript 프로퍼티
published: true
sitemap: true
---

# Javascript

## 🍳 자바스크립트의 프로퍼티

자바스크립트에서 프로퍼티는 객체(Object)를 구성하는 기본 요소로, "키(key)"와 "값(value)"의 쌍으로 이루어져 있습니다. <br>
객체는 다양한 속성(프로퍼티)을 가질 수 있으며, 각 속성은 객체의 상태와 행동을 정의합니다. <br>

### 🍳 프로퍼티의 기본 개념

자바스크립트 객체는 여러 프로퍼티로 구성됩니다. <br>
프로퍼티는 "key": "value" 형식으로 작성되며, 여러 프로퍼티는 콤마(쉼표, ,)로 구분됩니다. <br>
예를 들어, 다음은 세 개의 프로퍼티를 가진 person 객체입니다

```javascript
const person = {
  name: "John",
  age: 30,
  city: "New York",
};
```

위 예제에서 person 객체는 name, age, city라는 세 개의 프로퍼티를 가지고 있습니다. <br>
각 프로퍼티는 키와 값으로 구성되며, 키는 문자열이고 값은 문자열, 숫자, 객체 등 다양한 데이터 타입이 될 수 있습니다.
<br>

### 데이터 프로퍼티와 접근자 프로퍼티

자바스크립트의 프로퍼티는 크게 두 가지 유형으로 나눌 수 있습니다.데이터 프로퍼티와 접근자 프로퍼티입니다.

<br>

#### 데이터 프로퍼티

데이터 프로퍼티는 값을 가지고 있으며, 기본적인 키-값 쌍의 형태로 저장됩니다. 데이터 프로퍼티는 다음과 같은 속성을 가질 수 있습니다.

- value: 프로퍼티의 값입니다. 기본값은 `undefined`입니다.
- writable: 프로퍼티의 값을 변경할 수 있는지 여부를 나타냅니다. 기본값은 `true`입니다.
- enumerable: 프로퍼티가 열거 가능한지 여부를 나타냅니다. 기본값은 `true`입니다.
- configurable: 프로퍼티의 정의를 변경하거나 삭제할 수 있는지 여부를 나타냅니다. 기본값은 `true`입니다.
  <br>

예를 들어, Object.defineProperty 메서드를 사용하여 person 객체의 name 프로퍼티를 정의할 수 있습니다.

```javascript
Object.defineProperty(person, "name", {
  value: "John",
  writable: false,
  enumerable: true,
  configurable: true,
});
```

#### 접근자 프로퍼티

접근자 프로퍼티는 값을 저장하지 않으며, 대신 값을 가져오거나 설정할 때 호출되는 함수로 구성됩니다. 접근자 프로퍼티는 다음과 같은 속성을 가질 수 있습니다.

- get: 값을 가져올 때 호출되는 함수입니다.
- set: 값을 설정할 때 호출되는 함수입니다.
- enumerable: 프로퍼티가 열거 가능한지 여부를 나타냅니다.
- configurable: 프로퍼티의 정의를 변경하거나 삭제할 수 있는지 여부를 나타냅니다.
  예를 들어, age 프로퍼티에 접근자 프로퍼티를 사용할 수 있습니다.

```javascript
const person = {
  _age: 30,

  get age() {
    return this._age;
  },

  set age(value) {
    if (value > 0) {
      this._age = value;
    } else {
      console.log("Invalid age");
    }
  },
};
```

### 프로퍼티 조작

자바스크립트에서는 Object.defineProperty 메서드를 사용하여 프로퍼티를 정의하거나 수정할 수 있습니다.<br>
이를 통해 프로퍼티의 속성을 세밀하게 제어할 수 있습니다. 예를 들어, 다음과 같이 name 프로퍼티를 읽기 전용으로 설정할 수 있습니다.
<br>

```javascript
Object.defineProperty(person, "name", {
  value: "Alice",
  writable: false,
  enumerable: true,
  configurable: false,
});
```

### 결론

자바스크립트의 프로퍼티는 객체를 구성하는 기본 요소로, 객체의 상태와 행동을 정의하는 중요한 역할을 합니다. 프로퍼티는 "키: 값" 형식으로 작성되며, 데이터 프로퍼티와 접근자 프로퍼티로 나눌 수 있습니다. Object.defineProperty 메서드를 사용하여 프로퍼티의 속성을 세밀하게 제어할 수 있습니다. 이를 통해 객체의 구조를 유연하게 정의하고 조작할 수 있습니다.
