---
layout: post
title: CSS
date: 2024-04-24 23:20 +0900
description: 기타 CSS 속성
image: ../assets/img/blogcss.gif
category: blog
tags: CSS 2D transform transitions
published: true
sitemap: true
---

## 🔊 기타 CSS 속성

오늘은 기타 CSS속성에 대해 알아보겠습니다.
2D transform, transitions, animation 속성에 대해 알아보겠습니다.

> #### 📍 이차원 변형(2D transform)

CSS에서는 박스를 회전(rotate), 확대 축소(scale), 이동(translate), 찌그러뜨리기(skew)할 수 있습니다.


|속성 값|속성 설명|
|------|---|
|translate|- 우측으로 20px, 아래로 30px 이동<br> - translateX(), translateY() 둘로 사용 가능|
|rotate(30deg)|30도 회전|
|scale(0.7, 1.3)|가로 70%로 축소, 세로 130% 확대 <br> scaleX(), scaleY() 둘로 사용 가능|
|skew(30deg, 20deg)|- 가로 30도 찌그러뜨림, 세로 20도 찌그러뜨림<br> - skewX(), skewY() 둘로사용 가능|
|matrix(1, -0.3, 0, 1, 0 , 0)|scaleX(), skewY, skewX(), scaleY, translateX(), translateY()와 같은 순서대로 한꺼번에 적용함|
<br>

> #### 📍 속성 전환(transitions)

CSS에서 transition 속성은 요소의 상태 변화를 부드럽고 자연스럽게 표현할 수 있게 해 줍니다. 이를 통해 CSS 속성의 값이 시간에 따라 점진적으로 변경될 수 있도록 설정할 수 있습니다.
transition 속성은 웹 페이지에 시각적 효과를 추가하여 사용자 경험을 향상시키는 데 유용합니다.

* transition-property: 변화를 적용할 CSS 속성의 이름을 지정합니다. all이 기본값이며, 모든 속성에 트랜지션 효과를 적용합니다.

* transition-duration: 트랜지션 효과가 완료되는 데 걸리는 시간을 지정합니다. 초(s) 또는 밀리초(ms) 단위로 설정합니다.

* transition-timing-function: 트랜지션의 속도 곡선을 정의합니다. 예를 들어 linear, ease, ease-in, ease-out, ease-in-out 등이 있습니다.

* transition-delay: 트랜지션 효과가 시작되기 전의 지연 시간을 설정합니다.

````css
#myButton {
    background-color: blue;
    color: white;
    padding: 10px 20px;
    border: none;
    transition: background-color 0.5s ease;
}

#myButton:hover {
    background-color: red;
}
````
위의 예시에서는 #myButton이라는 ID를 가진 버튼에 대해 설명합니다. 이 버튼의 배경색은 기본적으로 파란색입니다. 버튼에 마우스를 올려놓을 때(:hover 상태), 배경색이 빨간색으로 부드럽게 변합니다. transition 속성을 사용하여 이 색상 변화가 0.5초 동안 일어나며, 변화 곡선은 ease로 설정되어 있어 시작과 끝에서는 천천히, 중간에는 빠르게 변화합니다.

<br>

> #### 📍 애니메이션 (animation) 속성
CSS에서 'animation' 속성은 요소에 복잡한 애니메이션을 적용할 수 있게 해줍니다.
'transition'과 비교했을 때, 'animation'은 특정 시간 간격에 걸쳐 여러 단계의 스타일 변경을 정의할 수 있으며, 더 복잡하고 다양한 효과를 만들 수 있습니다.

### Animation 속성 구성
CSS 애니메이션은 주로 두 부분으로 구성됩니다.

'@keyframes` 규칙과 애니메이션 관련 속성들입니다.

💞 @keyframes 규칙: 애니메이션 중에 발생하는 중간 스타일을 정의합니다. 0%에서 100%까지의 범위로, 애니메이션이 시작할 때와 끝날 때의 스타일, 그리고 중간 중간의 스타일을 지정할 수 있습니다.

💞 애니메이션 속성<br>

* animation-name: @keyframes에서 정의된 애니메이션의 이름을 지정합니다.

* animation-duration: 애니메이션이 완료되는 데 걸리는 시간입니다.

* animation-timing-function: 애니메이션의 속도 곡선을 설정합니다 (ease, linear 등).

✔ ease<br>
'ease'타이밍 함수는 애니메이션이 시작할 때는 천천히, 중간에는 빠르게, 그리고 끝날 때 다시 천천히 진행되는 형태입니다. 이는 자연스러운 움직임을 모방하려는 경우에 주로 사용되며, 시각적으로 부드러운 전환 효과를 제공합니다.
사용자 인터페이스 요소에 자주 사용되며, 버튼 클릭 효과, 팝업 창의 등장과 사라짐, 요소의 확대 및 축소 등에 이용됩니다.
<br>
✔ Linear<br>
`linear` 타이밍 함수는 애니메이션의 속도가 시작부터 끝까지 일정하게 유지되는 것을 말합니다. 애니메이션의 페이스에 변화가 없어, 매끄럽고 꾸준한 움직임을 제공합니다.
일정한 속도로 진행되는 스크롤 애니메이션이나 무한 로테이션에 주로 사용됩니다.
<br>

* animation-delay: 애니메이션이 시작하기 전에 대기하는 시간입니다.

* animation-iteration-count: 애니메이션이 몇 번 반복될지 설정합니다. infinite로 설정하면 무한 반복됩니다.

* animation-direction: 애니메이션이 정방향, 역방향 또는 번갈아 가며 진행되는지를 지정합니다 (normal, reverse, alternate, alternate-reverse).
<br>
✔ alternate : 순방향 - 역방향 순으로 지그재그 재생됩니다. (Infinite인 경우 실행됨)

✔ alternate-reverse : 역방향 - 순방향 순으로 지그재그 재생됩니다. (Infinite인 경우 실행됨)


* animation-fill-mode: 애니메이션이 시작하기 전과 끝난 후에 요소가 어떻게 보일지를 결정합니다 (none, forwards, backwards, both).

* animation-play-state: 애니메이션을 실행 중지하거나 다시 실행합니다 (running, paused).


````css
@keyframes spin {
    from { transform: rotate(0deg); }
    to { transform: rotate(360deg); }
}

.logo {
    width: 100px;
    height: 100px;
    background-color: tomato;
    animation-name: spin;
    animation-duration: 2s;
    animation-timing-function: linear;
    animation-iteration-count: infinite;
}
````
위 예시에서는 '.logo'라는 클래스를 가진 요소에 무한 회전 애니메이션을 적용했습니다.
`@keyframes` 규칙 `spin`은 로고가 0도에서 360도까지 회전하는 것을 정의하고, 이 애니메이션은 2초 동안 지속되며 무한히 반복됩니다. `animation-timing-function`은 `linear`로 설정되어 애니메이션의 속도가 일정하게 유지됩니다.

CSS 애니메이션을 사용하면 웹 페이지에 동적이고 매력적인 요소를 추가하여 사용자의 관심을 끌 수 있으며, 상호작용을 더 재미있고 의미 있게 만들 수 있습니다.



