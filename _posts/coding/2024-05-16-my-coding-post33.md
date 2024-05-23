---
layout: post
title: data 속성
date: 2024-05-15 10:00 +0900
description: data 속성
image: ../assets/img/data.png
category: HTML
tags: data 속성
published: true
sitemap: true
---

## data속성 
오늘은 data 속성에 대해 알아보겠습니다.
<br>

HTML5에서 도입된 data-* 속성은 개발자가 사용자 정의 데이터를 HTML 요소에 저장할 수 있도록 합니다.<br>
이 속성은 data-로 시작하고 그 뒤에 사용자 정의 이름이 오는 형태를 가지며, 자바스크립트와 CSS를 통해 쉽게 접근할 수 있습니다.<br>
특정한 데이터를 DOM 요소에 저장해두기 위함이 목적입니다.<br>
특히 동적인 웹 애플리케이션에서 유용하게 사용됩니다.

### HTML의 data-* 속성
HTML 코드에서 data-* 속성을 사용하여 사용자 정의 데이터를 저장할 수 있습니다.

🔍 사용예시

````html
<div id="product" data-id="12345" data-name="Widget" data-price="19.99">
  Product Information
</div>
````
위의 예제에서 div 요소는 data-id, data-name, data-price 속성을 가지고 있으며, 각각의 값은 "12345", "Widget", "19.99"입니다.

### 자바스크립트를 통한 접근
자바스크립트를 사용하여 data-* 속성에 접근하고 조작할 수 있습니다. HTML 요소의 dataset 속성을 통해 접근할 수 있습니다.

🔍 사용예시

````html
<script>
  document.addEventListener("DOMContentLoaded", function() {
    const product = document.getElementById('product');
    const productId = product.dataset.id;
    const productName = product.dataset.name;
    const productPrice = product.dataset.price;

    console.log(productId);  // "12345"
    console.log(productName);  // "Widget"
    console.log(productPrice);  // "19.99"
  });
</script>
````

### CSS를 통한 접근
CSS를 통해서는 직접 data-* 속성 값을 기반으로 스타일을 지정할 수는 없지만, [attribute] 선택자를 사용하여 특정 data-* 속성을 가진 요소를 스타일링할 수 있습니다.

🔍 사용예시

````html
<style>
  div[data-price="19.99"] {
    color: green;
    font-weight: bold;
  }
</style>
````
위의 예제에서는 data-price 속성이 "19.99"인 div 요소에 대해 텍스트 색상을 녹색으로 하고, 글씨를 굵게 표시합니다.<br>

그렇다면 각 요소의 자세한 예시를 다시 들어보고, 정리하는 시간을 가지겠습니다.

## 실용적인 예제

### HTML 코드
````html
<ul>
  <li data-category="fruit" data-price="2">Apple</li>
  <li data-category="vegetable" data-price="1">Carrot</li>
  <li data-category="fruit" data-price="3">Banana</li>
  <li data-category="vegetable" data-price="2">Lettuce</li>
</ul>

````

### 자바스크립트 코드

````html
<script>
  document.addEventListener("DOMContentLoaded", function() {
    const items = document.querySelectorAll('li');
    
    items.forEach(item => {
      const category = item.dataset.category;
      const price = item.dataset.price;
      
      console.log(`Category: ${category}, Price: ${price}`);
    });
  });
</script>
````

### CSS 코드
````html
<style>
  li[data-category="fruit"] {
    color: red;
  }
  
  li[data-category="vegetable"] {
    color: green;
  }
</style>
````

## 요약
- <b>HTML의 data-* 속성</b>: 사용자 정의 데이터를 HTML 요소에 저장하기 위한 속성. data-로 시작하고 뒤에 사용자 정의 이름을 붙입니다.
- <b>자바스크립트를 통한 접근</b>: element.dataset을 사용하여 접근하고 조작할 수 있습니다.
- <b>CSS를 통한 접근</b>: [attribute] 선택자를 사용하여 특정 data-* 속성을 가진 요소를 스타일링할 수 있습니다.
<br>
data-* 속성은 웹 애플리케이션에서 데이터를 저장하고 조작하는 데 매우 유용하며, HTML, CSS, 자바스크립트를 결합하여 동적인 사용자 경험을 제공할 수 있습니다.