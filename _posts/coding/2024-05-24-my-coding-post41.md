---
layout: post
title: var, let, const차이
date: 2024-05-24 10:00 +0900
description: 데이터 형 변환
image: ../assets/img/javascript07.png
category: Javascript
tags: Javascript var let const
published: true
sitemap: true
---

# JAVASCRIPT

## var, let, const의 차이
오늘은 자바스크립트에서 변수를 선언핳 때 사용하는 `var`, `let`, `const`의 차이에 대해 알아보겠습니다.

💡알아보기 전! 계속 나오는 개념인 스코프(Scope)에 대해 알아보겠습니다.

### 스코프
변수가 어디서 접근할 수 있는지를 결정하는 규칙입니다.<br>
즉, 변수를 사용할 수 있는 "유효 범위"라고 생각하면 됩니다.<br>
스코프는 코드의 가독성을 높이고 변수의 충돌을 막기 위해 중요합니다.

자바스크립트에서 스코프는 크게 두 가지가 있습니다.
`함수 스코프`와 `블록 스코프`입니다.

📍 함수 스코프(Function Scope) <br>
- 함수 안에서 선언된 변수는 함수 내부에서만 접근할 수 있는 범위를 말합니다.<br>
var로 선언된 변수는 함수 스코프를 가집니다.

````javascript
function myFunction() {
  var x = 10; // 함수 스코프
  console.log(x); // 10
}

myFunction();
console.log(x); // 오류! x는 함수 밖에서 접근할 수 없어요.
````
위 코드에서 x는 myFunction 함수 안에서만 접근할 수 있습니다.
<br>

📍 블록 스코프(Block Scope) <br>
- 중괄호 {}로 감싸진 코드 블록 내에서 선언된 변수는 블록 내부에서만 접근할 수 있는 범위를 말합니다.<br>
let과 const로 선언된 변수는 블록 스코프를 가집니다.

````javascript
if (true) {
  let y = 20; // 블록 스코프
  console.log(y); // 20
}

console.log(y); // 오류! y는 블록 밖에서 접근할 수 없어요.
````

<hr />
그럼 지금부터는 var, let, const의 차이에 대해 알아보겠습니다.

### var
- 함수 스코프: 함수 내에서 선언된 변수는 함수 전체에서 접근할 수 있습니다.
- 재선언 가능: 같은 이름으로 변수를 다시 선언할 수 있습니다.
- 호이스팅: 변수를 선언하기 전에 사용할 수 있지만, 그 값은 undefined입니다.

예시
````javascript
function example() {
  var x = 10;
  if (true) {
    var x = 20; // 같은 함수 내에서 다시 선언 가능
    console.log(x); // 20
  }
  console.log(x); // 20, 블록을 무시하고 함수 전체에서 접근 가능
}
example();
````

### let
- 블록 스코프: 중괄호 {}로 감싸진 블록 내에서만 접근할 수 있습니다.
- 재선언 불가능: 같은 스코프 내에서 동일한 이름으로 변수를 다시 선언할 수 없습니다.
- 호이스팅: 변수를 선언하기 전에 사용할 수 없고, ReferenceError가 발생합니다.

````javascript
function example() {
  let x = 10;
  if (true) {
    let x = 20; // 블록 내에서만 접근 가능
    console.log(x); // 20
  }
  console.log(x); // 10, 블록 밖의 x에 접근
}
example();
````

### const
- 블록 스코프: 중괄호 {}로 감싸진 블록 내에서만 접근할 수 있습니다.
- 재선언 불가능: 같은 스코프 내에서 동일한 이름으로 변수를 다시 선언할 수 없습니다.
- 재할당 불가능: 선언된 변수에 다른 값을 다시 할당할 수 없어요. 하지만 객체나 배열의 속성이나 요소는 변경할 수 있습니다.
- 호이스팅: 변수를 선언하기 전에 사용할 수 없고, ReferenceError가 발생합니다.

````javascript
function example() {
  const x = 10;
  if (true) {
    const x = 20; // 블록 내에서만 접근 가능
    console.log(x); // 20
  }
  console.log(x); // 10, 블록 밖의 x에 접근

  const person = { name: "John", age: 30 };
  person.age = 31; // 객체의 속성은 변경 가능
  console.log(person.age); // 31
}
example();
````
### ✅ 정리
📍 var:
- 함수 스코프 : 함수 내에서 선언된 변수는 함수 전체에서 접근할 수 있음
- 재선언 가능
- 호이스팅(변수를 선언하기 전에 사용할 수 있지만 undefined 값)
<br>

📍 let:
- 블록 스코프
- 재선언 불가능
- 호이스팅(변수를 선언하기 전에 사용할 수 없고 ReferenceError 발생)

📍 const:
- 블록 스코프
- 재선언 불가능
- 재할당 불가능 (객체나 배열의 속성은 변경 가능)
- 호이스팅(변수를 선언하기 전에 사용할 수 없고 ReferenceError 발생)

















