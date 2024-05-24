---
layout: post
title: 데이터 형 변환
date: 2024-05-22 10:00 +0900
description: 데이터 형 변환
image: ../assets/img/javascript05.png
category: Javascript
tags: javascript 데이터형변환
published: true
sitemap: true
---

# JAVASCRIPT

## 데이터 형 변환
자바스크립트에서 데이터 형 변환은 한 데이터 타입을 다른 데이터 타입으로 변경하는 과정을 의미합니다.<br>
형 변환은 암시적(자동)으로 이루어질 수도 있고, 명시적(수동)으로 수행할 수도 있습니다.

### 암시적 형 변환 (Implicit Type Conversion) : 자동
암시적 형 변환은 자바스크립트 엔진이 자동으로 수행하는 형 변환입니다.<br>
이는 주로 다양한 타입의 값을 조작할 때 발생합니다.

#### 1. 문자열 연결
숫자와 문자열을 더하면 숫자가 문자열로 변환됩니다.
<br>

````javascript
let result = 5 + '5'; // '55'
````

#### 2. 불리언 변환
조건문에서 숫자 0, 빈 문자열, null, undefined, NaN은 false로 간주됩니다.
<br>

````javascript
if (0) {
  console.log('This will not run');
}
````

### 명시적 형 변환 (Explicit Type Conversion)
명시적 형 변환은 프로그래머가 의도적으로 형 변환을 수행하는 것입니다.<br>
여러 가지 방법을 사용할 수 있습니다.

#### 1. 문자열로 변환
- String() 함수를 사용하여 변환
<br>

````javascript
let num = 10;
let str = String(num); // '10'
````

- toString() 메서드를 사용하여 변환
<br>

````javascript
let num = 10;
let str = num.toString(); // '10'
````

#### 2. 숫자로 변환
- Number() 함수를 사용하여 변환
<br>

````javascript
let str = '123';
let num = Number(str); // 123
````
- parseInt() 함수와 parseFloat() 함수 사용
<br>

````javascript
let str = '123.45';
let intNum = parseInt(str); // 123
let floatNum = parseFloat(str); // 123.45
````
- 단항 + 연산자를 사용하여 변환
<br>

````javascript
let str = '123';
let num = +str; // 123
````

#### 3. 불리언으로 변환

- Boolean() 함수를 사용하여 변환
<br>

````javascript
let str = '';
let bool = Boolean(str); // false
````
- !! 연산자를 사용하여 변환

````javascript
let str = 'Hello';
let bool = !!str; // true
````

✅ 예제 코드

````javascript
// 암시적 형 변환
console.log('5' - 3); // 2 (문자열 '5'가 숫자 5로 변환됨)
console.log('5' + 3); // '53' (숫자 3이 문자열 '3'으로 변환됨)

// 명시적 형 변환
let strNum = '123';
let num = Number(strNum); // 문자열을 숫자로 변환
console.log(num); // 123

let boolVal = 'true';
let bool = Boolean(boolVal); // 문자열을 불리언으로 변환
console.log(bool); // true

let numToStr = 456;
let str = String(numToStr); // 숫자를 문자열로 변환
console.log(str); // '456'

// parseInt와 parseFloat
let decimal = '123.45';
console.log(parseInt(decimal)); // 123
console.log(parseFloat(decimal)); // 123.45

// 단항 + 연산자
let strToNum = '789';
console.log(+strToNum); // 789

// !! 연산자
let emptyStr = '';
console.log(!!emptyStr); // false
let nonEmptyStr = 'JavaScript';
console.log(!!nonEmptyStr); // true
````


### ✅ 정리
암시적 형 변환
- 자바스크립트 엔진이 자동으로 수행하는 형 변환. 예: 문자열 연결, 조건문에서의 불리언 변환 등.

명시적 형 변환
- 로그래머가 의도적으로 수행하는 형 변환. String(), Number(), Boolean() 함수와 parseInt(), parseFloat(), 단항 +, !! 연산자 등을 사용.


이러한 형 변환 방법을 이해하면 자바스크립트 코드 작성 시 발생할 수 있는 예기치 않은 형 변환 문제를 방지하고, 필요한 경우 올바르게 형 변환을 수행할 수 있습니다.


















