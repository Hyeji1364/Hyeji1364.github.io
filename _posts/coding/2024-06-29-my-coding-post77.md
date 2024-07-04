---
layout: post
title: CSS 우선순위
date: 2024-06-29 10:00 +0900
description: CSS 우선순위
image: https://github.com/Hyeji1364/class2024/assets/161557112/c62721e3-1ad4-4a59-9798-f54b3e7537e6
category: CSS
tags: CSS
published: true
sitemap: true
---

# CSS 우선순위

웹 개발에서 CSS(Cascading Style Sheets)는 HTML 요소들의 스타일을 정의하는 데 사용됩니다. <br>
하지만 여러 가지 방법으로 스타일을 적용하다 보면 어떤 스타일이 최종적으로 적용될지 혼란스러울 수 있습니다. <br>
이 문제를 해결하기 위해 CSS는 우선순위 규칙을 가지고 있습니다. <br>
이 글에서는 CSS 우선순위에 대해 자세히 설명하겠습니다.
<br>

### 📁 01. !important 키워드

가장 높은 우선순위를 가지는 것은 속성 값 뒤에 `!important`를 붙인 속성입니다. <br>
이 키워드는 특정 스타일을 무조건 적용하고 싶을 때 사용합니다.
<br>

예시

```css
p {
  color: blue !important;
}
```

여기서 모든 `<p>` 요소의 글자 색은 무조건 파란색이 됩니다. <br>
!important는 매우 강력한 도구이지만, 남용하면 유지보수가 어려워질 수 있으므로 신중하게 사용해야 합니다.

<br>

### 📁 02. HTML에서 style을 직접 지정한 속성

HTML 요소에 직접 스타일을 지정하는 방식은 두 번째로 높은 우선순위를 가집니다.
<br>

예시

```html
<p style="color: red;">This is a paragraph.</p>
```

위의 예제에서는 `p` 요소의 글자 색이 인라인 스타일에 의해 빨간색으로 지정됩니다.

<br>

### 📁 03. #id로 지정한 속성

ID 셀렉터는 세 번째로 높은 우선순위를 가집니다. <br>
ID는 문서 내에서 고유해야 하며, 다음과 같이 사용됩니다.
<br>

```css
#unique {
  color: green;
}
```

<br>
````html
<p id="unique">This is a unique paragraph.</p>
````
이 경우, ID가 unique인 요소의 글자 색은 녹색으로 지정됩니다.

<br>

### 📁 04. .클래스, :추상 클래스로 지정한 속성

클래스 셀렉터와 의사 클래스(예: :hover, :active)는 네 번째 우선순위를 가집니다. <br>

```css
.highlight {
  color: yellow;
}
```

```html
<p class="highlight">This is a highlighted paragraph.</p>
```

여기서 `highlight` 클래스를 가진 요소의 글자 색은 노란색이 됩니다.

<br>

### 📁 05. 태그 이름으로 지정한 속성

태그 이름으로 지정한 속성은 다섯 번째 우선순위를 가집니다. <br>
태그 이름을 직접 사용하여 스타일을 지정할 수 있습니다.
<br>
예시

```css
p {
  color: orange;
}
```

이 경우 모든 `p` 요소의 글자 색은 주황색이 됩니다.
<br>

### 📁 06. 상위 객체에 의해 상속된 속성

마지막으로, 상위 객체에 의해 상속된 속성이 가장 낮은 우선순위를 가집니다. <br>
예를 들어, 상위 요소에 텍스트 색상을 지정하면 하위 요소들도 이 색상을 상속받게 됩니다. <br>
다음과 같은 예시가 있습니다.

```css
div {
  color: purple;
}
```

```html
<div>
  <p>This paragraph will inherit the color from the parent div.</p>
</div>
```

여기서 div 요소 내부의 `p` 요소는 글자 색을 상속받아 보라색이 됩니다.

<br>

## ✨ 우선순위의 결합

때로는 여러 규칙이 결합되어 사용됩니다. <br>
예를 들어, 특정 클래스와 ID가 결합된 경우, 이들의 우선순위를 합산하여 최종 스타일이 결정됩니다. <br>
따라서 우선순위를 잘 이해하고 사용하면 원하는 스타일을 더 정확하게 적용할 수 있습니다.
<br>

CSS 우선순위를 이해하고 적절하게 사용하는 것은 웹 디자인에서 매우 중요합니다. <br>
이를 통해 더 효율적이고 일관된 스타일링을 적용할 수 있으며, 유지보수 또한 용이해집니다. <br>
