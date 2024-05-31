---
layout: post
title: 자바스크립트 스코프(Scope)
date: 2024-05-30 10:00 +0900
description: 자바스크립트 스코프(Scope)
image: ../assets/img/javascript12.png
category: Javascript
tags: Javascript 스코프 Scope
published: true
sitemap: true
---

# Javascript

## 스코프(scope)

오늘은 자바스크립트의 스코프(Scope)에 대해 설명하겠습니다.<br>
자바스크립트에서 스코프는 변수가 접근 가능한 유효 범위를 말합니다.<br>
변수의 스코프는 해당 변수가 어디에서 선언되었는지에 따라 결정됩니다. <br>
스코프는 크게 전역 스코프(Global Scope)와 지역 스코프(Local Scope)로 나뉩니다.
<br>

### 1-1. 전역 스코프 (Global Scope)
전역 스코프는 코드 전체에서 접근 가능한 변수의 범위를 의미합니다.<br>
전역 변수는 함수 바깥에서 선언되며, 코드 어디에서나 접근할 수 있습니다.<br>
전역 변수는 페이지 로드 시 생성되며, 페이지가 닫힐 때까지 유지됩니다.

````javascript
var globalVariable = "I am global";

function printGlobalVariable() {
  console.log(globalVariable);
}

printGlobalVariable(); // "I am global"
````
<br>

### 1-2. 지역 스코프 (Local Scope)
지역 스코프는 특정 코드 블록 내에서만 접근 가능한 변수의 범위를 의미합니다.<br>
지역 변수는 함수나 블록 내에서 선언되며, 해당 함수나 블록이 실행될 때 생성되고, 실행이 끝나면 소멸됩니다.

````javascript
function myFunction() {
  var localVariable = "I am local";
  console.log(localVariable);
}

myFunction(); // "I am local"
console.log(localVariable); // ReferenceError: localVariable is not defined
````

### 2. 함수 스코프와 블록 스코프

자바스크립트에서는 함수 스코프(Function Scope)와 블록 스코프(Block Scope)를 구분합니다.<br>
이는 변수가 정의된 위치에 따라 다르게 동작합니다.

#### 2-1. 함수 스코프
함수 스코프는 변수가 함수 내부에서 선언되면 그 함수 전체에서 유효하다는 의미입니다.<br>
var 키워드는 함수 스코프를 따릅니다.

````javascript
function myFunction() {
  var functionScopedVariable = "I am function scoped";
  if (true) {
    var functionScopedVariable = "I am still function scoped";
    console.log(functionScopedVariable); // "I am still function scoped"
  }
  console.log(functionScopedVariable); // "I am still function scoped"
}

myFunction();
````
#### 2-2. 블록 스코프
블록 스코프는 변수가 블록({}) 내부에서 선언되면 그 블록 내에서만 유효하다는 의미입니다.<br>
`let`과 `const` 키워드는 블록 스코프를 따릅니다.

````javascript
function myBlockScopedFunction() {
  if (true) {
    let blockScopedVariable = "I am block scoped";
    console.log(blockScopedVariable); // "I am block scoped"
  }
  console.log(blockScopedVariable); // ReferenceError: blockScopedVariable is not defined
}

myBlockScopedFunction();6
````
<br>

### 3. 렉시컬 스코프
자바스크립트는 렉시컬 스코프(Lexical Scope) 또는 정적 스코프(Static Scope)를 따릅니다.<br>
이는 함수가 선언된 위치에 따라 상위 스코프가 결정된다는 의미입니다.<br>
자바스크립트는 함수가 호출되는 위치가 아닌, 함수가 정의된 위치를 기준으로 스코프를 결정합니다.

````javascript
var globalVar = "global";

function outerFunction() {
  var outerVar = "outer";

  function innerFunction() {
    console.log(globalVar); // "global"
    console.log(outerVar); // "outer"
  }

  innerFunction();
}

outerFunction();
````
위 예제에서 innerFunction은 outerFunction 내부에서 정의되었기 때문에, outerFunction의 스코프에 접근할 수 있습니다.
<br>

### 4. 클로저(Closures)
클로저는 자바스크립트의 강력한 기능 중 하나로, 함수가 선언될 때의 렉시컬 스코프를 기억하여 함수 외부에서 해당 스코프에 접근할 수 있게 합니다.<br>
이는 주로 데이터 은닉 및 상태 유지에 사용됩니다.

````javascript
function makeCounter() {
  let count = 0;
  return function() {
    count++;
    return count;
  };
}

const counter = makeCounter();
console.log(counter()); // 1
console.log(counter()); // 2
console.log(counter()); // 3
````
위 예제에서 `makeCounter` 함수는 count 변수를 정의하고, 이 변수를 참조하는 내부 함수를 반환합니다.<br>
반환된 내부 함수는 count 변수에 대한 클로저를 형성하여, makeCounter 함수가 실행된 이후에도 count 변수에 접근할 수 있게 합니다.
<br>

### ✅ 요약
자바스크립트의 스코프는 변수가 어디에서 정의되고 어디에서 접근 가능한지를 결정하는 중요한 개념입니다.<br>
전역 스코프와 지역 스코프, 함수 스코프와 블록 스코프, 렉시컬 스코프와 클로저까지 이해하면 자바스크립트 코드의 동작 방식을 더 깊이 이해할 수 있습니다.<br>
이러한 개념들은 코드의 가독성을 높이고, 예기치 않은 오류를 줄이는 데 큰 도움이 됩니다.<br>
스코프를 잘 이해하고 활용하면, 더욱 효율적이고 유지 보수하기 쉬운 코드를 작성할 수 있습니다.