---
layout: post
title: GSAP
date: 2024-04-23 01:10 +0900
description: 
image: ../assets/img/gsap.png
category: Javascript
tags: CSS position
published: true
sitemap: true
---

## GSAP

GSAP(GreenSock Animation Platform)은 CSS와는 별개의 자바스크립트 라이브러리입니다. GSAP는 웹 페이지에서 복잡하고 성능이 뛰어난 애니메이션을 구현하기 위해 개발되었습니다.
이 라이브러리를 사용하면 Javascript를 통해 HTML 요소의 CSS 속성을 애니메이션화할 수 있지만, 자체적으로는 CSS 코드나 스타일시트가 아닙니다.

<hr />

GSAP는 주로 다음과 같은 기능을 제공합니다.

> #### GSAP의 기능

* 속도와 성능 : 최적화된 엔진을 사용하여 빠르고 부드러운 애니메이션을 보장합니다.

* 유연성 : CSS 속성, SVG, 캔버스 요소 및 Javascript객체의 속성 등 다양한 대상에 애니메이션을 적용할 수 있습니다.

* 제어 : 애니메이션의 일시 중지, 재개, 역방향 재생, 속도 조절 등 세밀한 애니메이션 제어가 가능합니다.

* 호환성 : 다양한 브라우저와 장치에서 일관된 애니메이션 효과를 제공합니다.

<hr />

이제 GSAP에 대한 기능은 알았으니 GSAP를 사용하려면 어떻게 해야하는지 알아볼까요?!

> #### GSAP 시작하기
GSAP를 사용하는 두 가지 방법이 있습니다.

1️⃣ CDN을 통해 포함하기 <br>
GSAP를 사용하는 가장 간단한 방법은 HTML 문서의 'head' 태그 또는 'body'태그 바로 위에 GSAP 스크립트를 CDN 링크로 포함하는 것입니다.

````html
<script src="https://cdn.jsdelivr.net/npm/gsap@3.12.5/dist/gsap.min.js"></script>
````

2️⃣NPM을 통해 설치하기 <br>
Node.js 환경에서는 NPM을 사용하여 GSAP을 설치할 수 있습니다. 터미널에서 다음 명령을 실행하세요.

````html
npm install gsap
````

설치 후, JavaScript 파일에서 GSAP을 불러와 사용할 수 있습니다:

````html
import gsap from 'gsap';
````

> ### ✨ 애니메이션 생성

GSAP 메서드를  몇 가지 소개하겠습니다.
<br>
1️⃣ 'gsap.to()'<br>
선택한 요소를 특정 상태로 애니메이션합니다.
예를 들어, 요소를 페이드아웃하거나, 위치를 이동시키거나, 크기를 변화시키는 등의 작업을 할 수 있습니다.

````javascript
// 요소를 1초 동안 x축으로 100px, y축으로 50px 이동
gsap.to(".box", {duration: 1, x: 100, y: 50});
````

2️⃣ 'gsap.from()'<br>
'gsap.to()'와 반대로, 요소를 특정 상태에서 시작하여 원래 상태로 애니메이션합니다. 이는 요소가 처음에 어떤 상태였는지 설정하고, 그 상태에서 애니메이션을 시작하고자 할 때 유용합니다.

````javascript
// 요소가 투명한 상태에서 시작하여 1초 동안 불투명하게 변화
gsap.from(".box", {duration: 1, opacity: 0});
````


3️⃣ 'gsap.fromTo()'<br>
gsap.fromTo() 메서드는 요소를 지정된 시작 상태에서 끝 상태로 애니메이션합니다. 이 메서드는 두 개의 객체를 인자로 받으며, 첫 번째 객체는 시작 상태, 두 번째 객체는 끝 상태를 정의합니다.

````javascript
// 요소를 투명에서 불투명으로, x축으로 0px에서 100px로 1.5초 동안 이동
gsap.fromTo(".box", {opacity: 0, x: 0}, {duration: 1.5, opacity: 1, x: 100});
````

4️⃣ 'gsap. timeline()'

gsap.timeline() 메서드는 여러 애니메이션을 시퀀스로 조합하고 제어할 수 있는 타임라인을 생성합니다. 타임라인은 각 애니메이션의 시작 시간을 조절하여 순차적이거나 겹치게 할 수 있습니다.

````javascript
// 타임라인 생성 후, 여러 애니메이션 추가
let tl = gsap.timeline();
tl.to(".box1", {duration: 1, x: 100})
  .to(".box2", {duration: 1, y: 100}, "-=0.5") // 앞 애니메이션과 0.5초 겹치게 시작
  .from(".box3", {duration: 1, opacity: 0});
  ````
  타임라인을 사용한 추가적인 예제를 알아보겠습니다.
````javascript
let tl = gsap.timeline({repeat: 2, repeatDelay: 1});
tl.to(".element", {x: 100, duration: 1});
tl.to(".element", {y: 50, duration: 1});
````
이 타임라인은 요소를 먼저 x축으로 100 이동시키고, 그 다음 y축으로 50 이동시킨 후, 전체 시퀀스를 두 번 반복하고 각 반복 사이에 1초의 지연을 추가합니다.


5️⃣ 이벤트와 콜백

  애니메이션의 생명주기에 따라 콜백 함수를 설정하여 특정 이벤트가 발생했을 때 코드를 실행할 수 있습니다.

  ````javascript
  // 애니메이션이 완료됐을 때 콜백 함수 실행
gsap.to(".box", {
  duration: 2,
  x: 100,
  onComplete: function() {
    console.log("Animation completed!");
  }
});
  ````

  GSAP를 통해 애니메이션을 구현함으로써 웹 페이지에 동적이고 매력적인 시각적 요소를 추가할 수 있습니다. 😎