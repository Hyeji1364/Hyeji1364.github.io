---
layout: post
title: 폼 관련 요소 및 주요 속성 (1)
date: 2024-05-08 20:25 +0900
description: 폼 관련 요소 및 주요 속성에 대해 알아보기!
image: ../assets/img/html.gif
category: HTML
tags: HTML 폼요소
published: true
sitemap: true
---

## HTML

### 폼 관련 요소 및 주요 속성 (1)

<hr>

오늘은 폼 관련 요소 및 주요 속성에 대해 알아보는 시간을 가지겠습니다. <br>
폼 관련 요소는 내용이 길어 두 파트로 나눠서 다뤄보겠습니다. 또한, HTML에서 중요 속성이라고 생각하기 때문에 포스팅해보겠습니다.

#### 🎈 01-1. 폼
요소 유형 : 블록 레벨 요소 <br>

✔ 태그명 : 'form' <br>
✔  태그의 의미 및 특징 <br>
- 온라인 서식(검색, 로그인, 회원가입 등)에서 입력한 값들을 처리하는 프로그램으로 전송할 때 사용하는 태그입니다.
<br>

- 텍스트, 인라인 요소, 블록 레벨 요소를 포함할 수 있습니다. 일반적으로 서식(사용자 입력)에 관련된 태그들을 포함합니다.

##### ✅ action: 폼 데이터가 서버로 제출될 URL을 지정합니다.<br>                              

##### ✅ method: 데이터를 서버로 전송하는 방식을 지정합니다 (GET 또는 POST) <br>

- GET 방식 : 보통 `검색`은 GET 방식을 씁니다.<br>
- POST 방식 : 보통 `로그인` , `회원가입` 처럼 중요한 정보를 전송할 때는 POST 방식을 사용합니다.

##### ✅ enctype: 폼 데이터가 서버로 인코딩되는 방식을 지정합니다. 파일이나 이미지를 전송할 때 중요합니다. 예를 들어, 'multipart/form-data.'

##### ✅ novalidate: 이 속성이 설정되면 폼 제출 시 HTML5 폼 유효성 검사를 비활성화합니다. <br>

##### ✅ target: 폼을 제출할 때 응답이 표시될 위치를 지정합니다. (예: _blank, _self 등) <br>

#### 🎈 01-2. fieldset
✔ 태그명 : 'fieldset' <br>   
✔  태그의 의미 및 특징 <br>
- 양식 요소들을 그룹화 할 때 사용하는 태그입니다.<br>
- 텍스트, 인라인 요소, 블록 레벨 요소를 포함할 수 있습니다.<br>
- 그룹화 된 서식의 제목을 정의할 수 있는 'legend' 태그를 자식 요소로 포함합니다.

````html
<!DOCTYPE html>
<html lang="ko">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>폼</title>
</head>

<body>
    <form action="#" method="post">
        <fieldset>
            <legend>로그인</legend>
            <p>ID : <input type="text"></p>
            <p>PASSWORD : <input type="password"></p>
        </fieldset>
    </form>
</body>

</html>
````

이 HTML을 작성하면 이런 형식의 웹 페이지가 표시됩니다.

![image](https://github.com/Hyeji1364/class2024/assets/161557112/e9574e63-30ff-439b-a2a0-6e2abb8b703f)

<hr>

#### 🎈 input 태그 : 한줄 입력 요소

##### ✅type: 입력 필드의 유형을 지정합니다 (text, password, email, checkbox, radio, 등)<br>
##### ✅name: 폼 데이터와 함께 제출될 때 사용되는 필드의 이름을 지정합니다.<br>

##### ✅value: 입력 필드의 초기 값이나 버튼에 표시될 텍스트를 지정합니다.<br>

##### ✅placeholder: 필드에 입력하기 전에 표시되는 단서(placeholder) 텍스트를 지정합니다.<br>

##### ✅required: 필드가 반드시 필요함을 지정하여, 이 필드 없이는 폼을 제출할 수 없습니다.<br>

##### ✅readonly: 사용자가 입력 필드를 수정할 수 없도록 설정합니다.<br>

##### ✅disabled: 필드를 비활성화합니다. 비활성화된 필드는 폼 데이터로 제출되지 않습니다.<br>