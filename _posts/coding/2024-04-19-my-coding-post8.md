---
layout: post
title: 탭 메뉴
date: 2024-04-19 12:00 +0900
description: 
image: ../assets/img/tagimg.gif
category: 웹디자인기능사
tags: Tabmenu 웹디자인기능사
published: true
sitemap: true
---

## 탭메뉴

탭메뉴를 만드는것 또한 자바스크립트와 제이쿼리를 이용할 수 있는데, 여기서는 제이쿼리를 이용한 탭메뉴 만들기에 대해 다뤄볼 예정입니다.

<br>
제이쿼리를 사용하여 탭 메뉴를 만드는 것은 사용자 인터페이스에서 자주 사용되는 기능 중 하나입니다. 탭 메뉴를 사용하면 사용자가 한 화면에서 여러 섹션의 컨텐츠를 쉽게 탐색하고 전환할 수 있습니다.

웹디자인기능사 실기를 준비하고 있기 때문에 기능에 맞는 탭 메뉴 설정하기에 대해 알아볼 예정입니다 ☺ 

<hr />

현재 저는 웹디자인기능사 실기 F-1 유형 '주식회사 기능건설'에 대해 다루었고 코드를 분석하면서 공부해보겠습니다!

F유형은 이번에 새로 나온 유형이라고 합니다.


> 1️⃣ HTML 요소 선택

탭 메뉴와 관련된 HTML 요소들을 제이쿼리를 통해 선택합니다. 탭 버튼('li' 요소)과 각 탭에 해당하는 컨텐츠('div'요소)를 선택하는 과정입니다.

````javascript
const tabBtn = $(".notice .title > ul > li");  // 탭 버튼 설정
const tabCont = $(".notice .cont > div");      // 콘텐츠 설정
````

2️⃣ 초기 콘텐츠 설정

````javascript
tabCont.hide().eq(0).show();
````
초기에 페이지가 로드될 때, 모든 탭 컨텐츠를 숨기고 ('hide()')첫번째 탭 컨텐츠만 보이게 ('show()') 설정합니다. 이렇게 함으로써 사용자에게 초기에 보여질 컨텐츠를 제공하며, 나머지는 숨겨진 상태로 유지됩니다.

3️⃣ 클릭 이벤트 핸들러 추가

각 탭 버튼에 클릭 이벤트 핸들러를 추가합니다.
이 핸들러는 사용자가 탭 버튼을 클릭했을 때 실행됩니다. 클릭된 탭의 인덱스를 사용하여 해당 탭에만 특정 클래스를 적용하고, 해당하는 탭 컨텐츠를 보이게 하며, 다른 탭 컨텐츠는 숨깁니다.

````javascript
tabBtn.click(function (e) {
    const index = $(this).index();  // 클릭된 버튼의 인덱스

    $(this).addClass("active").siblings().removeClass("active");  // 'active' 클래스 추가 및 제거
    tabCont.eq(index).show().siblings().hide();  // 해당 인덱스의 콘텐츠 보이기, 다른 콘텐츠 숨기기
});

````

sibling은 형제라는 뜻을 가지고 있는데, 여기서는 

![image](https://github.com/Hyeji1364/class2024/assets/161557112/12666e5c-3cc5-42a1-a377-309211c3ffa5)

공지사항과 갤러리가 동일 선상에 있는 메뉴이기 때문에 사용한 것이라고 생각하면 됩니다!

그럼 여기서 탭 메뉴에 대한 설명을 마치겠습니다 👋🏼


