---
layout: post
title: 데이터 타입
date: 2024-05-20 10:00 +0900
description: 데이터 타입
image: ../assets/img/javascript04.png
category: Javascript
tags: javascript 데이터타입 원시타입 객체타입
published: true
sitemap: true
---

# JAVASCRIPT

## 데이터 타입 (원시 타입, 객체 타입)
자바스크립트에서 데이터 타입은 크게 원시 타입(Primitive Type)과 객체 타입(Object Type)으로 나뉩니다.<br> 이 두 가지 타입은 메모리 할당, 비교 방법, 변동성 등 여러 면에서 차이가 있습니다.<br>
오늘은 자바스크립트의 원시 타입과 객체 타입에 대해 알아보겠습니다.

### 원시 타입(Primitive Type)
원시 타입은 변경 불가능한(immutable) 데이터 타입입니다.<br>
원시 타입의 값은 직접 변수에 저장됩니다.<br>
자바스크립트에서 원시 타입에는 다음과 같은 종류가 있습니다.

#### 1. 숫자(Number)
정수와 부동 소수점을 모두 포함합니다.
<br>

````javascript
let age = 30;
let price = 19.99;
````

#### 2. 문자열(String)
텍스트 데이터를 나타내며, 작은따옴표(''), 큰따옴표("") 또는 백틱(``)으로 감쌉니다.
<br>

````javascript
let name = 'John Doe';
let greeting = "Hello, World!";
let template = `Template string`;
````
#### 3. 불리언(Boolean)
참(true) 또는 거짓(false) 값을 가집니다.
<br>

````javascript
let isActive = true;
let isComplete = false;
````
#### 4. null
의도적으로 "값이 없음"을 나타내는 값입니다.
<br>

````javascript
let emptyValue = null;
````
#### 5. undefined

````javascript
let uninitialized;
````

#### 6. 심볼(Symbol)
고유하고 변경 불가능한 값을 생성하는데 사용됩니다.<br>
주로 객체의 속성 키를 생성하기 위해 사용됩니다.
<br>

````javascript
let uniqueId = Symbol('id');
````

<hr />

### 객체 타입(Object Type)
객체 타입은 변경 가능한(mutable) 데이터 타입입니다.<br>
객체 타입의 값은 참조(reference)로 변수에 저장됩니다.<br>
객체 타입에는 다양한 데이터 구조가 포함됩니다

#### 1. 객체(Object)
키-값 쌍의 집합입니다.
<br>

````javascript
let person = {
  name: 'John Doe',
  age: 30,
  isActive: true
};
````

#### 2. 배열(Array)
순서가 있는 값의 집합입니다.
<br>

````javascript
let numbers = [1, 2, 3, 4, 5];
````

#### 3. 함수(Function)
재사용 가능한 코드 블록입니다.
<br>

````javascript
function greet() {
  console.log('Hello, World!');
}
````
#### 4. 날짜(Date)
날짜와 시간을 나타내는 객체입니다.
<br>

````javascript
let today = new Date();
````

#### 5. 정규 표현식(RegExp)
문자열 패턴을 나타내는 객체입니다.
<br>

### ✅주요 차이점

#### 1. 메모리 할당
- 원시 타입: 값 자체가 변수에 저장됩니다.
- 객체 타입: 변수는 실제 값이 저장된 메모리 위치를 참조합니다.

#### 2. 변경 가능성
- 원시 타입: 불변(immutable)입니다. 값이 변경되면 새로운 메모리 공간에 새로운 값이 할당됩니다.
- 객체 타입: 가변(mutable)입니다. 객체의 속성을 변경하면 동일한 메모리 위치에서 변경이 발생합니다.

#### 3. 비교 방법
- 원시 타입: 값 자체를 비교합니다.
- 객체 타입: 참조를 비교합니다. 즉, 동일한 객체를 가리키는지 여부를 확인합니다.

````javascript
let a = 5;
let b = 5;
console.log(a === b); // true

let obj1 = { key: 'value' };
let obj2 = { key: 'value' };
console.log(obj1 === obj2); // false

let obj3 = obj1;
console.log(obj1 === obj3); // true
````
### ✅ 정리
- 원시 타입: 변경 불가능한 값으로, 값 자체가 변수에 저장됩니다. 숫자, 문자열, 불리언, null, undefined, 심볼이 포함됩니다.
- 객체 타입: 변경 가능한 값으로, 변수는 값이 저장된 메모리 위치를 참조합니다. 객체, 배열, 함수, 날짜, 정규 표현식 등이 포함됩니다.
















