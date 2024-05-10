---
layout: post
title: Javascript 메서드 정리 (1)
date: 2024-05-10 23:00 +0900
description: 자바스크립트 메서드 
image: ../assets/img/webd.webp
category: Javascript
tags: Javascript
published: true
sitemap: true
---

## Javascript

### Javascript 메서드 정리
오늘은 자바스크립트 메서드에 대해 정리하는 시간을 가져보겠습니다.<br>
중요도에 따라 하트의 갯수가 1개부터 3개까지 정리하겠습니다.<br>

<hr>

### 01.💛.includes()

✔ 사용방식 : string.includes(searchString, position)

- searchString: 문자열에서 찾고자 하는 부분 문자열입니다.
- position (선택적): 검색을 시작할 위치를 지정합니다. 기본값은 0입니다.
- 메서드는 문자열 포함 여부를 검색하여, 불린(true, false)을 반환합니다.
- 대소문자를 구별합니다.
- 문자열이 포함되어 있으면 'true'를 그렇지 않으면 'false'를 반환합니다.
- 검색하려는 요소를 첫번째 매개변수로 지정하고, 검색을 시작할 위치를 두 번째 매개변수로 선택적으로 지정할 수 있습니다.

````javascript
{
let text = "Hello, world!";
console.log(text.includes("world"));  // 출력: true
console.log(text.includes("hello"));  // 출력: false (대소문자 구분)
console.log(text.includes("o", 5));   // 출력: true (인덱스 5부터 'o' 검색)
}
````

<details>
<summary>결과 확인하기</summary>
<div>
true<br>
false<br>
true<br>

<br>

#### 02. 💛.indexOf()
✔ 사용방식: string.indexOf(searchValue, fromIndex)
- searchValue: 찾고자 하는 문자열입니다.
- fromIndex (선택적): 검색을 시작할 위치입니다. 이 매개변수를 생략하면 기본값은 0입니다.
- 요소가 존재하지 않으면 '-1'을 반환합니다.
- 대소문자를 구분하며, 정확한 일치를 찾습니다.
- 배열에서는 특정 요소의 위치를, 문자열에서는 부분 문자열의 시작
- 위치를 알아내는데 유용하게 사용할 수 있습니다.

````javascript
{
let text = "Hello, world!";
console.log(text.indexOf("world"));   // 출력: 7
console.log(text.indexOf("Hello"));   // 출력: 0
console.log(text.indexOf("o"));       // 출력: 4
console.log(text.indexOf("z"));       // 출력: -1 (존재하지 않는 경우)
console.log(text.indexOf("o", 5));    // 출력: 8 (인덱스 5 이후의 'o' 위치)
}
````

<details>
결과 확인하기
<div>
7<br>
0<br>
4<br>
-1<br>
8<br>
