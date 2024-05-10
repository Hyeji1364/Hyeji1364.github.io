---
layout: post
title: Javascript 메서드 정리 (1) - 문자열 객체
date: 2024-05-06 09:10 +0900
description: 자바스크립트 메서드 
image: ../assets/img/Javascript.jpg
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

✔ 사용방법 : string.includes(searchString, position)

- searchString: 문자열에서 찾고자 하는 부분 문자열입니다.<br>
- position (선택적): 검색을 시작할 위치를 지정합니다. 기본값은 0입니다.<br>
- 메서드는 문자열 포함 여부를 검색하여, 불린(true, false)을 반환합니다.<br>
- 대소문자를 구별합니다.<br>
- 문자열이 포함되어 있으면 'true'를 그렇지 않으면 'false'를 반환합니다.<br>
- 검색하려는 요소를 첫번째 매개변수로 지정하고, 검색을 시작할 위치를 두 번째 매개변수로 선택적으로 지정할 수 있습니다.<br>

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
</div>
</details>

<br>

#### 02. 💛.indexOf()
✔ 사용방법: string.indexOf(searchValue, fromIndex)

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
<summary>결과 확인하기</summary>
<div>
7<br>
0<br>
4<br>
-1<br>
8<br>
</div>
</details>

#### 03. 💛match()
✔ 사용방법: string.match(regexp)
- 지정한 숫자(index)를 받아, 문자열에서 해당되는 인덱스의 요소를 반환합니다.
- 'regexp':일치를 찾기 위해 사용할 정규 표현식입니다.
- 일치하는 결과가 없으면 'null'을 반환합니다.
- 일치하는 결과가 있으면, 결과 배열을 반환합니다.
- 배열의 각 요소는 일치하는 문자열을 나타냅니다.
- 여기서 주어진 문자열은 "javascript reference"이며, at() 함수에 인덱스를 전달하여 해당 인덱스에 해당하는 문자를 반환합니다.
- 'index'는 일치가 발견된 시작위치이며, 'input'은 원본 문자열을 포함합니다.

````javascript
{
// 01. 기본 사용 예시
let text = "The quick brown fox jumps over the lazy dog.";
let regex = /quick/;
console.log(text.match(regex));
// 출력: ['quick', index: 4, input: 'The quick brown fox jumps over the lazy dog.', groups: undefined]

// 02. 글로벌 검색 : 정규 표현식에 'g'플래그(글로벌검색)를 사용하면 문자열 전체에서 모든 일치 항목을 찾아 배열로 반환합니다.
let text = "Repeat repeat repeat";
let regex = /repeat/gi;     // 'g'는 글로벌 검색, 'i'는 대소문자 구분 없이 검색
console.log(text.match(regex));
// 출력: ["Repeat", "repeat", "repeat"]

// 03.캡처 그룹:
괄호를 사용해 캡처 그룹을 정의하면, 그룹별로 일치하는 부분을 배열 내부에서 별도로 접근할 수 있습니다.
let text = "John: 34, Sarah: 32";
let regex = /(\w+): (\d+)/g;        //'(\w+)'는 문자열을, '(\d+)'는 숫자를 각각 캡처
let matches;
while ((matches = regex.exec(text)) !== null) {
  console.log(`${matches[1]} is ${matches[2]} years old.`);
}
// 출력: "John is 34 years old."
// 출력: "Sarah is 32 years old."
}
````
<details>
<summary>결과 확인하기</summary>
<div>
['quick', index: 4, input: 'The quick brown fox jumps over the lazy dog.', groups: undefined] <br>
["Repeat", "repeat", "repeat"]<br>
"John is 34 years old."<br>
"Sarah is 32 years old."<br>
</div>
</details>

✅ 부연 설명<br>
02. 글로벌검색 <br>
이 예시에서는 "repeat"라는 단어를 대소문자 구분 없이 (i 플래그 덕분에) 전체 텍스트에서 모두 찾아내어 결과 배열에 저장합니다.<br>
각각의 일치하는 부분이 배열의 요소로 반환됩니다.<br>

03. 캡쳐 그룹<br>
이 예시에서 (\w+)는 이름(문자열)을, (\d+)는 나이(숫자)를 각각 캡처합니다.<br>
regex.exec(text)를 사용하여 반복적으로 일치하는 정보를 찾고, matches 배열에서 matches[1]과 matches[2]로 각각 이름과 나이를 추출하여 출력합니다.<br>



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
</details>

#### 05. 💛.search()
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
</details>

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
</details>