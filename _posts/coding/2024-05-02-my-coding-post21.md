---
layout: post
title: Box Model
date: 2024-05-02 20:00 +0900
description: Box Model에 대해 알아보기!
image: ../assets/img/blogcss.gif
category: CSS
tags: CSS BOXMODEL
published: true
sitemap: true
---

## CSS

### Box Model

<hr>

오늘은 BOX MODEL에 대해 알아보는 시간을 가지겠습니다.<br>
웹 개발에서 CSS Box Model은 웹 페이지의 디자인과 레이아웃을 구성하는 데 중심적인 역할을 합니다.<br>
Box Model은 모든 HTML 요소를 하나의 상자로 간주하고, 이 상자의 콘텐츠, 패딩, 테두리, 마진을 정의하여 웹 페이지의 구조를 결정합니다. <br>
오늘은 그 Box Model의 주요 구성 요소와 사용법에 대해 자세히 설명해보겠습니다.<br>
기본적인 CSS 구성 요소이지만 다시 한번 상기시키며, 짚고 넘어가는 시간을 가지려고 합니다.

<hr>

### 🎈 Box Model의 구성 요소

1) <b> 콘텐츠(Content):</b> 요소의 실제 내용이 들어가는 영역입니다. 텍스트, 이미지 또는 다른 요소들이 이 공간에 위치합니다.

2) <b>패딩(Padding):</b> 콘텐츠와 테두리 사이의 영역입니다. 패딩은 콘텐츠 주변의 내부 공간을 늘려서 콘텐츠가 테두리에 닿지 않게 합니다.

3) <b>테두리(Border):</b> 패딩과 마진 사이에 위치하는 선으로, 요소의 경계를 나타냅니다.

4) <b>마진(Margin):</b> 요소와 이웃하는 다른 요소들 사이의 외부 공간입니다. 마진은 요소들 사이의 거리를 조절하는 데 사용됩니다.

5) <b>width, height:</b>요소의 가로 크기, 세로 크기를 말하며 기본적으로 여백과 테두리를 포함하지 않습니다.<br>

이와 함께 min-width, min-height, max-width, max-height 등이 있습니다.<br>
- max-width: 414px; : 요소의 너비 값을 414px로 지정함
- min-width: 1024px; : 요소의 가로 폭을 1024px 이상으로 지정함

6) <b>outline:</b> border 영역 외곽에 테두리를 치는 속성입니다.
outline은 두께가 늘어나도 주변에 공간을 확보하지 않으므로 레이아웃이 흐트러지지 않게 그저 영역 밖에 테두리를 표시할 뿐입니다.<br>

outline-style, ouline-width, outline-color라는 속성들을 따로 부여할 수 있으나 위, 아래, 왼쪽, 오른쪽 따로 적용할 수 없고 네 면 공동으로 적용됩니다.<br>
border와 outline 사이의 간격을 줄 때 outline-offset 속성을 사용할 수 있습니다.<br>
다음은 그 사용 예시입니다.

````css
border: 10px solid aaa ;
outline: 5px solid red;
outline-offset: 2px;
````
<br>

7) <b>box-sizing: </b> box-sizing 속성은 HTML요소의 박스 모델이 크기를 계산하는 방식을 결정합니다.<br>
기본적으로 CSS의 Box Model은 요소의 최종 크기를 계산할 때 width와 height가 콘텐츠 영역만을 포함하도록 설정되어 있습니다. <br>
하지만 box-sizing 속성을 사용하면 이 계산 방식을 변경할 수 있습니다.

#### box-sizing 속성의 값
✔ 속성 값 예문
1. box-sizing: content-box; -> 요소의 전체 크기에 padding, border 값을 포함시킵니다.<br>
width와 height 속성은 콘텐츠 영역(텍스트, 이미지 등이 실제로 차지하는 공간)만을 지정합니다.<br>
즉, 요소의 최종 크기는 width, height에 패딩, 테두리, 마진이 추가된 값이 됩니다.<br>
- 예시 : 만약 width: 100px;, padding: 10px;, border: 5px;로 설정되어 있다면, 실제 요소의 전체 너비 ? <br>
🗨 : 100px + 20px (양쪽 패딩) + 10px (양쪽 테두리) = 130px이 됩니다.
<br>

2. box-sizing: border-box; -> 요소의 전체크기에 padding, border 값을 포함시키지 않습니다.<br>
width와 height 속성은 테두리와 패딩을 포함한 요소의 전체 크기를 지정합니다.<br>
즉, 설정된 너비와 높이 내에 콘텐츠, 패딩, 테두리가 모두 포함되어야 합니다.
- 예시 : width: 100px; padding: 10px; border: 5px;로 설정되어 있다면, 실제 콘텐츠의 너비? <br>
🗨 : 100px - 20px (양쪽 패딩) - 10px (양쪽 테두리) = 70px이 됩니다. 요소의 외부 크기는 여전히 100px로 유지됩니다.<br>

✅content-box 모델 예제<br>
````html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Content-Box Model Example</title>
    <style>
        .content-box {
            box-sizing: content-box;
            width: 100px;
            padding: 20px;
            border: 5px solid red;
            background-color: blue;
            margin: 10px;
        }
    </style>
</head>
<body>
    <div class="content-box"></div>
</body>
</html>
````


✅border-box 모델 예제<br>
````html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Border-Box Model Example</title>
    <style>
        .border-box {
            box-sizing: border-box;
            width: 100px;
            padding: 20px;
            border: 5px solid #418ad7;
            background-color: pink;
            margin: 10px;
        }
    </style>
</head>

<body>
    <div class="border-box"></div>
</body>

</html>
````
<br>

8) box-shadow: CSS에서는 요소에 그림자를 발생시킬 수 있습니다. 이 때, box-shadow를 사용합니다.

