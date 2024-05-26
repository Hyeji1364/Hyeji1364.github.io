---
layout: post
title: Javascript 호이스팅
date: 2024-05-25 10:00 +0900
description: Javascript 호이스팅
image: ../assets/img/javascript08.png
category: Javascript
tags: Javascript 호이스팅 Hoisting
published: true
sitemap: true
---

# JAVASCRIPT

## 호이스팅(Hoisting)
오늘은 자바스크립트의 `호이스팅`에 대해 설명해보겠습니다.

자바스크립트에서 호이스팅(Hoisting)은 코드가 실행되기 전에 변수와 함수의 선언이 자동으로 코드의 맨 위로 끌어올려져 초기화되는 것을 말합니다.<br>
이로 인해 변수 선언 이전에 해당 변수를 참조하더라도 오류가 발생하지 않고 undefined를 반환하게 됩니다. <br>

호이스팅은 크게 변수 호이스팅과 함수 호이스팅으로 설명할 수 있습니다.
예시를 통해 설명해보겠습니다.<br>

### 📁 변수 호이스팅(Variable Hoisting)
먼저 변수 호이스팅을 보겠습니다.<br>
자바스크립트는 변수 선언을 코드의 맨 위로 끌어올립니다.<br>
하지만 변수의 값 할당은 원래 코드 위치에 남습니다.<br>

````javascript
console.log(myVar); // undefined
var myVar = 5;
console.log(myVar); // 5
````
➡ 위 코드에서 첫 번째 console.log는 myVar 변수를 선언하기 전에 호출되었지만, 오류가 발생하지 않고 undefined를 출력합니다.<br>
이는 자바스크립트가 내부적으로 다음과 같이 코드를 처리하기 때문입니다.

````javascript
var myVar;
console.log(myVar); // undefined
myVar = 5;
console.log(myVar); // 5
````
<br>
### 📁 함수 호이스팅 (Function Hoisting)
함수 호이스팅도 비슷합니다.<br>
함수 선언은 전체 함수가 코드의 맨 위로 끌어올려집니다.<br>
따라서, 함수 선언 전에 함수를 호출할 수 있습니다.

````javascript
myFunction(); // Hello, world!

function myFunction() {
    console.log("Hello, world!");
}
````
이 코드에서 myFunction은 함수 선언 전에 호출되었지만 정상적으로 작동합니다. 이는 자바스크립트가 내부적으로 다음과 같이 코드를 처리하기 때문입니다.

````javascript
function myFunction() {
    console.log("Hello, world!");
}

myFunction(); // Hello, world!
````
함수 선언이 코드의 맨 위로 끌어올려진 것입니다.
<br>
### 💡 let과 const의 호이스팅
let과 const로 선언된 변수도 호이스팅되지만, 이들은 <span style="color:yellow">"일시적 사각지대"(Temporal Dead Zone, TDZ)</span>에 들어가서 선언하기 전에는 접근할 수 없습니다.<br>
따라서 다음과 같은 코드에서는 오류가 발생합니다.

````javascript
console.log(myLet); // ReferenceError: Cannot access 'myLet' before initialization
let myLet = 5;
console.log(myLet); // 5
````
이 코드는 내부적으로 다음과 같이 처리됩니다.

````javascript
// TDZ 시작
let myLet;
// TDZ 끝
console.log(myLet); // ReferenceError: Cannot access 'myLet' before initialization
myLet = 5;
console.log(myLet); // 5
````

### ✅ 정리
- <b>변수 호이스팅</b>: var로 선언된 변수는 선언이 코드의 맨 위로 끌어올려지지만 값 할당은 원래 위치에 남습니다.
- <b>함수 호이스팅</b>: 함수 선언은 전체 함수가 코드의 맨 위로 끌어올려집니다.
- <b>let/const 호이스팅</b>: let과 const로 선언된 변수는 선언 전에 접근하려 하면 오류가 발생합니다.

호이스팅은 코드 실행 전 자바스크립트가 변수와 함수 선언을 어떻게 처리하는지 이해하는 데 도움이 됩니다. 이를 알면 코드가 어떻게 동작할지 예측하기 쉬워집니다.