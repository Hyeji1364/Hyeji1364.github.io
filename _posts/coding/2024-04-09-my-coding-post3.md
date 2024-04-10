---
layout: post
title: 자바스크립트 자료형
date: 2024-04-10 22:00 +0900
description: 
image: ../assets/img/Javascript.jpg
category: CSS
tags: CSS
published: true
sitemap: true
---

## CSS 

#### 선택자(selector)

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


> 선택자의 종류(selector)

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

<br>
2️⃣ id 선택자
HTML 요소에 id로 이름을 붙일 때에는 유일한 이름을 부여해야 하며, 다른 요소에 같은 id명을 또 주어서는 안됩니다.
CSS에서는 id선택자 앞에 #을 붙여야 합니다.
id명이나 class명은 숫자로 시작할 수 없으며, 주로 영문자로 시작합니다.

````css
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <title>id선택자</title>
    <style type="text/css">
    p { color : red ; }
    #ctxt { color : blue ; }
    </style>
</head>
<body>
    <p>우리를 기쁘게 하는 것들</p>
    <p id="ctxt">건강에 좋은 차</p>
    <p id="txt">머리가 좋아지는 음식</p>
</body>
</html>
````

▶ <h6 style="color:red">우리를 기쁘게 하는 것들</h6>
 <h6 style="color:blue">건강에 좋은 차</h6>
<h6 style="color:red">머리가 좋아지는 음식</h6>

결과를 보면 id가 txt인 p요소(머리가 좋아지는 음식)는 스타일이 지정된 바 없으므로 p요소에는 처음 지정된 빨간색 글자 스타일로 나타납니다.

3️⃣ class 선택자
HTML 문서의 여러 요소 중 같은 이름을 갖는 요소들만 모아 따로 속성을 부여할 수 있습니다.
id와 달리, class는 여러 개의 요소에 같은 class명을 부여할 수 있습니다. 또한 하나의 요소에 여러 개의 class명을 부여할 수도 있습니다.
CSS에서는 class 선택자 앞에 .을 붙여야 합니다.

4️⃣ 전체 선택자
전체 선택자는 페이지의 모든 요소를 가리키는 선택자로서 '*'로 표시합니다.

````css
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <title>전체 선택자</title>
    <style type="text/css">
    * { color : blue ; }
    </style>
</head>
<body>
    <h2>선택자의 종류</h2>
    <ul>
    <li>id 선택자</li>
    <li>class 선택자</li>
    <li>전체 선택자</li>
    <li>하위 선택자</li>
    <li>자식 선택자</li>
    <li>인접 선택자</li>
    <li>형제 선택자</li>
    <li>그룹 선택자</li>
    <li>속성 선택자</li>
    </ul>
    <p class= "ctxt">선택자의 종류에는 다양한 것들이 있다.</p>
</body>
</html>
````

<h2 style="color:blue">선택자의 종류</h2>
<h6 style="color:blue">class 선택자</h6>
<h6 style="color:blue">전체 선택자</h6>
<h6 style="color:blue">하위 선택자</h6>
<h6 style="color:blue">자식 선택자</h6>
<h6 style="color:blue">인접 선택자</h6>
<h6 style="color:blue">형제 선택자</h6>
<h6 style="color:blue">그룹 선택자</h6>
<h6 style="color:blue">속성 선택자</h6>

5️⃣ 하위 선택자
하위 선택자는 요소 내부에 있는 모든 해당 요소를 가리키며, 선택자 사이를 "공백"으로 분리합니다.


6️⃣ 자식 선택자
자식 선택자는 요소 내부에 있는 해당 요소를 가리키지만, 하위 요소의 하위 요소는 가리키지 않으며, 선택자 사이를 '>'으로 분리합니다.
다음 예제에서는 abox 클래스 내부에 있는 요소들 중 또 다른 하위 요소(ul)안에 있는 p 태그들을 제외한 나머지 p 태그들의 문자만을 파란색으로 표시하도록 속성을 부여합니다.
````css
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <title>자식 선택자</title>
    <style type="text/css">
    .abox > p { color : blue ; }
    </style>
</head>
<body>
    <div class="abox">
    <p>7월의 여행지</p>
    <ul>
        <li><p>1주차 여행지</p></li>
        <li><p>2주차 여행지</p></li>
        <ul>
        <p>8월의 여행지</p>
        </div>
        <p>내년의 여행지</p>
</body>
</html>
````

<h6 style="color:blue">7월의 여행지</h6>

- 1주차 여행지
- 2주차 여행지

<h6 style="color:blue">8월의 여행지</h6>
내년의 여행지<br>
<br>

7️⃣ 인접 선택자
인접 선택자는 현재 요소의 바로 뒤에 나오는 요소만을 가리키는 선택자로,선택자 사이를 "+"로 분리합니다.

````css
h1 + p { color: blue; }
이 예시에서는 <h1> 요소 바로 다음에 오는
<p> 요소의 텍스트 색상을 파란색으로 변경합니다.
<h1> 요소 다음에 오는 첫 번째 <p> 요소에만 적용되며, 그 이후에 오는 <p> 요소들에는 영향을 주지 않습니다.
````

8️⃣ 형제 선택자
형제 선택자는 현재 요소와 같은 계층에 있는 요소만을 선택할 수 있으며 "~"로 구분합니다.
````css
<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<title>형제 선택자 예시</title>
<style>
  /* h1 요소 뒤에 오는 모든 p 요소에 스타일 적용 */
  h1 ~ p {
    color: green;
    border: 1px solid green;
  }
</style>
</head>
<body>

<h1>제목입니다</h1>
<p>첫 번째 문단입니다. 이 문단은 초록색으로 표시됩니다.</p>
<div>이 div는 스타일의 영향을 받지 않습니다.</div>
<p>두 번째 문단입니다. 이 문단도 초록색으로 표시됩니다.</p>

</body>
</html>
````

9️⃣ 그룹 선택자
그룹 선택자는 여러 선택자들을 ","로 구분하여 함께 묶어 속성을 부여하는 것입니다.

````css
<!DOCTYPE html>
<html>
<head>
<style>
.box1, .box2 {
  width: 100px;
  height: 100px;
  background-color: red;
}

.box3 {
  width: 100px;
  height: 100px;
  background-color: blue;
}
</style>
</head>
<body>

<div class="box1"></div>
<div class="box2"></div>
<div class="box3"></div>

</body>
</html>
````
위 코드에서는 클래스 이름이 box1과 box2인 두 개의 div 요소를 그룹 선택자로 묶어서 선택하고, background-color 속성을 red로 설정합니다.
클래스 이름이 box3인 div 요소는 그룹 선택자로 묶이지 않고 따로 선택되어 background-color 속성이 blue로 설정됩니다.

이렇게 그룹 선택자를 사용하면 여러 개의 선택자를 하나의 그룹으로 묶어서 관리할 수 있어서 편리합니다.

🔟 속성 선택자
HTML 요소의 속성 유무 또는 속성값을 중괄호[]안에 넣어 선택자로 사용할 수 있습니다.
- h1[class] : class명을 가진 h1 요소
- img[alt] : alt속성을 가진 img 요소
- p[class="abc"] : class명이 유일하게 'abc'인 p요소
- p[class~="abc"] : class명이 유일하게 'abc'이거나 여러 개의 class명 중 하나가 'abc'인 p 요소
- p[class|="abc"] : class명이 'abc'이거나 'abc-'로 시작하는 p 요소
- p[class^="abc"] : class명이 철자 'abc'로 시작하는 p  요소
- p[class$="abc"] : class명이 철자 'abc'로 끝나는 p요소
- p[class*="abc"] : class명에 철자 'abc'가 포함되어 있는 p요소
- p[href^="mailto"] : href 속성 값이 'mailto'로 시작하는 a 요소

1️⃣1️⃣ 가상클래스 선택자
가상클래스 선택자란 링크가 걸린 문자에 스타일을 부여하는 것입니다.
- a:link : 링크가 걸린 문자에 속성을 부여하는 선택자
- a:visited : 링크를 클릭하여 해당 페이지에 갔다가 돌아온 경우의 속성을 부여하는 선택자
- a:hover : 링크가 걸린 문자에 마우스가 닿았을 경우의 속성을 부여하는 선택자
- a:active : 링크 걸린 글자가 활성화되었을 경우의 속성을 부여하는 선택자(클릭했다가 돌아왔거나 클릭하려다 만 경우)
- a:focus : 링크 걸린 글자에 포커스가 생길 경우의 속성을 부여하는 선택자(키보드의 [Tab]키 등으로 포커스가 나타날 경우)

1️⃣2️⃣ 가상요소 선택자
가상요소 선택자는 요소에 id명이나 class명을 부여하지 않고도 위치를 찾아서 선택할 수 있는 선택자입니다.
- :first-lettr : 요소의 첫 글자
- :first-line : 요소의 첫 줄
- :first-child : 같은 요소 중 첫 번째 요소
- :last-child : 같은 요소 중 마지막 요소
- :nth-child(n): 같은 요소 중 n번째 요소
- :before : 요소 안 맨 앞에 배치될 요소(마크업에는 없는 가상 요소)
- :after : 요소 안 맨 뒤에 배치될 요소(마크업에는 없는 가상 요소)

1️⃣3️⃣ 종속 선택자
종속 선택자는 type 선택자와 id선택자, class 선택자가 결합된 형태입니다.
````css
<p id="atxt">선택자의 다양한 표현</p>
````
마크업이 위와 같을 때 #atxt와 p#atxt는 같은 선택자입니다. 다만 p#atxt가 #atxt보다 높은 우선순위를 가집니다.

1️⃣4️⃣ 선택자의 우선순위
우선순위가 같은 선택자라면 나중에 기술한 것이 먼저 기술한 것보다 우선순위가 높습니다.

선택자마다 우선순위를 값으로 매겨본다면 다음과 같습니다.
- 전체 선택자 (*) : 033
- type 선택자(p, h1, ul, ...) : 1
- 가상 선택자 (:first-child, ...) : 10
- class 선택자(.abc, ...) : 10
- id 선택자 (#abc, ...) : 100
요소에 직접  style=""형식으로 CSS를 기술하는 인라인 스타일은 위의 모든 선택자보다 우선으로 실행됩니다.
지금까지 나온 방법보다 최우선으로 CSS를 적용해야 할 경우에는 선택자에 속성을 부여하는 마지막에 "!important"를 붙이면 됩니다.
````css
p { color : red !important; }
````

💭 선택자에 대해 정리한 후 느낀점
CSS의 선택자에 대해 막연하게만 느꼈던 것을 이론으로 정리하고 나니,CSS를 적용할 때 감으로만 익혔던 것들을 자세히 알 수 있어 앞으로 스타일을 적용할 때 유용하게 사용할 수 있을 것 같다!
