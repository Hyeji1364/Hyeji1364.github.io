---
layout: post
title: Javascript ajax
date: 2024-06-05 10:00 +0900
description: Javascript ajax
image: ../assets/img/javascript17.png
category: Javascript
tags: Javascript ajax
published: true
sitemap: true
---

# Javascript

## 🍳 AJAX

웹 페이지를 새로 고침하지 않고 서버와 통신할 수 있게 해주는 기술입니다.<br>
AJAX를 사용하면 웹 애플리케이션이 비동기적으로 데이터를 주고받을 수 있으며, 사용자 경험을 향상시키는 데 중요한 역할을 합니다. <br>
AJAX의 핵심 개념과 사용법에 대해 자세히 알아보겠습니다.

<br>

### 🍳 AJAX의 기본 개념

AJAX는 Asynchronous JavaScript and XML의 약자로, 자바스크립트를 통해 비동기적으로 서버와 통신하여 XML 데이터를 주고받는 것을 의미합니다. <br>
하지만 현대 웹에서는 XML뿐만 아니라 JSON, HTML, 일반 텍스트 등 다양한 포맷의 데이터를 주고받을 수 있습니다. <br>
AJAX의 주요 목적은 웹 페이지를 새로 고침하지 않고도 서버에서 데이터를 가져오거나 서버로 데이터를 보낼 수 있도록 하는 것입니다.
<br>

### AJAX의 주요 구성 요소

1. XMLHttpRequest 객체
   AJAX 요청을 생성하고 서버와 데이터를 주고받기 위해 사용되는 자바스크립트 객체입니다.<br>
   최신 브라우저에서는 fetch API가 대체제로 사용되기도 합니다.
   <br>

2. 서버
   AJAX 요청을 처리하고 응답을 반환하는 서버입니다. <br>
   서버는 다양한 언어로 작성될 수 있으며, 데이터베이스와의 상호작용, 파일 처리, 비즈니스 로직 등을 담당합니다.
   <br>

3. 데이터 포맷
   서버와 클라이언트 간에 주고받는 데이터의 포맷으로, XML, JSON, HTML, 텍스트 등이 있습니다.
   <br>

#### XMLHttpRequest를 사용한 AJAX

XMLHttpRequest 객체를 사용하여 AJAX 요청을 보내는 방법을 단계별로 설명하겠습니다.

1. XMLHttpRequest 객체 생성

```javascript
let xhr = new XMLHttpRequest();
```

2. 요청 준비
   `open` 메서드를 사용하여 요청을 초기화합니다. 첫 번째 인자는 HTTP 메서드(GET, POST 등)이며, 두 번째 인자는 요청할 URL입니다.

```javascript
xhr.open("GET", "https://api.example.com/data", true);
```

<br>

3. 요청 전송
   `send` 메서드를 사용하여 요청을 서버로 전송합니다.

```javascript
xhr.send();
```

<br>

4. 응답 처리
   `onreadystatechange` 이벤트 핸들러를 사용하여 서버 응답을 처리합니다. <br>
   `readyState`가 4이고 `status`가 200이면 요청이 성공적으로 완료된 것입니다.

```javascript
xhr.onreadystatechange = function () {
  if (xhr.readyState === 4 && xhr.status === 200) {
    console.log(xhr.responseText);
  }
};
```

#### 예시 : GET요청

다음은 XMLHttpRequest를 사용하여 서버에서 데이터를 가져오는 간단한 예시입니다.

```javascript
let xhr = new XMLHttpRequest();
xhr.open("GET", "https://api.example.com/data", true);
xhr.onreadystatechange = function () {
  if (xhr.readyState === 4 && xhr.status === 200) {
    let data = JSON.parse(xhr.responseText);
    console.log(data);
  }
};
xhr.send();
```

<br>

#### 예시: POST 요청

POST 요청을 보내는 방법은 send 메서드에 데이터를 포함시키는 것입니다.

```javascript
let xhr = new XMLHttpRequest();
xhr.open("POST", "https://api.example.com/data", true);
xhr.setRequestHeader("Content-Type", "application/json;charset=UTF-8");
xhr.onreadystatechange = function () {
  if (xhr.readyState === 4 && xhr.status === 200) {
    console.log(xhr.responseText);
  }
};
let data = JSON.stringify({ name: "John", age: 30 });
xhr.send(data);
```

#### Fetch API

XMLHttpRequest의 대안으로, Fetch API를 사용하면 더 간단하고 직관적으로 비동기 요청을 처리할 수 있습니다.

```javascript
fetch("https://api.example.com/data")
  .then((response) => response.json())
  .then((data) => console.log(data))
  .catch((error) => console.error("Error:", error));
```

<br>

POST 요청의 경우:

```javascript
fetch("https://api.example.com/data", {
  method: "POST",
  headers: {
    "Content-Type": "application/json",
  },
  body: JSON.stringify({ name: "John", age: 30 }),
})
  .then((response) => response.json())
  .then((data) => console.log(data))
  .catch((error) => console.error("Error:", error));
```

### 결론

AJAX는 자바스크립트를 사용하여 비동기적으로 서버와 통신하고, 웹 페이지를 새로 고침하지 않고도 동적으로 콘텐츠를 업데이트할 수 있게 해주는 강력한 기술입니다. <br>
XMLHttpRequest 객체와 Fetch API는 AJAX 요청을 보내고 서버 응답을 처리하는 데 사용됩니다. 이러한 기술을 통해 사용자 경험을 크게 향상시킬 수 있습니다.
