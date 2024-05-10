---
layout: post
title: Javascript 메서드 정리(2) - 문자열객체
date: 2024-05-10 09:30 +0900
description: 자바스크립트 메서드 
image: ../assets/img/Javascript.jpg
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



#### 04. 💛replace()
✔ 사용방식: string.replace(searchValue, newValue)
📍searchValue: 대체하고자 하는 문자열이나 정규 표현식입니다.
📍newValue: searchValue를 대체할 문자열이거나, 매치된 부분을 다루는 함수가 될 수 있습니다.

- 메서드는 문자열에서 특정 문자열을 교체하여, 새로운 문자열을 반환합니다.
- 이 메소드는 문자열의 첫 번째 일치 항목만 대체하거나, 정규 표현식과 함께 사용하여 글로벌로 여러 항목을 대체할 수 있습니다.
- 메서드는 문자열에서 특정 문자열을 교체하여, 새로은 문자열을 반환합니다.


````javascript
{
// 01. 문자열로 대체하기
// 문자열을 사용해 대체하는 경우, 가장 첫 번째로 찾은 'searchValue'에 해당하는 부분만 'newValue'로 바뀝니다.
let text = "Hello, world!";
let newText = text.replace("world", "everyone");
console.log(newText);  // 출력: "Hello, everyone!"

// 02. 정규 표현식과 함께 사용하기
// 정규 표현식을 사용할 경우, g 플래그를 사용하여 문자열 전체에서 모든 일치하는 항목을 대체할 수 있습니다.
let text = "Repeat, repeat, repeat";
let newText = text.replace(/repeat/gi, "do");
console.log(newText);  // 출력: "Do, do, do"

// 03. 함수를 사용하여 대체하기
// newValue에 함수를 사용하는 경우, 각 일치 항목에 대해 이 함수가 호출되며, 함수의 반환값으로 해당 항목이 대체됩니다.
// 이 함수는 여러 인자를 받을 수 있으며, 일반적으로 다음과 같은 매개변수를 포함합니다:

let text = "John Smith";
let newText = text.replace(/(\w+) (\w+)/, function(match, p1, p2) {
    return `${p2}, ${p1}`; // 성과 이름의 위치를 바꿈
});
console.log(newText);  // 출력: "Smith, John"
}
````
`match`: 일치하는 전체 문자열
`p1, p2, ...`: 캡처된 그룹, 정규 표현식 내부의 괄호(())에 의해 캡처된 각 그룹
`offset`: 원본 문자열에서 일치하는 항목이 시작되는 인덱스
`string`: 원본 전체 문자열

<details>
<summary>결과 확인하기</summary>
<div>
"Hello, everyone!"<br>
"Do, do, do"<br>
"Smith, John"<br>
</div>

#### 04. 💛.search()
✔ 사용방식: string.search(regexp)
- 메서드는 문자열(정규식)을 검색하고, 위치값(숫자)을 반환합니다.
- 일치하는 부분이 없으면 -1을 반환합니다.
- 메서드는 문자열(정규식)을 검색하고, 위치값(숫자)을 반환합니다.

````javascript
{
// 01. 간단한 검색 예시: 
let text = "Hello, world!";
let index = text.search(/world/);
console.log(index);  // 출력: 7

// 02. 대소문자 구분 없이 검색 : 정규 표현식에 'i'플래그를 사용하면 대소문자를 구분하지 않고 검색할 수 있습니다.
let text = "Hello, World!";
let index = text.search(/world/i);
console.log(index);  // 출력: 7


//03. 글로벌 검색 플래그 g의 영향:
// .search() 메소드는 g 플래그의 영향을 받지 않습니다. 정규 표현식에 g 플래그가 있어도 첫 번째 일치 항목의 인덱스만 반환합니다.
let text = "Repeat, repeat, repeat";
let index = text.search(/repeat/g);  // 'g' 플래그는 무시됨
console.log(index);  // 출력: 8
}
````

<details>
<summary>결과 확인하기</summary>
<div>
7 7 8
</div>

#### 05. 💛💛.slice()
✔ 사용방법: arrayOrString.slice(start, end)<br>
📍 start: 추출을 시작할 인덱스입니다.<br>
이 인덱스 포함하여 그 이후의 요소들이 결과에 포함됩니다.<br>

📍end (선택적): 추출을 끝낼 인덱스입니다. 이 인덱스는 결과에 포함되지 않습니다.<br>
이 매개변수를 생략하면 배열이나 문자열의 끝까지 추출합니다.<br>
<br>

- 메서드는 문자열에서 시작 위치에서 종료 위치 값을 추출하여, 새로운 문자열을 반환합니다.
- 이 메서드는 원본 데이터를 수정하지 않고, 지정되 시작 인덱스부터 끝 인덱스 전까지의 요소들로 구성된 새로운 인스턴스를 생성합니다.
- .slice() 메소드는 데이터의 일부를 안전하게 추출할 필요가 있을 때 매우 유용합니다.
원본 데이터를 변경하지 않기 때문에, 원본 데이터의 무결성을 유지하면서 작업할 수 있다는 장점이 있습니다.

````javascript
{
// 01. 문자열에서 사용하기
let text = "Hello, world!";
console.log(text.slice(0, 5));  // 출력: 'Hello'
console.log(text.slice(7));     // 출력: 'world!'

// 02. 배열에서 사용하기
let numbers = [1, 2, 3, 4, 5];
console.log(numbers.slice(1, 3));  // 출력: [2, 3]
console.log(numbers.slice(-3));    // 출력: [3, 4, 5]
}
````
✅ 부연 설명<br>
01. 문자열에서 사용하기 <br>
첫 번째 예에서는 인덱스 0부터 5까지의 문자들을 추출하여 "Hello"를 반환합니다. 두 번째 예에서는 인덱스 7부터 문자열의 끝까지 추출하여 "world!"를 반환합니다.<br>
💡 end는 결과에 포함되지 않으므로 'Hello'뒤의 ','는 포함되지 않습니다.<br>
<details>
<summary>결과 확인하기</summary>
<div>
'Hello'<br>
'world!'<br>
'[2, 3]'<br>
'[3, 4, 5]'<br>
</div>
