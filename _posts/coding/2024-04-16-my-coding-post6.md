---
layout: post
title: jQuery를 이용한 이미지 슬라이드
date: 2024-04-12 3:36 +0900
description: 
image: ../assets/img/jquery.jpg
category: jQuery
tags: jQuery 이미지슬라이드 CSS
published: true
sitemap: true
---

## 이미지 슬라이드


이미지 슬라이드는 여러 개의 이미지를 슬라이드 효과로 볼 수 있는 기능입니다.
웹사이트나 블로그에서 많이 사용되며, 사용자에게 시각적인 흥미와 정보를 제공할 수 있습니다.

<hr />

> #### 🔍 이미지 슬라이드 활용 사례

🎈 메인 페이지 배너
웹사이트의 메인 페이지에서 주요 콘텐츠를 슬라이드로 보여줄 수 있습니다.
<br>
🎈 포트폴리오 및 갤러리
작품이나 이미지를 슬라이드로 효과적으로 전시할 수 있습니다.
<br>
🎈 프로모션 및 광고
다양한 제품이나 서비스를 슬라이드로 소개할 수 있습니다.

<br>

🗯 현재 나의 경우, 웹디자인기능사 실기를 준비하고 있는데, 이때 이미지 슬라이드를 구현하는 기능을 사용해야 해서 이미지 슬라이드를 써야한다.

이 외에도 포트폴리오에도 이미지 슬라이드를 활용할 수 있어 이미지 슬라이드는 많이 활용될 것 같은 기능이다!

일단 이미지 슬라이드를 배우면서 Jquery로 사용하는것이 훨씬 간단하다고 생각되어 오늘은 Jquery로 이미지 슬라이드를 구현하는 방법에 대해 알아볼 것이다.

> #### ✏ Jquery를 통한 이미지 슬라이드 구현

<br>

> ###### 1️⃣ 구조 설정

이미지 슬라이드를 표시할 영역을 <div>요소로 감싸고, 각 이미지를 <img>태그로 추가합니다.

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