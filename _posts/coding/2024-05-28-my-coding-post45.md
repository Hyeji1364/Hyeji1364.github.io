---
layout: post
title: 제이쿼리 메서드 attr(), prop() 차이
date: 2024-05-28 10:00 +0900
description: 제이쿼리 메서드 attr(), prop() 차이
image: ../assets/img/jquery01.png
category: Jquery
tags: Jquery attr() prop() 
published: true
sitemap: true
---

# JQEURY

## JQUERY 메서드 중 attr(), prop() 차이

오늘은 자바스크립트의 `attr()`과 `prop()` 메서드의 차이점에 대해 알아보겠습니다.<br>
attr()와 prop() 메서드는 jQuery에서 HTML 요소의 속성(attribute)과 프로퍼티(property)를 다루기 위해 사용되며, 이 두 메서드는 서로 비슷하게 보이지만 중요한 차이점이 있습니다.<br>
다음은 이 두 메서드의 공통점과 차이점에 대해 알아보겠습니다.
<br>

### 공통점 🔍
01. 역할
- 두 메서드 모두  HTML 요소의 특성을 가져오거나 설정하는 데 사용됩니다.
<br>

02. 사용방법
- 둘 다 값을 가져올 때와 설정할 때 동일한 구문을 사용합니다.

````javascript
// 값을 가져올 때
var value = $('selector').attr('attributeName');
var value = $('selector').prop('propertyName');

// 값을 설정할 때
$('selector').attr('attributeName', value);
$('selector').prop('propertyName', value);
````
<br>

03. 인수
- 두 메서드 모두 첫 번째 인수로 속성 또는 프로퍼티의 이름을 받고, 두 번째 인수로 설정할 값을 받습니다.
<br>

### 차이점 🪕
01. 동작 대상
- attr(): <span style="color:red">HTML 속성(attribute)</span>을 대상으로 합니다.
- prop(): <span style="color:red">DOM 프로퍼티(property)</span>를 대상으로 합니다.
<br>

02. 일반적인 사용 사례
- attr(): HTML 요소의 <span style="color:red">정적 속성(예: src, href, id)</span>을 다루는 데 사용됩니다.
- prop(): HTML 요소의 <span style="color:red">상태와 관련된 동적 속성(예: checked, disabled, selected)</span>을 다루는 데 사용됩니다.
<br>

03. 반환 값
- attr(): 문자열을 반환합니다.
- prop(): 대부분의 경우, 프로퍼티의 실제 자료형(boolean, number, object 등)을 반환합니다.

##  예제 비교 🔍

### 01. checked 속성:
````javascript
// attr()을 사용하여 checked 설정
$('input[type="checkbox"]').attr('checked', 'checked');
console.log($('input[type="checkbox"]').prop('checked')); // false일 수 있음

// prop()을 사용하여 checked 설정
$('input[type="checkbox"]').prop('checked', true);
console.log($('input[type="checkbox"]').prop('checked')); // true
````
<br>

### 02. src 속성:
````javascript
// attr()을 사용하여 src 설정
$('img').attr('src', 'newimage.jpg');
console.log($('img').attr('src')); // 'newimage.jpg'

// prop()을 사용하여 src 설정
$('img').prop('src', 'newimage.jpg');
console.log($('img').prop('src')); // 'newimage.jpg' (같은 결과)
````
좋은 지적입니다. src 속성을 다룰 때, attr() 메서드와 prop() 메서드 모두 사용 가능하지만, 기술적으로 차이가 있습니다.<br>
일반적으로 src와 같은 HTML 속성은 attr() 메서드를 사용하는 것이 더 맞습니다.<br>
그러나 두 메서드 모두 같은 결과를 반환하는 이유는 src 속성이 DOM 프로퍼티로도 존재하기 때문입니다.

### src 속성을 사용할 때의 차이점
- attr() 사용: src 속성은 HTML 마크업에 정의된 속성을 그대로 읽거나 설정합니다. 즉, HTML 태그에 직접적으로 영향을 줍니다.
- prop() 사용: src 속성은 DOM 요소의 속성으로 취급됩니다. 이 속성은 자바스크립트 객체로서의 요소에 영향을 줍니다.
<br>

### 왜 같은 결과가 나올까요? 🤔 
src와 같은 속성은 HTML 속성이면서 동시에 DOM 프로퍼티입니다.<br>
attr()과 prop() 모두 이 속성에 접근하고 설정할 수 있으며, 대부분의 경우 결과는 유사합니다.<br>
그러나, 그 반환 값이 절대 경로로 변환된다는 점과 실제로 브라우저가 어떻게 해석하는지에 따라 차이가 발생할 수 있습니다.

### ✅ 차이점 요약
- 절대 경로 vs 상대 경로: attr()은 설정한 그대로의 값을 반환하지만, prop()은 브라우저가 해석한 절대 경로를 반환할 수 있습니다.
- HTML vs DOM: attr()은 HTML 마크업 속성을 다루고, prop()은 DOM 프로퍼티를 다룹니다.


요약하자면, attr()과 prop()은 HTML 요소의 특성을 다루는 데 사용되지만, attr()은 HTML 속성을, prop()은 DOM 프로퍼티를 다룬다는 점에서 차이가 있습니다.<br>
HTML 요소의 상태와 관련된 속성을 다룰 때는 prop()을 사용하는 것이 더 적합합니다.
<br>

결론적으로, HTML 속성을 설정하거나 읽을 때는 attr()을 사용하는 것이 더 직관적이며, DOM 요소의 상태를 다룰 때는 prop()을 사용하는 것이 더 적합합니다.<br>
src 속성의 경우, 두 방법 모두 사용 가능하지만, attr()이 더 일반적으로 사용됩니다.
 
