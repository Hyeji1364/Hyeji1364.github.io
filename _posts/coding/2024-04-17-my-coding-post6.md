---
layout: post
title: 이미지 슬라이드
date: 2024-04-17 17:37 +0900
description: 
image: ../assets/img/image.jpg
category: jQuery
tags: jQuery 선택자
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

> #### ✏ jQuery를 통한 이미지 슬라이드 구현

<br>

> ###### 1️⃣ HTML 구조 설정

이미지 슬라이드를 표시할 영역을 <div>요소로 감싸고, 각 이미지를 img 태그로 추가합니다.

````html
<div class="slideshow-container">
    <div class="slide"><img src="img1.jpg" alt="이미지 1"></div>
    <div class="slide"><img src="img2.jpg" alt="이미지 2"></div>
    <!-- 추가 이미지 -->
</div>
````
<br>

 > ###### 2️⃣ CSS스타일링

 슬라이드 컨테이너와 이미지에 대한 스타일을 CSS로 지정합니다.

 ````css
 .slideshow-container {
    position: relative;
    width: 100%;
    height: 400px; /* 슬라이드 높이 조정 */
}

.slide {
    position: absolute;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    display: none; /* 초기에는 모든 슬라이드를 숨깁니다. */
}

.active {
    display: block; /* 활성화된 슬라이드만 표시됩니다. */
}
````
<br>

###### 3️⃣ jQuery로 슬라이드 기능 추가

jQuery를 사용하여 이미지 슬라이드를 제어하는 스크립트를 작성합니다.

````javascript
$(document).ready(function() {
    // 초기 상태 설정
    $(".slide").eq(0).addClass("active");

    // 이미지 슬라이드 함수
    function slide() {
        var currentSlide = $(".active");
        var nextSlide = currentSlide.next(".slide");

        // 마지막 슬라이드일 경우 첫 번째 슬라이드로 이동
        if (nextSlide.length === 0) {
            nextSlide = $(".slide").eq(0);
        }

        // 현재 활성화된 슬라이드를 서서히 투명하게 만들고 다음 슬라이드를 서서히 나타나게 함
        currentSlide.fadeOut(1000).removeClass("active");
        nextSlide.fadeIn(1000).addClass("active");
    }

    // 3초마다 슬라이드 호출
    setInterval(slide, 3000);
});
````

위 코드는 각 이미지를 3초 간격으로 자동으로 전환하는 기본적인 이미지 슬라이드쇼를 만드는 방법입니다.
여기서는 각 슬라이드를 페이드 인/아웃 효과로 구현했습니다.


그럼 추후에는 자바스크립트로 이미지 슬라이드 만들기에 대해서도 가져오겠습니다... Coming soon... 




