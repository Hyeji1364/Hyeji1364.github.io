---
layout: post
title: 메뉴유형
date: 2024-04-19 04:30 +0900
description: 
image: 
category: 웹디자인기능사
tags: 웹디자인기능사 메뉴유형
published: true
sitemap: true
---

## 메뉴 유형

웹디자인 기능사 준비중 메뉴 유형을 만드는 과정을 설명해 볼 예정입니다.
메뉴 유형 중 하나로 자주 사용되는 드롭다운 메뉴를 예로 들어 설명해보겠습니다.

<hr />

📗 드롭다운 메뉴 만들기

드롭다운 메뉴는 웹사이트에서 흔히 사용되는 네비게이션 메뉴 유형 중 하나로, 사용자가 메뉴 항목에 마우스를 ㅇ로렸을 때 추가적인 메뉴 옵션이 나타나는 방식입니다.

> 1️⃣ HTML 주고

드롭다운 메뉴의 HTML은 기본적으로 중첩된 리스트 ('ul'과 'li'태그)를 사용하여 구성됩니다.
다음은 간단한 드롭다운 메뉴의 HTML 구조 예시입니다.

````html
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <title>드롭다운 메뉴 예제</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <nav class="navbar">
        <ul class="nav-menu">
            <li><a href="#">메인</a></li>
            <li>
                <a href="#">서비스</a>
                <ul class="dropdown">
                    <li><a href="#">웹 디자인</a></li>
                    <li><a href="#">웹 개발</a></li>
                    <li><a href="#">그래픽 디자인</a></li>
                </ul>
            </li>
            <li><a href="#">프로젝트</a></li>
            <li><a href="#">연락처</a></li>
        </ul>
    </nav>
</body>
</html>
````
<br>

> 2️⃣ CSS 스타일링

CSS를 사용하여 메뉴의 시각적인 부분을 꾸미고, 드롭다운 효과를 구현합니다. :hover 선택자를 사용하여 메뉴에 마우스를 올렸을 때 드롭다운 메뉴가 나타나도록 설정합니다.

````css
/* 기본 네비게이션 바 스타일 */
.navbar {
    background-color: #333;
    overflow: hidden;
}

/* 네비게이션 메뉴 항목 스타일 */
.nav-menu > li {
    float: left;
    list-style-type: none;
}

/* 모든 링크 스타일 */
.nav-menu a {
    display: block;
    padding: 14px 20px;
    color: white;
    text-decoration: none;
}

/* 드롭다운 메뉴 숨김 */
.dropdown {
    display: none;
    position: absolute;
    background-color: #f9f9f9;
    min-width: 160px;
    box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
    z-index: 1;
}

/* 드롭다운 메뉴 스타일 */
.dropdown a {
    color: black;
    padding: 12px 16px;
    text-decoration: none;
    display: block;
    text-align: left;
}

/* 드롭다운 메뉴 보이기 */
.nav-menu li:hover .dropdown {
    display: block;
}

````

<br>

이 CSS 코드는 기본 네비게이션 메뉴 스타일을 설정하고, 드롭다운 메뉴를 마우스 오버 시 보이게 만듭니다. 메뉴 항목에 마우스를 올리면 드롭다운 메뉴가 나타나며, 마우스를 치우면 사라집니다.

웹디자인기능사 실기 시험을 준비할 때 메뉴유형 또한 기본적이며 중요한 요소이므로 그 구조를 이해하는 것이 중요합니다. 😉

