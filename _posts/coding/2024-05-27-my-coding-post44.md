---
layout: post
title: Javascript this
date: 2024-05-27 10:00 +0900
description: Javascript this
image: ../assets/img/javascript10.png
category: Javascript
tags: Javascript This
published: true
sitemap: true
---

# JAVASCRIPT

## This

오늘은 자바스크립트의 this에 대해 알아보겠습니다.
자바스크립트에서 `this` 키워드는 코드가 실행되는 문맥(context)에 따라 달라지는 특별한 키워드입니다.<br>
this의 값은 함수가 호출되는 방식에 따라 결정됩니다.<br>
this는 여러 상황에서 다른 값을 가질 수 있기 때문에 자바스크립트의 중요한 개념 중 하나입니다.
다음은 this가 어떻게 동작하는지에 대한 시나리오입니다.

### 01. 전역 컨텍스트(Global Context)
전역 실행 문맥에서 this는 전역 객체를 참조합니다.<br>
브라우저 환경에서는 전역 객체가 window입니다.

````javascript
console.log(this); // 브라우저에서는 window 객체를 출력
````
<br>

### 02. 함수 컨텍스트(Function Context)
기본 함수 호출에서 this는 전역 객체를 참조합니다.<br>
하지만 엄격 모드('use strict')에서는 undefined를 참조합니다.

````javascript
function showThis() {
  console.log(this);
}

showThis(); // 브라우저에서는 window 객체를 출력

// 'use strict' 모드
function showThisStrict() {
  'use strict';
  console.log(this);
}

showThisStrict(); // undefined 출력
````
<br>

### 03. 메서드 컨텍스트(Method Context)
객체의 메서드 안에서 쓸 경우 this는 해당 메서드를 소유하는 객체로 바인딩 되어 메소드를 소유하고 있는 객체를 가리킵니다.

````javascript
const obj = {
  value: 42,
  showThis: function() {
    console.log(this);
  }
};

obj.showThis(); // obj 객체를 출력
````
<br>

### 04. 생성자 함수 (Constructor Function)
생성자 함수 내에서 this는 새로 생성된 객체를 참조합니다.

````javascript
function Person(name) {
  this.name = name;
}

const person = new Person('Alice');
console.log(person.name); // 'Alice' 출력
````
<br>

### 05. 화살표 함수 (Arrow Function)
화살표 함수는 자신만의 this 바인딩을 가지지 않습니다.<br>
대신, 화살표 함수 내에서의 this는 화살표 함수가 정의된 렉시컬 컨텍스트(lexical context)에서의 this 값을 가집니다.
<br>
💡`렉시컬 컨텍스트` : 화살표 함수가 정의된 위치의 스코프를 의미합니다.<br>
화살표 함수는 자신만의 this 바인딩을 갖지 않으며, 대신에 자신이 정의된 위치에서의 this 값을 상속받습니다. 이것은 일반 함수와 중요한 차이점입니다.

````javascript
const obj = {
  value: 42,
  showThis: function() {
    const arrowFunction = () => {
      console.log(this);
    };
    arrowFunction();
  }
};

obj.showThis(); // obj 객체를 출력
````
<br>

### 06. 명시적 바인딩 (Explicit Binding)
`call`, `apply`, `bind` 메서드를 사용하여 this를 명시적으로 설정할 수 있습니다.
<br>

- call: 함수를 호출하면서 this 값을 명시적으로 설정합니다.
- apply: call과 동일하지만, 인수를 배열로 받습니다.
- bind: 새로운 함수를 반환하면서 this 값을 명시적으로 설정합니다.

````javascript
function showThis() {
  console.log(this);
}

const obj = { value: 42 };

showThis.call(obj);  // obj 객체를 출력
showThis.apply(obj); // obj 객체를 출력

const boundFunction = showThis.bind(obj);
boundFunction();     // obj 객체를 출력
````
<br>

### 07. 이벤트 핸들러 (Event Handler)
이벤트 핸들러 내에서 this는 이벤트를 발생시킨 요소를 참조합니다.

````javascript
<button id="myButton">Click me</button>

<script>
  const button = document.getElementById('myButton');
  button.addEventListener('click', function() {
    console.log(this); // 클릭된 버튼 요소를 출력
  });
</script>
````
<br>

### ✅ 정리
- 전역 문맥: this는 전역 객체를 참조합니다.
- 함수 문맥: 기본 함수 호출에서 this는 전역 객체 (엄격 모드에서는 undefined)를 참조합니다.
- 메서드 문맥: 메서드 내에서 this는 메서드를 소유한 객체를 참조합니다.
- 생성자 함수: 생성자 함수 내에서 this는 새로 생성된 객체를 참조합니다.
- 화살표 함수: 화살표 함수는 자신만의 this를 가지지 않으며, 정의된 문맥에서의 this를 사용합니다.
- 명시적 바인딩: call, apply, bind 메서드를 사용하여 this를 명시적으로 설정할 수 있습니다.
- 이벤트 핸들러: 이벤트 핸들러 내에서 this는 이벤트를 발생시킨 요소를 참조합니다.




