---
layout: post
title: CSS - position
date: 2024-04-21 18:40 +0900
description: 
image: ../assets/img/blogcss.gif
category: 
tags: CSS position
published: true
sitemap: true
---

## CSS

### 레이아웃 : position

레이아웃을 배치하거나 요소 위치를 지정하는 요소 중 중요한 속성이 position입니다.
position에서는 세로 배열, 가로 배열이 문제가 아니라 주로 부모 박스의 좌표를 기준으로 요소의 위치가 결정됩니다.
따라서 부모 박스가 어떤 요소인지가 매우 중요합니다.

<hr />

> ### ✅ position

positon에는 static, relative, absolute, fixed 네 가지의 속성 값이 있으며 다음과 같이 표현합니다.

````css
position: relative
````

✔ position 기능 정리 

|속성 값|속성 설명|
|------|---|
|static|- 요소를 이동하거나 겹칠 수 없는 원래 그대로의 상태<br>- relative, absolute, fixed했던 박스를 원상태로 회복
|relative|- left,top속성으로 이동할 수 있음<br> - position:absolute로 지정된 요소의 '부모'역할을 할 수도 있음|
|absolute|- 원래 위치에서 따로 떼어내 독립적으로 새로운 위치를 설정함<br> - left, right,top,bottom 속성으로 위치 지정할 수 있음|
|fixed|- 요소의 위치를 screen 기준으로 지정함<br> - left, right, top, bottom 속성으로 위치 지정할 수 있음|

우리가 지금까지 사용해 온 블록들은 이미 position: static 상태였습니다.
position은 매우 다양한 형태로 활용될 수 있습니다.
어떤 요소를 원래 위치에서 이동해야 하거나 제이쿼리 등으로 애니메이션을 지정해야 할 때에 position:relative 할 수 있으며, 다른 요소와 겹쳐야 할 때나 마크업 순서와 다르게 위치를 설정해야 할 때 position: absolute 할 수 있습니다.

⚠ position: absolute; 된 요소의 부모 박스는 반드시 position: relative; 이거나 positio: absolute; 또는 position: fixed 되어야 하며, 부모 박스를 지정하지 않으면 body가 부모가 됩니다.

> ### 💛 z-index

z-index는 CSS 속성 중 하나로 HTML 문서의 요소들이 페이지 상에서 서로 겹쳐지는 순서를 정할 때 사용됩니다.
이 속성은 주로 포지셔닝이 지정된 요소 (ex. position: absolute, position: relative, position: fixed, position: sticty)에 적용됩니다.

🔰<mark> z-index의 기본 원리 </mark>
* z-index의 값은 정수(음수 포함)로 지정하며, 값이 클수록 위쪽에 표시됩니다.

* 같은 부모 요소 내에서 z-index 값이 높은 자식 요소가 더 위에 겹쳐서 표시됩니다.

* z-index가 지정되지 않은 요소는 z-index:0으로 간주됩니다.

🔰<mark> 중요한 특징 </mark>

1. 스태킹 컨텍스트(Stacking Context)<br>

* 특정 요소에 z-index가 적용되면, 해당 요소와 그자식 요소들을 독립적인 스태킹 컨텍스트를 형성합니다.

* 스태킹 컨텍스트는 요소들이  z축에서 어떻게 쌓일지 결정하는 범위를 형성합니다. 컨텍스트 내의 요소는 외부 요소와의 상대적인 z-index 값을 무시하고, 자신의 컨텍스트 안에서만 z-index 값을 비교합니다.
<br>

2. 상속❌<br>

z-index는 상속되지 않습니다. 부모 요소의 z-index가 자식 요소에 직접적인 영향을 주지 않습니다.
대신, 부모 요소의 스태킹 컨텍스트가 자식 요소에 영향을 줍니다.
<br>

3. 음수 값의 사용<br>

* z-index에 음수 값을 사용할 수 있으며, 이 경우 다른 요소들보다 더 아래에 위치하게 됩니다.

* 음수를 사용할 때는 주변 요소와의 상호 작용을 신중히 고려해야 합니다. 예를 들어, 사용자의 클릭이나 마우스 이벤트 등이 예상대로 작동하지 않을 수 있습니다.

✔ z-index의 활용 예<br>
HTML 요소들을 시각적으로 레이어링 할 때, 팝업, 드롭다운 메뉴, 모달 창 등이 다른 요소들 위에 올바르게 표시되도록 관리하는 데 z-index를 활용할 수 있습니다.

z-index는 복잡한 인터페이스와 상호 작용하는 웹 페이지의 레이아웃을 조정하는 데 매우 중요한 도구입니다.
