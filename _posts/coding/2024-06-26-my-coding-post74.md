---
layout: post
title: id와 class의 차이점
date: 2024-06-25 10:00 +0900
description: id와 class의 차이점
image: https://github.com/Hyeji1364/class2024/assets/161557112/7d6d753f-604b-43a6-915e-c0c0d4a82356
category: HTML
tags: HTML CSS
published: true
sitemap: true
---

# HTML 속성

## id와 class의 차이점

웹 개발에서 HTML 요소에 스타일을 적용하거나 자바스크립트를 통해 요소를 조작할 때, id와 class 속성은 매우 중요한 역할을 합니다.<br>
이 두 속성은 요소를 식별하고 그룹화하는 데 사용되지만, 그 목적과 사용 방법에 있어 차이가 있습니다. <br>
이번 글에서는 id와 class 속성의 차이점을 명확히 알아보고, 각각의 사용 사례를 살펴보겠습니다.

## 💛 id 속성

id 속성은 HTML 요소에 고유한 식별자를 부여합니다. <br>
이는 문서 내에서 단 하나의 요소에만 적용될 수 있습니다. <br>
id는 특정 요소를 유일하게 식별할 때 사용되며, CSS나 자바스크립트를 통해 해당 요소를 정확하게 타겟팅할 수 있게 합니다.

<br>

### id 속성의 주요 특징

#### 01. 고유성

id는 문서 내에서 유일해야 합니다. 즉, 동일한 id를 가진 두 개 이상의 요소가 있어서는 안 됩니다.

#### 02. CSS 타겟팅

`id`는 CSS에서 `#` 기호를 사용하여 스타일을 적용할 수 있습니다.

#### 03.자바스크립트 접근

자바스크립트에서 `document.getElementById` 메서드를 사용하여 특정 요소를 선택할 수 있습니다.

<br>

#### id속성의 예제

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>ID Example</title>
    <style>
      #uniqueElement {
        color: red;
        font-weight: bold;
      }
    </style>
  </head>
  <body>
    <div id="uniqueElement">This is a unique element with an ID.</div>
  </body>
</html>
```

위 예제에서 `id="uniqueElement"`를 가진 `<div>` 요소는 CSS에서 `#uniqueElement` 선택자를 통해 스타일이 적용됩니다.

<br>

## 💛 class속성

class 속성은 HTML 요소를 그룹화하는 데 사용됩니다. <br>
동일한 class를 여러 요소에 적용할 수 있으며, 이를 통해 CSS나 자바스크립트에서 공통 스타일이나 기능을 부여할 수 있습니다.
<br>

### class 속성의 주요 특징

#### 01. 중복 가능

여러 요소가 동일한 `class`를 가질 수 있습니다. 이를 통해 공통 스타일을 쉽게 적용할 수 있습니다.

#### 02. CSS 타겟팅

class는 CSS에서 `.` 기호를 사용하여 스타일을 적용할 수 있습니다.

#### 03. 자바스크립트 접근

자바스크립트에서 `document.getElementsByClassName` 메서드를 사용하여 특정 클래스를 가진 모든 요소를 선택할 수 있습니다.
<br>

#### class 속성의 예제

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Class Example</title>
    <style>
      .highlight {
        color: blue;
        background-color: yellow;
      }
    </style>
  </head>
  <body>
    <p class="highlight">This paragraph is highlighted.</p>
    <p class="highlight">This paragraph is also highlighted.</p>
    <p>This paragraph is not highlighted.</p>
  </body>
</html>
```

위 예제에서 `class="highlight"`를 가진 두 개의 `<p>` 요소는 CSS에서 `.highlight` 선택자를 통해 스타일이 적용됩니다.
<br>

## id와 class의 차이점 요약

### 01. 고유성

id는 문서 내에서 고유해야 하며, 한 요소에만 적용될 수 있습니다. <br>
반면, class는 여러 요소에 중복 적용될 수 있습니다.

### 02. 선택자

CSS에서 id는 `#` 기호를 사용하고, class는 `.` 기호를 사용합니다.

### 03. 사용 목적

id는 특정 요소를 유일하게 식별할 때 사용되며, class는 여러 요소를 그룹화하여 공통 스타일이나 기능을 적용할 때 사용됩니다.

### 04. 자바스크립트 접근 방법

자바스크립트에서 id는 `document.getElementById`를 사용하여 접근하고, class는 `document.getElementsByClassName` 또는 `document.querySelectorAll`을 사용하여 접근합니다.

<br>

## 결론 ✨

id와 class 속성은 HTML 문서에서 요소를 식별하고 스타일을 적용하거나 자바스크립트를 통해 조작하는 데 필수적인 도구입니다. <br>
id는 고유한 식별자를 부여하여 특정 요소를 타겟팅하는 데 사용되며, class는 여러 요소를 그룹화하여 공통 스타일이나 기능을 적용하는 데 사용됩니다. <br>
이 두 속성을 적절히 활용하면, 웹 페이지를 보다 효율적으로 관리하고 스타일링할 수 있습니다.
