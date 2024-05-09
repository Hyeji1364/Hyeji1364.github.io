---
layout: post
title: GSAP 효과주기
date: 2024-05-09 21:00 +0900
description: GSAP Parallax 효과주기
image: ../assets/img/gsap.png
category: GSAP
tags: GSAP
published: true
sitemap: true
---

## GSAP

### Parallax 효과주기

<hr>

### 🎈 trigger

“trigger”는 GSAP에서 사용되는 용어 중 하나로, 특정 이벤트가 발생할 때 애니메이션을 시작하거나 제어하는 데 사용됩니다. 이것은 일반적으로 마우스 클릭, 마우스 오버, 스크롤, 시간 기반 이벤트 등과 같은 사용자 인터랙션 또는 요소의 특정 상태 변화에 반응하여 애니메이션을 시작하는 데 사용됩니다.

아래는 trigger를 사용한 애니메이션 예시입니다.

````javascript
gsap.to("#section01 .img", {
    duration: 2,
    x: 500,
    rotation: 360,
    borderRadius: 100,

    //화면에 보이면 바로 움직입니다.
    scrollTrigger: {
        trigger: "#section02 .img"
    }
});
````

이 코드는 GSAP의 to 메서드를 사용하여 #section01 .img 요소에 애니메이션을 적용하고, scrollTrigger를 사용하여 화면에 요소가 보이면 애니메이션을 시작하는 예시입니다. 


### 🎈toggleActions
toggleActions이라는 이 메서드는 스크롤 애니메이션을 위해 사용됩니다. 요소가 화면에 표시되는 동안 또는 사라지는 동안 발생하는 특정 동작을 지정할 수 있습니다.

````javascript
//toggleActions : 상황별 애니메이션 처리
gsap.to("#section02 .img", {
    duration: 2,
    x: 500,
    rotation: 360,
    borderRadius: 100,

    // onEnter, onLeave, onEnterBack, onLeaveBack
    // "play", "pause", "resume", "reset", "restart", "complete", "reverse", "none",
    scrollTrigger: {
        trigger: "#section02 .img",
        toggleActions: "play none reverse none",
    }
});
````

이 코드는 GSAP의 to 메서드를 사용하여 #section02 .img 요소에 애니메이션을 적용하고, scrollTrigger를 사용하여 화면에 요소가 보이면 애니메이션을 시작합니다. 또한 특정 상황에 따라 다른 애니메이션 동작을 설정하는 예시입니다.<br>
<br>
적용된 효과<br>

- toggleActions: 이 속성은 ScrollTrigger 플러그인을 사용하여 특정 상황에서 어떤 동작을 취할지를 설정합니다. 여기서 사용된 값은 “play none reverse none”입니다.<br>
- play: 요소가 뷰포트에 진입할 때 애니메이션을 재생합니다.
- none: 요소가 뷰포트를 벗어날 때 애니메이션을 중지하지 않고 유지합니다.
- reverse: 요소가 뷰포트를 벗어날 때 애니메이션을 역으로 되감습니다.

### 🎈scrub
스크럽 애니메이션에 사용되는 효과입니다.<br>
사용자가 애니메이션을 스크롤하면 해당 위치에 따라 애니메이션의 진행 상황이 조절됩니다.<br>

````javascript
gsap.to("#section03 .img", {
    duration: 5,
    x: 600,
    rotation: 360,
    borderRadius: 100,

    scrollTrigger: {
        trigger: "#section03 .img",
        markers: false,
        start: "top 50%",
        end: "bottom 10%",
        scrub: true    //  true  | number
    }
});
````
이 코드는 GSAP의 to 메서드를 사용하여 #section03 .img 요소에 애니메이션을 적용하고, scrollTrigger를 사용하여 화면에 요소가 보이면 애니메이션을 시작하고, 스크롤에 따라 애니메이션이 일어나는 정도를 조절하는 예시입니다. 여기서 추가된 부분은 다음과 같습니다:

scrub: 이 속성은 스크롤에 따라 애니메이션이 일어나는 정도를 조절합니다. 이 예제에서는 true로 설정되어 있으므로 스크롤에 따라 애니메이션이 부드럽게 진행됩니다.
true: 스크롤 위치에 따라 애니메이션이 부드럽게 진행됩니다.


