---
layout: post
title: Javascript 함수의 선언식과 표현식
date: 2024-06-06 10:00 +0900
description: React
image: ../assets/img/javascript18.png
category: Javascript
tags: Javascript 선언식 표현식
published: true
sitemap: true
---

# Javascript

## 🍳 함수의 선언식과 표현식

자바스크립트에서 함수를 정의하는 방법은 크게 두 가지로 나눌 수 있습니다. <br>
함수 선언식과 함수 표현식입니다.<br>
이 두 가지 방법은 함수의 동작 방식이나 코드에서의 사용법에서 차이를 보입니다.<br>
아래에서 각각의 방법을 자세히 설명하겠습니다.

### 함수 선언식

함수 선언식은 가장 전통적인 함수 정의 방법입니다. 이 방법은 function 키워드를 사용하여 함수를 선언하며, 이름을 지정해줍니다.

👀 예시

```javascript
function greet(name) {
  return `Hello, ${name}!`;
}
```

위 예시에서 greet라는 함수가 선언되었습니다. 이 함수는 name이라는 인자를 받아서 "Hello, name!"이라는 문자열을 반환합니다.

#### 주요 특징

1. 호이스팅(Hoisting)
   함수 선언식으로 정의된 함수는 호이스팅되므로, 함수가 선언되기 전에 호출해도 정상적으로 작동합니다.
   그 예시입니다.

```javascript
console.log(greet("Alice")); // "Hello, Alice!"

function greet(name) {
  return `Hello, ${name}!`;
}
```

<br>

2. 명확한 이름
   함수 선언식은 함수 이름이 명확하게 코드에 드러나기 때문에, 디버깅이나 코드 이해에 도움이 됩니다.
   <br>

### 함수 표현식

함수 표현식은 `변수`를 사용하여 함수를 정의하는 방법입니다. 이는 익명 함수나 기명 함수를 변수에 할당하는 형태로 사용됩니다.
<br>

👀 예시

```javascript
const greet = function (name) {
  return `Hello, ${name}!`;
};
```

위 예시에서 greet라는 변수에 함수가 할당되었습니다.<br>
이 함수도 name이라는 인자를 받아 "Hello, name!"이라는 문자열을 반환합니다.
<br>

#### 주요 특징

1. 익명 함수와 기명 함수
   함수 표현식은 익명 함수로 작성될 수도 있고, 기명 함수로 작성될 수도 있습니다.<br>
   익명 함수는 함수 이름이 없지만, 기명 함수는 이름이 있습니다.

```javascript
// 익명 함수
const greet = function (name) {
  return `Hello, ${name}!`;
};

// 기명 함수
const greet = function greetFunction(name) {
  return `Hello, ${name}!`;
};
```

<br>

2. 즉시 실행 함수 표현식
   함수 표현식은 정의와 동시에 실행될 수 있습니다.<br>
   이를 즉시 실행 함수 표현식(IIFE, Immediately Invoked Function Expression)이라고 합니다.

```javascript
(function (name) {
  console.log(`Hello, ${name}!`);
})("Alice");
```

#### 함수 선언식과 함수 표현식의 비교

1. 호이스팅

- 함수 선언식은 호이스팅되어 함수 선언 전에도 호출할 수 있습니다.
- 함수 표현식은 변수 선언 이후에만 호출할 수 있습니다.
  <br>

2. 가독성

- 함수 선언식은 함수 이름이 코드에 명확하게 드러나므로 가독성이 좋습니다.
- 함수 표현식은 익명 함수로 사용할 경우 함수 이름이 없기 때문에, 가독성이 떨어질 수 있습니다.
  <br>

3. 유연성

- 함수 표현식은 함수 정의와 동시에 실행할 수 있는 IIFE와 같은 패턴을 사용할 수 있어 유연합니다.
- 함수 선언식은 정의된 이후에만 실행됩니다.
  <br>

함수 선언식과 함수 표현식은 각각의 장단점이 있으며, 코드의 구조와 필요에 따라 적절히 선택하여 사용할 수 있습니다.<br>
블로그 글을 작성할 때는 이러한 특징들을 예시와 함께 잘 설명해주면 독자들이 이해하기 쉬울 것입니다.
