---
layout: post
title: 자바스크립트 자료형
date: 2024-04-09 18:22 +0900
description: 
image: ../assets/img/Javascript.jpg
category: CSS
tags: CSS
published: true
sitemap: true
---
## <h1 style="color:#D86D6D">CSS</h1>

#### <h4 style="color:blue">선택자(selector)</h4>

<hr />

> 선택자란 ❓

선택자란 CSS로 UI의 어떤 부분을 디자인할지, 즉 표현할 대상이 되는 부분을 말합니다.

CSS로 속성을 부여하는 형식은 다음과 같습니다.

```css
h1 { color : red ; background : yellow ; }
````

h1: 선택자
color : 속성 / red : 속성값
background : 속성 / yellow : 속성값

✍🏼이 예문은 h1 요소에 배경색을 노란색으로, 글자색을 빨간색으로 지정한다는 의미를 담고있네요!

{}안에 여러 속성을 지정할 수 있고, 각 속성 설정 간에는 ";"로 구분해주며 마지막 속성 끝에는 구분을 생략할 수 있습니다.
속성은 가로로 붙여 써도 되고 다음과 같이 한 줄씩 따로 기술해도 됩니다.

````css
h1 {
    color: red;
    background: yellow;
}
````


> <h5 style="color:yellow">선택자의 종류(selector)</h5>
1️⃣ type 선택자 
html문서의 태그 이름을 선택자로 사용할 수 있습니다.

````css
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <title>type 선택자</title>
    <style type="text/css">
        p { color : blue; }
    </style>
</head>
<body>
    <p>머리가 좋아지는 음식<p>
</body>
</html>
````
이 경우 body태그 안의 '머리가 좋아지는 음식'의 색상이 파란색으로 표현됩니다.

<h6 style="color:blue">머리가 좋아지는 음식</h6>

