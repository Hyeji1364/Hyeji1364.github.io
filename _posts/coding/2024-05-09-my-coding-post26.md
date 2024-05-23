---
layout: post
title: Javascript 메서드 정리(2) - 문자열객체
date: 2024-05-09 09:30 +0900
description: 자바스크립트 메서드 
image: ../assets/img/javscript01.png
category: Javascript
tags: Javascript
published: true
sitemap: true
---

## Javascript

### Javascript 메서드 정리(2)
자바스크립트 메서드에 대해 두번째 정리입니다. <br>
중요도에 따라 하트의 갯수가 1개부터 3개까지 입력됩니다.<br>

<hr>

### 01.💛substring()

✔ 사용방법 : string.substring(indexStart, indexEnd)<br>

📍indexStart: 추출을 시작할 인덱스입니다. <br>
📍indexEnd (선택적): 추출을 종료할 인덱스입니다. <br>
이 인덱스는 결과에 포함되지 않습니다. 이 매개변수를 생략하면 문자열의 끝까지 추출합니다.<br>

- 메서드는 문자열에서 시작 위치에서 종료 위치 값을 추출하여, 새로운 문자열을 반환합니다.
1. 인덱스 순서: 'indexStart'가 'indexEnd'보다 크면 .substring()은 두 인덱스를 자동으로 스왑합니다.
예를 들어, substring(10, 5)는 substring(5, 10)으로 처리됩니다.
2.음수 인덱스: .substring()은 음수 인덱스를 처리하지 않습니다. 음수 값은 자동으로 0으로 취급됩니다.
- 반환 값 : 지정된 부분 문자열을 반환합니다.
- 인덱스 값이 혼동될 경우 자동으로 조정해주는 특성이 있어 편합니다.

````javascript
{
// 01. 기본 사용 예시:
let text = "Hello, world!";
console.log(text.substring(7, 12));  // 출력: 'world'
console.log(text.substring(7));     // 출력: 'world!'

// 02. 인덱스 스왑 예시:
let text = "Hello, world!";
console.log(text.substring(12, 7));  // 출력: 'world'
}
````
✅ 부연 설명<br>
1. 기본 사용 예시:
첫 번째 예에서는 인덱스 7부터 12까지의 문자열 "world"를 반환합니다.<br>
두 번째 예에서는 인덱스 7부터 문자열의 끝까지 "world!"를 반환합니다.<br>

2. 인덱스 스왑 예시:
이 예에서 .substring() 메소드는 indexStart와 indexEnd의 순서를 스왑하여 "world"를 정상적으로 추출합니다.<br>


<details>
<summary>결과 확인하기</summary>
<div>
'world'<br>
'world!'<br>
'world'<br>
</div>
</details>

<br>

#### 02. 💛💛💛split()
✔ 사용방법: string.split(separator, limit)

📍separator: 문자열을 나눌 기준이 되는 구분자입니다.<br>
이 값은 문자열 또는 정규 표현식일 수 있습니다. 구분자를 생략하거나 빈 문자열을 전달하면 전체 문자열이 하나의 요소로 포함된 배열이 반환됩니다.
<br>
📍 limit (선택적): 반환될 배열의 최대 요소 수를 지정합니다. 이 값이 설정되면, 결과 배열은 최대 limit 개의 요소를 포함하게 됩니다.<br>
반환 값 : 구분자로 나누어진 문자열의 배열을 반환합니다.
<br>

- 메서드는 문자열을 구분자로 구분하고, 여러 개의 문자열(배열)을 반환합니다.
- 문자열을 배열로 분리하는데 사용됩니다.
- 구분자는 생략할 수 있습니다.

````javascript
{
// 01. 기본 사용 예시
// 이 예에서는 ", "를 구분자로 사용하여 문자열을 세 부분으로 나누고, 각 부분이 배열의 요소가 됩니다.
let text = "apple, banana, cherry";
let fruits = text.split(", ");
console.log(fruits);  // 출력: ['apple', 'banana', 'cherry']

// 02. 정규 표현식 사용 예시
// 여기서는 공백 문자(\s+)를 기준으로 문자열을 나누었습니다.
// 정규 표현식 /s+는 하나 이상의 공백을 의미합니다.
et text = "apple banana cherry";
let fruits = text.split(/\s+/);
console.log(fruits);  // 출력: ['apple', 'banana', 'cherry']

// 03. Limit 매개변수 사용 예시
// 이 예에서는 공백을 구분자로 사용하고, limit을 2로 설정하여 최대 두 개의 요소만 포함하는 배열을 생성합니다.
let text = "one two three four";
let words = text.split(" ", 2);
console.log(words);  // 출력: ['one', 'two']
}
````

<details>
<summary>결과 확인하기</summary>
<div>
['apple', 'banana', 'cherry'] ['apple', 'banana', 'cherry'] ['one', 'two']
</div>
</details>

#### 03. 💛 trim()
✔ 사용방법: 문자열.trim()
- 문자열 앞과 뒤에 있는공백이 제거된 새 문자열을 반환합니다.
- 메서드는 문자열의 앞/뒤 공백을 제거하고, 새로운 문자열을 반환합니다.
- 여기서 말하는 '공백'에는 스페이스, 탭, 줄바꿈 등이 포함됩니다.
- 이 메소드는 문자열 가운데 있는 공백은 건드리지 않고, 앞과 뒤의 공백만 제거합니다.
- .trim()은 데이터를 정리하거나, 불필요한 공백 때문에 발생할 수 있는 오류를 방지하는 데 유용하게 사용됩니다.
- 이 메소드는 원본 문자열을 변경하지 않고, 새로운 정리된 문자열을 반환합니다.


````javascript
{
let userInput = "   Hello, World!   ";
let trimmedInput = userInput.trim();
console.log(trimmedInput);  // 출력: "Hello, World!"
}
````

<details>
<summary>결과 확인하기</summary>
<div>
Hello, World!
</div>
</details>
