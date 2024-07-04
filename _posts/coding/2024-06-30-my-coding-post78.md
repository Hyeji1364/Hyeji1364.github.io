---
layout: post
title: CSS Display속성
date: 2024-06-30 10:00 +0900
description: CSS Display속성
image: https://github.com/Hyeji1364/class2024/assets/161557112/396bbc8c-c72b-4d48-991c-b961a1e33e79
category: CSS
tags: CSS
published: true
sitemap: true
---

# CSS Display 속성

## Block, Inline, Inline-Block의 차이점

웹 개발에서 CSS의 display 속성은 HTML 요소의 레이아웃과 배치 방식을 결정하는 중요한 역할을 합니다. <br>
이 글에서는 inline, block, inline-block의 차이점과 각각의 특성을 설명하겠습니다.
<br>

### Inline

inline 요소는 <mark>텍스트의 크기 만큼만 공간을 점유</mark>하며, 줄바꿈을 하지 않습니다.<br>
대표적인 inline 요소로는 `<span>`, `<a>`, `<strong>` 등이 있습니다.
<br>

예시

```html
<span>This is inline</span> <span>element</span>
```

위의 코드를 보면, `span` 요소들이 한 줄에 나란히 배치됩니다. <br>
`inline` 요소는 너비와 높이를 설정할 수 없으며, 마진과 패딩을 설정해도 좌우 공간만 반영됩니다.

<br>

### Block

`block` 요소는 <mark>항상 한 줄을 점유</mark>하며, 다음 요소는 자동으로 줄바꿈됩니다. <br>
대표적인 block 요소로는 `<div>`, `<p>`, `<h1>` 등이 있습니다.
<br>

예시

```html
<div>This is a block element</div>
<div>Another block element</div>
```

위의 코드를 보면, 각 `div` 요소가 한 줄씩 차지하여 배치됩니다.<br>
block 요소는 너비와 높이, 마진, 패딩 등을 자유롭게 설정할 수 있습니다.

<br>

### Inline-Block

`inline-block` 요소는 `inline`과 `block` 속성의 특징을 모두 가지고 있습니다.<br>
기본적으로는 inline 요소처럼 동작하지만, 너비와 높이를 설정할 수 있으며, line-height도 적용할 수 있습니다. <br>
또한, 줄바꿈 없이 동일한 라인에 배치할 수 있습니다.
<br>

```html
<span style="display:inline-block; width:100px; height:50px;"
  >Inline-block element</span
>
<span style="display:inline-block; width:100px; height:50px;"
  >Another inline-block</span
>
```

위의 코드를 보면, inline-block 요소들이 한 줄에 나란히 배치되지만, 너비와 높이를 설정하여 블록 요소처럼 크기를 조절할 수 있습니다.

<br>

## ✨비교 요약

- Inline: 텍스트 크기만큼 공간을 차지하며, 줄바꿈이 되지 않습니다. 너비와 높이를 설정할 수 없습니다.
- Block: 한 줄 전체를 차지하며, 다음 요소는 줄바꿈됩니다. 너비와 높이, 마진, 패딩 등을 설정할 수 있습니다.
- Inline-Block: inline과 같은 라인에 배치되지만, 너비와 높이를 설정할 수 있습니다. 줄바꿈 없이 배치되며, 블록 요소처럼 크기를 조절할 수 있습니다.

<br>

## 활용 예시

Inline: 텍스트 내부의 일부를 스타일링할 때 사용합니다. 예를 들어, 강조 표시나 링크 등을 스타일링할 때 유용합니다.

```html
<p>This is a <span style="color:red;">highlighted</span> text.</p>
```

<br>

Block: 레이아웃을 구성할 때 사용합니다. 섹션을 구분하거나, 컨테이너를 만들 때 주로 사용됩니다.

```html
<div style="border:1px solid black; padding:10px;">
  <p>This is a block container.</p>
</div>
```

<br>

Inline-Block: 레이아웃을 구성하면서, 요소를 한 줄에 배치하고 싶을 때 사용합니다. <br>
버튼이나 메뉴 항목 등을 스타일링할 때 유용합니다.

```html
<span style="display:inline-block; padding:10px; border:1px solid black;"
  >Button 1</span
>
<span style="display:inline-block; padding:10px; border:1px solid black;"
  >Button 2</span
>
```

## 결론

CSS의 display 속성은 요소의 레이아웃과 배치에 큰 영향을 미칩니다. <br>
inline, block, inline-block의 차이점을 이해하면 더 효과적이고 유연하게 웹 페이지를 디자인할 수 있습니다. <br>
