---
layout: post
title: IR효과
date: 2024-07-01 10:00 +0900
description: IR효과
image: https://github.com/user-attachments/assets/2a438173-0906-4dfb-abd8-0c36fb6ed45c
category: CSS
tags: CSS IR효과
published: true
sitemap: true
---

# CSS

## ✨ IR효과

### 웹 접근성을 위한 이미지 대체 텍스트 제공 방법

웹 접근성은 모든 사용자가 웹 콘텐츠를 문제없이 접근하고 이용할 수 있도록 하는 중요한 요소입니다. <br>
특히 시각 장애가 있는 사용자에게 이미지를 이해할 수 있도록 돕는 것은 매우 중요합니다. <br>
이를 위해 IR(이미지 대체 텍스트 제공) 기법이 사용됩니다. 이 글에서는 IR 기법에 대해 알아보고, `ir_pm`, `ir_wa`, `ir_so`와 같은 구체적인 클래스들에 대해 설명하겠습니다.

<br>

### IR기법이란

IR(이미지 대체 텍스트 제공, Image Replacement) 기법은 CSS를 이용해 이미지를 숨기고 대신 대체 텍스트를 제공하는 방법입니다. <br>
이는 시각 장애가 있는 사용자가 스크린 리더를 통해 이미지의 내용을 이해할 수 있도록 돕기 위해 사용됩니다. <br>
다양한 IR 기법이 존재하지만, 여기서는 `ir_pm`, `ir_wa`, `ir_so`를 중심으로 설명하겠습니다.
<br>

### 1. ir_pm

`.ir_pm` 클래스는 의미 있는 이미지의 대체 텍스트를 제공하기 위한 방법입니다. <br>
이 클래스는 이미지를 시각적으로 숨기지만, 스크린 리더에게는 대체 텍스트를 읽을 수 있게 합니다. <br>
예를 들어, 로고나 중요한 아이콘의 대체 텍스트를 제공할 때 사용할 수 있습니다.

```css
.ir_pm {
  display: block;
  overflow: hidden;
  text-indent: -9999px;
  width: 0;
  height: 0;
  line-height: 0;
}
```

위의 CSS 코드에서 text-indent 속성을 이용해 텍스트를 화면 밖으로 밀어내고, width와 height를 0으로 설정하여 이미지를 숨깁니다.
<br>

```html
<span class="ir_pm">This is alternative text for a meaningful image</span>
```

이 코드는 사용자에게 보이지 않지만, 스크린 리더는 "This is alternative text for a meaningful image"라고 읽어줍니다.

<br>

### 2. ir_wa

`.ir_wa` 클래스는 의미 있는 이미지의 대체 텍스트를 제공하며, 이미지를 완전히 숨기지 않고 <mark>대체 텍스트가 항상 보이도록 할 때 사용됩니다.</mark> <br>
이는 이미지가 로드되지 않거나 비활성화된 경우에도 대체 텍스트를 보여주는 방법입니다.

```css
.ir_wa {
  position: relative;
  width: 1px;
  height: 1px;
  overflow: hidden;
}
.ir_wa:before {
  content: attr(data-text);
  position: absolute;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  white-space: nowrap;
  text-align: center;
  background: #fff;
  color: #000;
}
```

이 기법은 `:before` 가상 요소를 사용하여 대체 텍스트를 표시합니다.<br>
`attr(data-text)`를 사용하여 요소의 `data-text` 속성에 있는 텍스트를 가져옵니다.

```html
<div
  class="ir_wa"
  data-text="This text is visible when the image is not loaded"
></div>
```

이 코드는 이미지가 로드되지 않거나 숨겨져 있을 때 "This text is visible when the image is not loaded"라는 텍스트를 표시합니다.

<br>

### 3. ir_so

`.ir_so` 클래스는 주로 스크린 리더 전용 텍스트를 제공하는 데 사용됩니다.<br>
시각적으로는 완전히 숨기지만, 스크린 리더는 이 텍스트를 읽을 수 있습니다.

```css
.ir_so {
  position: absolute;
  width: 1px;
  height: 1px;
  margin: -1px;
  padding: 0;
  border: 0;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  white-space: nowrap;
}
```

이 기법은 요소를 화면에서 완전히 제거하는 대신, 화면에서 보이지 않도록 위치와 크기를 조정합니다.
<br>

```html
<span class="ir_so">This is a screen reader only text</span>
```

이 코드는 시각적으로는 보이지 않지만, 스크린 리더는 "This is a screen reader only text"라는 텍스트를 읽습니다.

<br>

## 결론

IR 기법은 웹 접근성을 높이기 위해 중요한 역할을 합니다.<br>
`ir_pm`, `ir_wa`, `ir_so`와 같은 클래스들은 각각의 상황에 맞는 이미지 대체 텍스트를 제공하는 데 유용합니다. <br>
이를 통해 시각 장애가 있는 사용자들도 웹 콘텐츠를 쉽게 접근하고 이해할 수 있게 됩니다. <br>
웹 개발자는 이러한 기법들을 적절히 활용하여 모든 사용자가 접근 가능한 웹 사이트를 만드는 데 기여할 수 있습니다.
