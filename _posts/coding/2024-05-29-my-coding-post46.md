---
layout: post
title: 자바스크립트 화살표 함수와 일반 함수의 차이
date: 2024-05-29 10:00 +0900
description: 자바스크립트 화살표 함수와 일반 함수의 차이
image: ../assets/img/javascript11.png
category: Javascript
tags: Javascript 화살표함수 일반함수
published: true
sitemap: true
---

# Javascript

## 화살표 함수와 일반 함수 차이

오늘은 자바스크립트의 화살표 함수와 일반함수의 차이에 대해 알아보겠습니다.<br>
화살표 함수(Arrow Function)와 일반 함수(Function Expression/Declaration)는 몇 가지 중요한 차이점이 있습니다.<br>
이 차이점들은 주로 문법적 차이, this 키워드의 처리 방식, 그리고 몇 가지 고유한 특성들에 있습니다.
<br>

<hr />

### 1. 문법적 차이

📍 일반 함수

````javascript
// 함수 선언식 (Function Declaration)
function regularFunction(a, b) {
    return a + b;
}

// 함수 표현식 (Function Expression)
const regularFunction = function(a, b) {
    return a + b;
};
````
<br>
📍 화살표 함수

````javascript
const arrowFunction = (a, b) => {
    return a + b;
};

// 중괄호와 return 생략 가능 (한 줄일 경우)
const arrowFunction = (a, b) => a + b;

// 매개변수가 하나일 경우 괄호 생략 가능
const singleParamFunction = a => a * 2;

// 매개변수가 없을 경우 빈 괄호 사용
const noParamFunction = () => console.log('Hello!');
````
<br>

### 2. this 키워드의 처리 방식

📍 일반 함수
일반 함수에서는 this 키워드는 함수가 호출될 때의 컨텍스트를 가리킵니다.<br>
즉, this는 함수를 호출한 객체를 가리킵니다.

````javascript
const obj = {
    value: 10,
    regularFunction: function() {
        console.log(this.value); // this는 obj를 가리킴
    }
};

obj.regularFunction(); // 10
````
<br>

 📍 화살표 함수

화살표 함수에서는 this 키워드는 자신이 정의된 시점의 상위 스코프를 가리킵니다.<br>
즉, 화살표 함수는 자신의 this 값을 가지지 않고, 외부 함수의 this를 사용합니다.

````javascript
const obj = {
    value: 10,
    arrowFunction: () => {
        console.log(this.value); // this는 외부 스코프를 가리킴 (전역 객체 또는 undefined)
    }
};

obj.arrowFunction(); // undefined (또는 strict 모드에서는 에러)
````
<br>

### 3. arguments 객체

📍 일반 함수
일반 함수는 암묵적인 arguments 객체를 가지고 있어서, 함수에 전달된 모든 인수에 접근할 수 있습니다.

````javascript
function regularFunction() {
    console.log(arguments);
}

regularFunction(1, 2, 3); // [1, 2, 3]
````
<br>

📍 화살표 함수
````javascript
const arrowFunction = (...args) => {
    console.log(args);
};

arrowFunction(1, 2, 3); // [1, 2, 3]
````
<br>

### 4. 생성자 함수

📍 일반 함수
일반 함수는 new 키워드와 함께 호출되어 생성자 함수로 사용할 수 있습니다.

````javascript
function Person(name) {
    this.name = name;
}

const person = new Person('Alice');
console.log(person.name); // Alice
````
<br>

📍 화살표 함수
화살표 함수는 생성자 함수로 사용할 수 없습니다. new 키워드와 함께 호출하면 에러가 발생합니다.

````javascript
const Person = (name) => {
    this.name = name;
};

const person = new Person('Alice'); // Error: Person is not a constructor
````
<br>

### 5. 메서드 정의

📍 일반 함수
객체 메서드를 정의할 때 주로 일반 함수를 사용합니다.

````javascript
const obj = {
    value: 10,
    regularMethod: function() {
        console.log(this.value); // 10
    }
};
````
<br>
📍 화살표 함수

````javascript
const obj = {
    value: 10,
    arrowMethod: () => {
        console.log(this.value); // undefined
    }
};
````
<br>

### ✅ 요약
- 문법: 화살표 함수는 간결한 문법을 제공합니다.
- this 바인딩: 화살표 함수는 상위 스코프의 this를 사용하고, 일반 함수는 호출 시점의 컨텍스트에 따라 this를 바인딩합니다.
- arguments 객체: 일반 함수는 arguments 객체를 가지지만, 화살표 함수는 가지지 않습니다.
- 생성자 함수: 일반 함수는 생성자 함수로 사용할 수 있지만, 화살표 함수는 사용할 수 없습니다.
- 메서드 정의: 객체 메서드를 정의할 때는 일반 함수를 사용하는 것이 더 적합합니다.

