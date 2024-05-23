---
layout: post
title: block, inline-block, inline 차이
date: 2024-05-15 10:00 +0900
description: block, inline-block, inline 차이
image: ../assets/img/inline.png
category: CSS
tags: CSS block inline-block inline
published: true
sitemap: true
---

## block, inline-block, inline 차이

오늘은 CSS에서 block, inline-block, inline 차이에 대해 알아보겠습니다.
<br>
CSS에서 block, inline-block, inline 디스플레이 속성은 요소가 문서 내에서 어떻게 배치되고 다른 요소와 상호작용하는지를 결정합니다.<br>
이 세 가지 디스플레이 속성은 각기 다른 레이아웃 특성을 가지며, 특정 상황에서 적절히 사용됩니다.<br>

01.  block 요소
- 특성: block 요소는 항상 새로운 줄에서 시작하며, 가능한 최대 너비(부모 요소의 너비)를 차지합니다. <br>
너비와 높이를 지정할 수 있으며, 마진과 패딩을 적용할 수 있습니다.
- 예: `div`, `h1`, `p` 등이 대표적인 블록 요소입니다.
- 용도: 문단, 섹션, 블록 수준의 레이아웃에 사용됩니다.

````html
<div style="border: 1px solid black;">Block Element 1</div>
<div style="border: 1px solid black;">Block Element 2</div>
````

위의 예시에서 각 div 요소는 새로운 줄에서 시작하며, 가능한 최대 너비를 차지합니다.

02. inline 요소
- 특성: inline 요소는 콘텐츠의 크기만큼 너비를 차지하며, 다른 요소와 같은 줄에 배치됩니다.<br>
- 너비와 높이를 지정할 수 없으며, 수평 및 수직 마진과 패딩만 일부 적용됩니다.
- 예: `span`, `a`, `strong` 등이 대표적인 인라인 요소입니다.
- 용도: 텍스트 내에서 스타일을 적용하거나 작은 영역을 강조하는 데 사용됩니다.


02. inline-block 요소
- 특성: inline-block 요소는 inline 요소처럼 같은 줄에 배치되지만, block 요소처럼 너비와 높이를 지정할 수 있습니다.<br>
마진과 패딩도 완전히 적용됩니다.
- 예: 디폴트로는 없지만, `display: inline-block;`을 적용하여 생성할 수 있습니다.
- 용도: 인라인 레이아웃에서 블록 수준의 제어가 필요한 경우 사용됩니다.<br>
예를 들어, 네비게이션 메뉴나 버튼 등을 만들 때 유용합니다.


✨ 정리
#### block 요소:
- 새로운 줄에서 시작하고, 가능한 최대 너비를 차지함.
- 예: `div`, `h1`, `p`

#### inline 요소:
- 같은 줄에 배치되고, 콘텐츠의 크기만큼 너비를 차지함.
- 예: `span`, `a`, `strong`

#### inline-block 요소:
- 같은 줄에 배치되지만, 너비와 높이를 지정할 수 있음.
- 예: `display: inline-block;`으로 설정한 요소

이러한 속성을 적절히 사용하면 웹 페이지의 레이아웃을 효과적으로 관리하고, 원하는 디자인을 구현할 수 있습니다.
