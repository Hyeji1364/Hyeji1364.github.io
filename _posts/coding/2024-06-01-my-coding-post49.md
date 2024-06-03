---
layout: post
title: Javascript 클로저(closure)
date: 2024-06-01 10:00 +0900
description: Javascript 클로저(closure)
image: ../assets/img/javascript14.png
category: Javascript
tags: Javascript 클로저 closure
published: true
sitemap: true
---

# Javascript

## 클로저 (closure)

오늘은 자바스크립트의 클로저(closure)에 대해 알아보겠습니다.
클로저는 <span style="color:red">외부 함수에 접근할 수 있는 내부 함수 혹은 이러한 원리를 일컫는 용어입니다.</span><br>
쉽게 말해서, 함수가 선언될 때 그 함수의 스코프에 있는 변수들을 기억하는 것입니다.<br>

스코프에 따라서 내부 함수의 범위에서는 외부 함수 범위에 있는 변수에 접근이 가능하지만
그 반대는 실현이 불가능하다는 개념입니다.<br>
<br>
클로저를 사용하면 함수가 선언된 곳의 외부 변수에 접근할 수 있습니다.

### 왜 클로저를 사용 ❓ 
클로저는 다음과 같은 상황에서 사용됩니다.

- 데이터 캡슐화 : 변수들을 함수 스코프에 감춰 직접 접근하지 못하게 합니다.
- 상태 유지 : 함수 호출이 끝난 후에도 변수를 기억합니다.
- 콜백 함수 : 비동기 프로그래밍에서 유용하게 쓰입니다.

👀 기본 예시

````javascript
function outerFunction() {
    let outerVariable = 'I am outside!';
    
    function innerFunction() {
        console.log(outerVariable); // innerFunction은 outerVariable에 접근할 수 있다
    }
    
    return innerFunction;
}

const myFunction = outerFunction();
myFunction(); // 'I am outside!' 출력
````
위 예제에서 innerFunction은 outerFunction의 outerVariable에 접근할 수 있습니다.<br>
outerFunction이 실행된 후에도 innerFunction은 outerVariable을 기억합니다.<br>
이것이 클로저의 핵심입니다.

<br>

👀또 다른 예제
````javascript
function makeCounter() {
    let count = 0;
    
    return function() {
        count++;
        return count;
    }
}

const counter1 = makeCounter();
console.log(counter1()); // 1
console.log(counter1()); // 2

const counter2 = makeCounter();
console.log(counter2()); // 1
console.log(counter2()); // 2
````
여기서 makeCounter 함수는 count라는 변수를 가진 내부 함수를 반환합니다.<br>
counter1과 counter2는 각각 독립된 클로저를 가집니다.<br>
그래서 counter1()과 counter2()는 서로 다른 count 값을 유지합니다.
<br>

### ❓ 클로저를 사용하는 이유 
- 은닉성 제공 : 클로저를 사용하면 변수와 함수를 외부에서 직접 접근하지 못하게 할 수 있다.
- 데이터 보존 : 클로저는 함수가 호출될 때마다 상태를 유지할 수 있게 해준다
- 모듈 패턴 구현 : 로저를 사용하여 모듈 패턴을 구현하면 코드의 가독성과 유지보수성이 향상된다.

✅ 정리
클로저는 자바스크립트의 강력한 기능으로, 함수와 그 함수가 선언된 스코프를 기억하는 메커니즘입니다.<br>
클로저를 활용하면 데이터 은닉, 상태 유지, 콜백 함수 처리 등 다양한 상황에서 유용하게 사용할 수 있습니다.<br>