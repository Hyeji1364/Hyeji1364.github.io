---
layout: post
title: jQuery 선택자
date: 2024-04-12 3:36 +0900
description: 
image: ../assets/img/jquery.png
category: jQuery
tags: jQuery 선택자
published: true
sitemap: true
---

## jQuery


### 선택자(selector)

jQuery 선택자는 HTML 요소를 선택하고 조작하는 강력한 방법을 제공합니다.
기본 선택자부터 복잡한 선택자까지 다양한 유형이 있으며, 이를 통해 웹 페이지의 동적인 상호작용을 구현할 수 있습니다.

<hr />

> #### 💟 기본 선택자

|선택자 종류||설명|
|------|---|---|
|태그 선택자|$("p")|p 요소를 선택합니다.|
|id 선택자|$("#gnb")|#gnb요소를 선택합니다.|
|class 선택자|$(".logo")|logo인 요소를 선택합니다.|
|자식 선택자|$(".logo > ul > li")|#gnb의 자식 요소의 자식 요소 li를 선택합니다.|
|하위 선택자|$(".gnb ul")|#gnb의 하위에 있는 모든 ul 요소를 선택합니다.|
|인접 선택자|$("#visual + #content")|#visual 다음에 오는 #content 요소를 선택합니다.|
|형제 선택자|$("#visual ~ #footer")|#visual의 형제 요소 #footer를 선택합니다.|
|종속 선택자|$(".logo")|logo인 요소를 선택합니다.|
|그룹 선택자|$(".left, .rihgt, #banner")|.left, rigth, #banner 요소들을 선택합니다.|
|전체 선택자|$("*")|모든 요소를 선택합니다.|

<br>

> #### 💟 기본 선택자

|선택자 종류||설명|
|------|---|---|
|요소[속성]|$("span[class]")|span 요소 중 class 속성을 가지고 있는 요소를 선택합니다.|
|요소[속성='값']|$("span[class='abc']")|span 요소 중 class가 'abc'인 요소를 선택합니다.|
|요소[속성!='값']|$("span[class!='abc']")|span 요소 중 class가 'abc'가 아닌 요소를 선택합니다.|
|요소[속성~='값']|$("span[class~='abc']")|span 요소 중 class가 'abc'를 포함하는 요소를 선택합니다.'abc' 앞뒤로 연결된 문자가 없어야 합니다. 'bg abc'는 선택되나 'bg_abc'는 선택되지 않습니다.|
|요소[속성*='값']|$("span[class*='abc']")|span 요소 중 class가 'abc'를 포함하는 요소를 모두 선택합니다. 'bg abc','bg_abc' 모두 선택합니다.|
|요소[속성^='값']|$("span[class^='abc']")|span 요소 중 class가 'abc'로 시작하는 요소를 선택합니다.|
|요소[속성$='값']|$("span[class$='abc']")|span 요소 중 class가 'abc'로 끝나는 요소를 선택합니다.|

<br>

> #### 💟 필터 선택자

선택자에 ':'이 붙은 선택자를 필터 선택자라고 합니다.

✅ tr : table row의 약자로, 태이블의 한 행을 나타냅니다.

✅td : table data의 약자로, 테이블의 데이터 셀을 나타냅니다.

✅th : table header의 약자로, 테이블의 헤더 셀을 나타냅니다.
주로 테이블의 제목이나 카테고리를 표시하는데 사용됩니다.

* 필터 선택자의 종류

|선택자 종류||설명|
|------|---|---|
|:even|$("tr:even")|tr 요소 중 짝수 행만 선택합니다.|
|:odd|$("tr:odd")|tr 요소 중 홀수 행만 선택합니다.|
|:first|$("td:first")|tr 요소 중 짝수 행만 선택합니다.|
|:last|$("td:last")|마지막 td 요소를 선택합니다.|
|:header|$(":header")|헤딩(h1~h6) 요소를 선택합니다.|
|:eq()|$("li:eq(0)")|index가 0인 li 요소를 선택합니다. index는 0번이 첫 번째 요소입니다.|
|:gt()|$("li:gt(0)")|index가 0보다 큰 li 요소들을 선택합니다.|
|:lt()|$("li:lt(2)")|index가 2보다 작은 li 요소들을 선택합니다.|
|:not()|$("li:not(.bg)")|li 요소 중에서 class명 bg가 아닌 li 요소를 선택합니다.|
|:root|$(":root")|html을 의미합니다.|
|:animated|$(":animated")|움직이는 요소를 선택합니다.|


##### 😊 자식 필터 선택자

자식 필터 선택자 중 'child'가 붙은 선택자는 요소가 순차적으로 나열되어 있을 때 사용하고, 'of-type'이 붙은 선택자는 요소가 순차적으로 나열되어 있지 않아도 동일 요소이면 선택이 가능합니다.

|선택자 종류||설명|
|------|---|---|
|:first-child|$("span:first-child")|첫 번째 span 요소를 선택합니다.|
|:last-child|$("span:last-child")|마지막 span 요소를 선택합니다.|
|:first-of-type|$("span:first-of-type")|span 요소 중에서 첫 번째 span 요소를 선택합니다.|
|:last-of-type|$("span:last-of-type")|첫 번째 span 요소를 선택합니다.|
|:first-child|$("span:first-child")|첫 번째 span 요소를 선택합니다.|
|:nth-child|$("span:nth-child(2)")|두 번째 span 요소를 선택합니다.nth-child(2n)은 2,4,6..번째 요소를 선택하고, nth-child(2n+1)은 1,3,5.. 번째 요소를 선택합니다.|
|:nth-last-child|$("span:nth-last-jchild(2)")|마지막에서 두 번째 span 요소를 선택합니다.|
|:nth-of-type|$("span:nth-of-type(2)")|span 요소 중에서 두 번째 span 요소를 선택합니다.|
|:nth-last-of-type|$("span:nth-last-of-type(2)")|span 요소 중에서 마지막에서 두 번째 span 요소를 선택합니다.|
|:only-child|$("div > span:only-child")|div의 자식 요소에서 오직 span요소가 하나만 있는 span 요소를 선택합니다.|
|:only-of-type|$("div > span:only-of-type")|div의 자식 요소에서 span요소가 하나만 있는 span 요소를 선택합니다.|

<br>

> #### 💟 탐색 선택자

* ##### 기본 탐색 선택자

|선택자 종류||설명|
|------|---|---|
|children()|$(("div").children)|div 요소의 자식 요소를 선택합니다.|
|parent()|$("p").|parent()|$(("p").children)|p요소의 부모 요소를 선택합니다.|
|parents()|$("p").parent("div")|p요소의 부모가 되는 모든 div 요소를 선택합니다.|
|closest()|$("p").slosest("div")|p요소의 부모가 되는 첫 번째 div 요소를 찾습니다.|
| next()|$("div.m").next()|div.m요소의 다음 요소를 선택합니다.|
|filter()|$("div").filter(".m")|div 요소 중 class가 "m"인 요소를 선택합니다.|
|eq()|$("div").eq(0)|div 요소 중 index가 0인 요소를 선택합니다. index 0번은 첫 번째 요소입니다.|
|gt()|$("div").gt(0)|index가 0보다 큰 div 요소들을 선택합니다.|
|lt()|$("div").lt(3)|index가 3보다 작은 div 요소들을 선택합니다.|

* ##### 기타 탐색 선택자

|선택자 종류|설명|
|------|---|
|add()|$("div").add("p") <br> div 요소와  p요소를 선택합니다.|
|addBack()|$("div").children("p").addBack() <br> p 요소와 이전 선택요소 div를 선택합니다.|
|end()|$("div").find("span").css(...).end().find("em".css(...)) <br> $("div").find("span").css(...) 의 실행이 끝나면 처음 선택자 $("div")로 다시 돌아와 $("div").find("em").css(...)가 실행됩니다.|
|is()|선택한 요소를 판별해 주는 선택자로 보통 if문의 조건식에 사용됩니다.<br> if("div").children().is("p"){<br>console.log("p 요소가 맞습니다.");<br>}|