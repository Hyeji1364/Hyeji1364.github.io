---
layout: post
title: img태그와 background태그
date: 2024-04-17 16:43 +0900
description: 
image: ../assets/img/tagimg.gif
category: CSS
tags: img background
published: true
sitemap: true
---

## img 태그와 background 태그


이미지를 표시하는데는 img 태그와 background 속성을 사용하는 두 가지 주요 방법이 있습니다. 각각의 방법은 특징과 용도에 따라 선택됩니다.

<hr />

> #### 👀 img 태그 사용

* img 태그는 HTML 문서 안에서 이미지를 직접 표시하는 데 사용됩니다.
* 이미지의 URL을 'src' 속성으로 지정하여 이미지를 로드하고 표시합니다.
* 주로 컨텐츠 이미지나  사용자에게 직접적으로 보여줘야 할 이미지에 사용됩니다.
* img 태그를 사용하면 이미지에 대한 대체 텍스트를 제공할 수 있어 웹 접근성을 향상시킬 수 있습니다.

🎈 alt 속성<br>
img태그의 'alt'속성은 이미지에 대한 대체 텍스트를 정의하는 데 사용됩니다.
대체 텍스트는 이미지가 표시되지 않을 때나 이미지가 로딩되기 전에 화면에 표시됩니다.
이는 시각 장애를 가진 사용자나 시각적으로 이미지를 표시할 수 없는 상황에서 웹 사이트의 접근성을 향상시키는 데 중요합니다.

'alt'속성을 포함하는 것은 웹 접근성을 준수하는데 필수적이며,
대체 텍스트는 이미지의 콘텐츠나 의도를 설명하는 역할을 합니다.
대체 텍스는 이미지가 어떤 내용을 나타내는지 설명하는 짧고 명확한 문구여야 합니다.

````html
<img src="example.jpg" alt="이미지 설명">

<img src="cat.jpg" alt="고양이">
````
<br>

> #### 👀 배경이미지(background) 사용

* CSS의 background 속성을 사용하여 요소의 배경으로 이미지를 설정합니다.
* 주로 디자인적인 목적으로 요소의 배경으로 이미지를 표시할 때 사용됩니다.
* HTML 문서에서는 내용이 아닌 디자인적인 요소로서 이미지를 사용할 때 주로 배경 이미지가 선택됩니다.
* 이미지에 대한 대체 텍스트를 제공할 수 없습니다.

````html
.element {
    background-image: url("example.jpg");
}
````


