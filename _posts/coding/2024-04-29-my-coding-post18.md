---
layout: post
title: 자바스크립트 오답정리 (3)
date: 2024-04-28 20:24 +0900
description: 자바스크립트 오답정리
image: ../assets/img/Javascript.jpg
category: Javascript
tags: javascript 자바스크립트
published: true
sitemap: true
---

## 자바스크립트

### 오답정리

<hr>

오늘은 자바스크립트 오답정리(2)에 이어 나머지 10문제도 풀어볼 예정입니다.
자바스크립트 오답정리(2)와 이어지는 내용입니다!

### 문제11
<hr>
다음을 보고 결괏값을 작성하시오!

````javascript
{
        let a, b, result;
        a = 7, b = 4
        result = a | b;
    
        console.log(result)
}
````

이 코드는 JavaScript에서 두 변수 a와 b의 비트 OR 연산(|)을 수행합니다. 여기서 변수 a는 7로, b는 4로 초기화되어 있습니다.

비트 OR 연산은 두 정수의 이진 표현에서 비트 단위로 수행되며, 두 입력 비트 중 적어도 하나가 1이면 결과 비트가 1이 됩니다. 구체적인 계산은 다음과 같습니다.

1) 이진수 변환: <br>
* a = 7 의 이진 표현: 0111<br>
* b = 4 의 이진 표현: 0100
<br>

2) 비트 OR 연산: <br>
* 0111(7) <br>
* 0100(4) <br>
* 위 두 이진수에 대해 비트 OR 연산을 수행하면, 각 비트 위치별로 OR 연산을 적용합니다.

````markdown
0111
| 0100
------
0111
````

3) 이진수 결과를 십진수로 변환: <br>
* 이진수 0111은 십진수로 변환하면 7입니다.
<br>

따라서, console.log(result)에서 <mark>출력되는 값은 7입니다.</mark>

<br>

### 문제12
<hr>
다음을 보고 결괏값을 작성하시오!

````javascript
{
        function solution(a, b, c){
                let answer = "YES", max;
                let total = a + b + c;
        
                if(a > b) max = a;
                else max = b;
                if(c > max) max = c;
                if(total-max <= max) answer = "NO"; 
                
                return answer;
        }
    
        console.log(solution(53, 93, 107));
}
````

이 코드는 세 개의 수 a, b, c를 인수로 받아, 이 수들을 변으로 하는 삼각형이 만들어질 수 있는지를 판단하는 JavaScript 함수 solution입니다. 삼각형의 성립 조건은 어느 한 변의 길이가 다른 두 변의 길이의 합보다 작아야 합니다. 코드의 로직은 다음과 같습니다:

1) 변수 초기화: <br>
* answer는 기본적으로 "YES"로 설정되어 있습니다. 이는 기본적으로 삼각형이 성립한다고 가정합니다.<br>
* max는 세 변 중 가장 긴 변의 길이를 저장하는 데 사용됩니다.<br>
* total은 세 변의 길이 합을 저장합니다.
<br>

2) 가장 긴 변 찾기:
* a, b, c 중에서 가장 큰 값을 max에 할당합니다.
<br>

3) 삼각형 성립 조건 검사:<br>
* total - max는 가장 긴 변을 제외한 두 변의 길이 합입니다.<br>
* 삼각형의 성립 조건은 가장 긴 변의 길이가 다른 두 변의 길이 합보다 작아야 합니다.<br>
* if(total-max <= max) answer = "NO";는 이 조건을 만족하지 않을 경우, 즉 가장 긴 변의 길이가 다른 두 변의 길이 합보다 크거나 같은 경우에 "NO"를 반환합니다.
<br>

4) 특정 입력 값에 대한 결과: <br>
* solution(53, 93, 107)을 호출하면, 가장 긴 변 max는 107입니다. <br>
* 다른 두 변의 합 total - max는 53 + 93 + 107 - 107 = 146입니다. <br>
* 146 (다른 두 변의 합)는 107 (가장 긴 변)보다 크므로 삼각형의 성립 조건을 만족합니다. <br>
* 따라서 answer = "YES"가 유지되고, 이 값이 반환됩니다.

🎈 답
<mark>console.log(solution(53, 93, 107));의 출력은 "YES"입니다. </mark>
이는 제공된 변의 길이로 삼각형을 만들 수 있음을 의미합니다.

