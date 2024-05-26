---
layout: post
title: Javascript ES6 문법 특징과 차이
date: 2024-05-26 10:00 +0900
description: Javascript 호이스팅
image: ../assets/img/javascript09.png
category: Javascript
tags: Javascript ES6
published: true
sitemap: true
---

# JAVASCRIPT

## ES6 문법 특징
자바스크립트 ES6(ECMAScript 2015)는 자바스크립트의 주요 업데이트로, 많은 새로운 기능과 개선된 문법을 도입했습니다.<br>
이를 통해 코드를 더 간결하고 효율적으로 작성할 수 있게 되었습니다.<br>
오늘은 ES6 주요 문법 특징과 차이점을 설명하겠습니다.

### 📍 01. let과 const 
- let : 블록 스코프 변수를 선언합니다. 블록({}) 내에서만 유효합니다.
- const: 블록 스코프 상수를 선언합니다. 선언과 동시에 값을 할당해야 하며, 이후에 값을 변경할 수 없습니다.

````javascript
let x = 10;
x = 20; // 가능

const y = 30;
y = 40; // 오류: 상수는 값을 변경할 수 없습니다.
````
<br>

### 📍 02. 화살표 함수 (Arrow Functions)
화살표 함수는 간결한 함수 표현식입니다.<br>
<span style="color:red">화살표 함수로 함수 선언법이 좀 더 간결해졌습니다.</span><br>
function 키워드를 생략하고, this 바인딩이 선언 시점의 컨텍스트를 유지합니다.

````javascript
// 기존 함수 표현식
var add = function(a, b) {
    return a + b;
};

// 화살표 함수
const add = (a, b) => a + b;
````
<br>

### 📍 03. 템플릿 리터럴 (Template Literals)
템플릿 리터럴은 `백틱(``)`을 사용하여 문자열을 작성하며, `${}`를 사용해 변수나 표현식을 삽입할 수 있습니다.<br>
<span style="color:red">ES5에서는 변수를 문자열과 같이 쓰려면 하나씩 문자열을 지정해야 하지만 백틱을 사용해 여러 줄의 문자열과 값을 간단하게 나타냅니다.</span><br>
멀티라인 문자열도 쉽게 작성할 수 있습니다.

````javascript
const name = 'Alice';
const greeting = `Hello, ${name}!`;
console.log(greeting); // Hello, Alice!

const multiline = `This is
a multi-line
string.`;
console.log(multiline);
````
<br>

### 📍 04. 디스트럭처링 (Destructuring)
디스트럭처링을 사용하면 배열이나 객체의 값을 쉽게 추출하여 변수에 할당할 수 있습니다.

````javascript
// 배열 디스트럭처링
const [a, b] = [1, 2];
console.log(a); // 1
console.log(b); // 2

// 객체 디스트럭처링
const { name, age } = { name: 'Alice', age: 25 };
console.log(name); // Alice
console.log(age); // 25
````
<br>

### 📍 05. 기본 매개변수
기본 매개변수를 사용하면 함수 매개변수에 기본값을 지정할 수 있습니다.<br>
ES5에서는 인자가 없거나 언디파인드인 경우에 기본값을 설정해 놓아야 합니다.<br>
ES6에서는 기본 매개변수를 지정하고 없는 경우에는 지정한 기본값을 인자로 전달 해야한다.

````javascript
function greet(name = 'Guest') {
    console.log(`Hello, ${name}!`);
}
greet(); // Hello, Guest!
greet('Alice'); // Hello, Alice!
````
<br>

### 📍 06. 전개 연산자 (Spread Operator)와 나머지 매개변수 (Rest Parameters)
- 전개 연산자: 배열이나 객체의 요소를 개별 요소로 분리합니다.

````javascript
const arr1 = [1, 2, 3];
const arr2 = [...arr1, 4, 5];
console.log(arr2); // [1, 2, 3, 4, 5]
````
- 나머지 매개변수: 함수의 매개변수 목록의 나머지를 배열로 묶습니다.

````javascript
function sum(...numbers) {
    return numbers.reduce((total, num) => total + num, 0);
}
console.log(sum(1, 2, 3)); // 6
````
<br>

### 📍 07. 클래스(Classes)
ES6 클래스는 기존의 프로토타입 기반 상속을 더 직관적으로 사용할 수 있게 해줍니다.
````javascript
class Person {
    constructor(name, age) {
        this.name = name;
        this.age = age;
    }

    greet() {
        console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
    }
}

const alice = new Person('Alice', 25);
alice.greet(); // Hello, my name is Alice and I am 25 years old.
````
<br>

### 08. 📍 모듈 (Modules)
ES6 모듈을 사용하면 코드를 모듈화하고 재사용할 수 있습니다.<br>
ES6부터는 import/export로 모듈을 관리할 수 있습니다.<br>
로드 모듈은 import/from으로 설정하고 아웃풋 모듈은 export default class를 설정하면 됩니다.<br>

#### 모듈 내보내기 (export):
- 기본 내보내기 (export default) : 모듈에서 기본으로 내보낼 항목을 지정합니다.<br>
파일당 하나의 기본 내보내기만 가능합니다.
````javascript
// math.js
export default class Math {
    static add(a, b) {
        return a + b;
    }

    static subtract(a, b) {
        return a - b;
    }
}
````
- 명시적 내보내기 (export): 여러 개의 항목을 내보낼 수 있습니다. 함수, 변수, 클래스 등을 개별적으로 내보낼 수 있습니다.

````javascript
// math.js
export const add = (a, b) => a + b;
export const subtract = (a, b) => a - b;
````

- 모듈 가져오기 (import):
````javascript
// main.js
import { add, subtract } from './math.js';
console.log(add(2, 3)); // 5
console.log(subtract(5, 2)); // 3
````

<br>

### 📍 09. 프로미스 (Promises)
프로미스는 `비동기` 작업을 처리하는 새로운 방법을 제공합니다.<br>
콜백 함수 대신 `.then`과 `.catch`를 사용합니다.
````javascript
const fetchData = () => {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            resolve('Data fetched');
        }, 2000);
    });
};

fetchData().then(data => console.log(data)); // Data fetched (after 2 seconds)
````

💡 여기서 비동기 방식이란 , 시간이 오래걸리는 작업을 수행하는 동안 그 작업이 완료될 때까지 기다리지 않고 다른 작업을 계속할 수 있게 해주는 것입니다.
이와 반대로 동기 방식은 작업이 완료될 때까지 다음 작업을 기다리는 방식입니다.
이를 통해 프로그램이 더 효율적으로 실행될 수 있고 주요 개념으로는 콜백 함수, 프로미스, `async`과 `await`가 있습니다.

비동기 방식에서는 추후 포스팅으로 다뤄보겠습니다.
<br>

### 📍 10. 심볼 (Symbols)
심볼은 고유하고 변경 불가능한 데이터 타입으로, 객체의 속성 키로 사용될 수 있습니다.
````javascript
const mySymbol = Symbol('description');
const obj = {
    [mySymbol]: 'value'
};
console.log(obj[mySymbol]); // value
````
### ✅ 정리
ES6는 자바스크립트를 더 강력하고 편리하게 만드는 다양한 새로운 기능을 도입했습니다.<br>
이 새로운 기능들은 코드의 가독성, 유지보수성, 그리고 효율성을 크게 향상시킵니다.<br>
ES6를 사용하면 더 간결하고 직관적인 코드를 작성할 수 있습니다.