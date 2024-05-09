---
layout: post
title: 폼 관련 요소 및 주요 속성 (1)
date: 2024-05-09 01:25 +0900
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

##### ✅ action: 폼 데이터가 서버로 제출될 URL을 지정합니다.                             
##### ✅ method: 데이터를 서버로 전송하는 방식을 지정합니다.(GET 또는 POST)

- GET 방식 : 보통 `검색`은 GET 방식을 씁니다.<br>
- POST 방식 : 보통 `로그인` , `회원가입` 처럼 중요한 정보를 전송할 때는 POST 방식을 사용합니다.

##### ✅ enctype: 폼 데이터가 서버로 인코딩되는 방식을 지정합니다. 파일이나 이미지를 전송할 때 중요합니다. 예를 들어, 'multipart/form-data.'

##### ✅ novalidate: 이 속성이 설정되면 폼 제출 시 HTML5 폼 유효성 검사를 비활성화합니다.

##### ✅ target: 폼을 제출할 때 응답이 표시될 위치를 지정합니다. (예: _blank, _self 등)

#### 🎈 01-2. fieldset
✔ 태그명 : 'fieldset' <br>   
✔ 태그의 의미 및 특징 <br>
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

#### 🎈 02. input 태그

요소 유형 : 인라인 요소 <br>

✔ 태그명 : input <br>
✔ 태그의 의미 및 특징 <br>
- 사용자로부터 데이터 값을 입력받기 위한 태그입니다.
- type 속성 값에 따라 다양한 폼 컨트롤을 생성할 수 있습니다.
- 공통 속성으로 name, value 속성이 있습니다.

##### type: 입력 필드의 유형을 지정합니다 (text, password, email, checkbox, radio, 등)

✔ type속성 값
- text <br>
한 줄 글 입력 상자
maxlength 속성으로 최대 글자 수를 제한할 수 있다.
- password<br>
입력된 내용은 '*'로 표시 
- search<br>
- email<br>
- tel : 전화번호 입력 상자<br>
- color<br>
- number : 숫자 입력 상자<br>
숫자의 최솟값, 최댓값을 min, max속성으로 지정할 수 있다.<br>
- range : 슬라이드 바<br>
최솟값, 최댓값을 min, max 속성으로 지정할 수 있다.<br>
- radio: 라디오 버튼<br>
여러 개 radio 중 하나만 선택 가능하다.(요소의 name 속성이 같아야 함)
````
이메일 수신 여부:
예 <input type="radio" name="email">
아니오 <input type="radio" name="email">
````
- checkbox : 체크박스<br>
다중 선택이 가능하다.<br>
checked 속성을 정의하면 웹 페이지 실행 시 해당 checkbox가 기본으로 정의됨<br>
- submit : 전송 버튼<br>
`value`속성으로 버튼에 표시되는 텍스트를 지정<br>
- reset : 초기화 버튼<br>
`value`속성으로 버튼에 표시되는 텍스트를 지정<br>
- button : 범용 버튼<br>
`value`속성으로 버튼에 표시되는 텍스트를 지정<br>
- image : 이미지 버튼<br>
alt 속성을 반드시 정의해야 함<br>
- file : 첨부 파일
- hidden<br>
사용자에게 노출할 필요가 없는 데이터를 지정<br>
화면에 표시되지 않음

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
            <legend>type 속성</legend>
            <p>아이디 : <input type="text"></p>
            <p>비밀번호 : <input type="password"></p>
            <p>검색 : <input type="search"></p>
            <p>전화번호 : <input type="tel"></p>
            <p>컬러선택 : <input type="color"></p>
            <p>수량 : <input type="number" min="1" max="10" value="1"></p>
            <p>만족도 : <input type="range" min="1" max="10" value="1"></p>
            <p>예 : <input type="radio" name="receive" checked="checked"> css <input type="checkbox"></p>
            <p><input type="submit" value="전송"></p>
            <p><input type="reset" value="취소"></p>
            <p><input type="button" value="확인"></p>
            <p><input type="file"></p>
        </fieldset>
    </form>
</body>

</html>
````
위의 예시는 type속성값을 작성한 예시입니다.

이것을 화면에 구현한 웹페이지입니다.
![image](https://github.com/Hyeji1364/class2024/assets/161557112/61e29ea7-e949-4642-8032-39a4eadb8d16)

##### name: 폼 데이터와 함께 제출될 때 사용되는 필드의 이름을 지정합니다.

##### value: 입력 필드의 초기 값이나 버튼에 표시될 텍스트를 지정합니다.

##### placeholder: 필드에 입력하기 전에 표시되는 단서(placeholder) 텍스트를 지정합니다.

##### required: 필드가 반드시 필요함을 지정하여, 이 필드 없이는 폼을 제출할 수 없습니다.

##### readonly: 사용자가 입력 필드를 수정할 수 없도록 설정합니다.

##### disabled: 필드를 비활성화합니다. 비활성화된 필드는 폼 데이터로 제출되지 않습니다.
