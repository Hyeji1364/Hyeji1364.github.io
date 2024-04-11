---
layout: post
title: jQuery 선택자
date: 2024-04-11 12:51 +0900
description: 
image: 
category: jQuery
tags: jQuery 선택자
published: true
sitemap: true
---

## jQuery


#### 선택자(selector)    

<hr />

jQuery 선택자의 형식
````css
$("선택자") | $("#gnb")
````

> 💟 기본 선택자

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

> 💟 속성 선택자