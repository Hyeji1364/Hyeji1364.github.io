---
layout: post
title: Javascript 메서드 정리(3) - 배열 객체
date: 2024-05-10 10:00 +0900
description: 자바스크립트 메서드 
image: <img width="810" alt="Javscript배열객체" src="https://github.com/Hyeji1364/Hyeji1364.github.io/assets/161557112/cd8affc2-dd1d-4002-97c6-0c61cf3072c2">
category: Javascript
tags: Javascript
published: true
sitemap: true
---

## Javascript

### Javascript 메서드 정리(3)
자바스크립트 메서드에 대해 세번째 정리입니다. <br>
메서드정리 1,2에서는 문자열 객체에 대해 다루었고, 이번 시간에는 배열 객체에 대해 다룰 예정입니다.<br>
중요도에 따라 하트의 갯수가 1개부터 3개까지 입력됩니다.<br>

<hr>

### 01.💛💛💛find()

✔ 사용방법 : const foundElement = 배열.find(function(element, index, array) {<br>
<br>
return 조건; // 조건이 true일 때 현재 요소를 반환 <br>
});<br>

- 메서드는 주어진 판별 함수를 만족하는 첫 번째 요소의 값을 반환합니다.
- javascript에서 배열의 요소들을 순회하며 주어진 조건을 만족하는 첫 번째 요소를 찾아 반환하는 함수입니다.
- 이 메서드는 콜백 함수를 인자로 받고, 이 콜백 함수는 각 요소를 평가하여 조건에 맞는지 확인합니다.
- 조건에 맞는 첫 번째 요소를 찾으면 그 요소를 반환하고, 만약 조건을 만족하는 요소가 없으면 undefined를 반환합니다.
- find() 메서드는 원본 배열을 변경하지 않습니다.

````javascript
{
// 01. 객체 배열에서 특정 조건을 만족하는 객체 찾기:
const products = [
    { id: 1, name: 'Keyboard', price: 29.99 },
    { id: 2, name: 'Mouse', price: 19.99 },
    { id: 3, name: 'Monitor', price: 99.99 }
];

const cheapProduct = products.find(function(product) {
    return product.price < 30; // 가격이 30 미만인 제품 찾기
});

console.log(cheapProduct); // 출력: { id: 1, name: 'Keyboard', price: 29.99 }


// 02. 배열에서 특정 숫자 찾기:
const numbers = [5, 12, 8, 130, 44];
const firstLargeNumber = numbers.find(function(number) {
    return number > 10;
});

console.log(firstLargeNumber); // 출력: 12

}
````
✅ 부연 설명<br>
02. 배열에서 특정 숫자 찾기'<br>
'numbers' 배열에서 10보다 큰 첫 번째 숫자를 찾습니다. 조건에 맞는 첫 번째 숫자는 12이므로, 12가 출력됩니다.<br>


<details>
<summary>결과 확인하기</summary>
<div>
{ id: 1, name: 'Keyboard', price: 29.99 }<br>
12<br>
</div>
</details>

<br>

#### 02. 💛💛💛forEach()
✔ 사용방법: "배열.forEach(function(element, index, array) {<br>
<br>
});<br>

`element`: 요소 / index : 인덱스 / array: forEach가 호출된 배열
<br>

- forEach()메서드는 주어진 함수 조건을 배열 요소 각각에 대해 실행하고, 그 결과를 반환합니다.
- JavaScript의 배열 메서드 중 하나로, 배열의 각 요소에 대해 주어진 함수를 한 번 씩 실행합니다.
- 이 메서드는 배열의 각 요소마다 콜백 함수를 호출하면서, 요소 자체와 요소의 인덱스, 그리고 배열 전체를 인자로 전달합니다.
- forEach() 메서드는 원본 배열을 수정하지 않으며 반환값도 없습니다(즉, undefined를 반환합니다).
- 이 메서드는 주로 배열 내 각 요소에 대해 연산을 수행하거나 결과를 출력하는 등의 작업에 사용됩니다.

````javascript
{
const numbers = [1, 2, 3, 4, 5];
numbers.forEach(function(number, index) {
    console.log(`Index ${index}: ${number}`);
});
}
````

<details>
<summary>결과 확인하기</summary>
<div>
Index 0: 1<br>
Index 1: 2<br>
Index 2: 3<br>
Index 3: 4<br>
Index 4: 5<br>
</div>
</details>

#### 03. 💛filter()
✔ 사용방법: const newArray = 배열.filter(function(element, index, array) { <br>
<br>
return 조건; // 조건이 true일 때 요소를 새 배열에 포함<br>
});<br>

`element`: 배열에서 현재 처리 중인 요소입니다.<br>
`index`: 배열에서 현재 처리 중인 요소의 인덱스입니다.<br>
`array`: filter()가 호출된 배열입니다.
<br>

- 이 메서드는 주어진 함수 조건에 맞는 모든 요소를 새로운 배열로 반환합니다.
- 콜백 함수를 인자로 받으며, 이 콜백 함수는 각 요소를 평가하여 'true' 또는 'false'를 반환합니다.
- true를 반환하는 요소만이 새 배열에 포함됩니다.
- filter()는 원본 배열을 변경하지 않으며, 조건에 맞는 요소들로 구성된 새로운 배열을 반환합니다.

````javascript
{
const numbers = [1, 2, 3, 4, 5, 6];
const evenNumbers = numbers.filter(function(number) {
    return number % 2 === 0; // 짝수 조건
});
console.log(evenNumbers); // 출력: [2, 4, 6]
}
````

위의 예시에서는 숫자 배열에서 짝수만 필터링하여 새로운 배열을 생성하는 방법을 보여줍니다.<br>
이 코드는 배열 numbers의 각 요소를 콜백 함수에 전달하고, 짝수인지 확인합니다.<br>
짝수일 경우 true를 반환하며, 이 때문에 해당 요소는 evenNumbers 배열에 포함됩니다.<br>

<details>
<summary>결과 확인하기</summary>
<div>
[2, 4, 6]
</div>
</details>


#### 04. 💛💛💛map()
✔ 사용방식: const newArray = 배열.map(function(element, index, array){ <br>
<br>
return 새로운 값;<br>
});<br>

- 이 메서드는 주어진 함수를 호출하여 각 요소에 대한 결과를 모아 새로운 배열을 만듭니다.
- 이 메서드는 원본 배열의 모든 요소를 하나씩 처리하여 그 결과를 새 배열의 해당 위치에 저장합니다.
- map()은 배열의 길이를 변경하지 않고, 원본 배열은 수정하지 않으면서 각 요소에 대해 주어진 함수를 실행한 결과로 구성된 새 배열을 반환합니다.
- map() 메서드는 데이터를 변환하거나 수정하여 새로운 형태의 데이터를 생성할 때 매우 유용합니다.
- 예를 들어, 객체 배열에서 특정 키의 값을 수정하거나 새로운 키를 추가하는 등의 작업에 자주 사용됩니다.


````javascript
{
const numbers = [1, 2, 3, 4, 5];
const squaredNumbers = numbers.map(function(number) {
    return number * number; // 각 숫자를 제곱
});
console.log(squaredNumbers); // 출력: [1, 4, 9, 16, 25]
}
````
위의 예시에서는 숫자 배열의 각 요소를 제곱하여 새로운 배열을 생성하는 방법을 보여줍니다.<br>
이 코드는 numbers 배열의 각 요소에 대해 제곱 연산을 수행하고, 그 결과를 squaredNumbers라는 새 배열에 저장합니다.<br>
결과적으로, 각 숫자의 제곱값을 요소로 하는 새 배열이 출력됩니다.<br>

<details>
<summary>결과 확인하기</summary>
<div>
[1, 4, 9, 16, 25]
</div>
</details>

#### 04. 💛includes()
✔ 사용방식: const containsElement = 배열.includes(찾고자하는요소, 시작인덱스);<br>
시작인덱스 : 검색을 시작할 인덱스입니다. 이 인자는 선택적이며, 기본값은 0입니다.<br>

- 이 메서드는 배열 내에 특정 요소 또는 문자가 포함되어 있는지를 검색하여, 불린(true, false)을 반환합니다.
- 배열에서는 특정 요소의 존재 여부를 확인할 때 사용하고, 문자열에서는 특정 문자열이 포함되어 있는지를 검사할 때 사용됩니다.
- includes() 메서드는 간단하게 특정 값이나 문자열이 포함되어 있는지 여부를 확인할 때 유용하게 사용되며, 조건문에서 특히 자주 사용됩니다.

````javascript
{
const fruits = ['apple', 'banana', 'mango'];
const hasBanana = fruits.includes('banana');
console.log(hasBanana); // 출력: true
}
````

<details>
<summary>결과 확인하기</summary>
<div>
true
</div>
</details>

#### 05. 💛indexOf()
✔ 사용방식: array.indexOf(searchElement, fromIndex)<br>

- 메서드는 배열을 검색하고, 주어진 값과 일치하는 첫 번째 인덱스를 반환합니다.
- searchElement: 배열에서 찾고자 하는 요소입니다.
- fromIndex (선택적): 검색을 시작할 인덱스입니다. 기본값은 0입니다.

````javascript
{
let numbers = [1, 2, 3, 4, 5, 2];
console.log(numbers.indexOf(2));         // 출력: 1
console.log(numbers.indexOf(7));         // 출력: -1 (존재하지 않는 경우)
console.log(numbers.indexOf(2, 2));      // 출력: 5 (인덱스 2 이후에 위치한 '2'의 인덱스)
}
````

📍01. 기본예시 <br>
여기서 'world'는 문자열 's'의 7번 인덱스에서 시작하기 때문에 '7'을 반환합니다.<br>
'Python'은 문자열 's'에 존재하지 않기 때문에 '-1'이 반환됩니다.
<br>
📍02. 시작 인덱스와 끝 인덱스 사용하기<br>
두 번째 호출은 인덱스 5부터 13까지의 범위에서 'over'문자열이 포함되어 있지 않으므로 '-1'이 출력됩니다.<br>

<details>
<summary>결과 확인하기</summary>
<div>
1<br>
-1<br>
5<br>
</div>
</details>