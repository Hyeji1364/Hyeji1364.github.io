---
layout: post
title: 폼 관련 요소 및 주요 속성 (2)
date: 2024-05-09 18:47 +0900
description: 폼 관련 요소 및 주요 속성에 대해 알아보기!
image: ../assets/img/html.gif
category: HTML
tags: HTML 폼
published: true
sitemap: true
---

## HTML

### 폼 관련 요소 및 주요 속성 (2)

<hr>

오늘은 폼 관련 요소 및 주요 속성 두번째에 대해 알아보는 시간을 가지겠습니다. <br>
지난 시간에 폼 관련 속성에 대해 폼 태그, input태그에 대해 알아보았습니다.
이번 시간에는 첫번째 시간에 알아보았던 내용을 제외한 폼 관련 요소 및 주요 속성에 대해 알아보겠습니다. 

#### 🎈 01. textarea, select : 여러 줄 입력 요소
✔ 요소 유형 : 인라인 요소 <br>

##### ✔ 태그명 : 'textarea' <br>
✔ 태그의 의미 및 특징 <br>
- 여러 줄 텍스트 입력 상자 태그입니다.<br>
- 주로 긴 텍스트 입력이 필요한 경우에 사용되며, 댓글, 메시지, 기타 텍스트 기반 입력을 위한 공간을 제공합니다.<br>
- rows 속성과 cols 속성으로 텍스트 입력 상자의 행과 열 수를 지정할 수 있습니다.<br>


###### ✅ textarea 태그의 기본 구조
````html
<textarea name="message" rows="10" cols="50">
여기에 초기에 표시할 텍스트를 입력하세요.
</textarea>
````
- name: 폼 데이터와 함께 서버로 전송될 때 사용되는 이름입니다.<br>
- rows: 텍스트 영역의 높이를 줄 단위로 지정합니다. <br>
- cols: 텍스트 영역의 너비를 문자 단위로 지정합니다. <br>

<br>

👀 <textarea>는 여러 가지 HTML 속성을 사용하여 세부적으로 구성할 수 있습니다. <br>
<br>
- placeholder: 사용자에게 입력 필드의 예상 입력을 알려줄 수 있는 안내 텍스트를 제공합니다. 입력 시작 시 텍스트가 사라집니다. <br>
- readonly: 이 속성이 설정되면 사용자는 텍스트 영역의 내용을 수정할 수 없습니다. 단지 읽기만 가능합니다.<br>
- disabled: 이 속성이 설정되면 텍스트 영역이 비활성화됩니다. 폼 제출 시 데이터도 함께 전송되지 않습니다. <br>
- maxlength: 사용자가 입력할 수 있는 최대 문자 수를 제한합니다.<br>
- required: 폼이 제출되기 전에 사용자가 반드시 텍스트 영역에 데이터를 입력해야 합니다.<br>
- autofocus: 페이지 로드 시 자동으로 이 요소에 포커스가 맞춰집니다. <br>

#### 🎈 02. select : 선택 요소

##### ✔ 태그명 : 'select' <br>
✔ 태그의 의미 및 특징 <br>
- HTML에서 사용자에게 드롭다운 목록 형태의 선택 옵션을 제공하는 폼 요소입니다. <br>
- 선택 목록 상자 태그입니다.<br>
- option 태그 외에 다른 태그는 자식 요소로 올 수 없습니다. <br>
- option 태그에 selected 속성이 정의되면 웹 페이지 실행 시 해당 option 태그가 기본 목록으로 표시됩니다. <br>

###### ✅ select 태그의 기본 구조

````html
<select name="car" id="car">
  <option value="volvo">Volvo</option>
  <option value="saab">Saab</option>
  <option value="mercedes">Mercedes</option>
  <option value="audi">Audi</option>
</select>
````

- name: 폼 데이터와 함께 서버로 전송될 때 사용되는 필드의 이름입니다.
- id: CSS 스타일링이나 JavaScript 조작을 위해 요소를 식별하는 데 사용됩니다.

<br>

#### 🎈 03. option 태그
HTML에서 'form'태그는 사용자 입력을 수집하기 위한 양식을 정의하는 데 사용되며, 여러 종류의 입력 필드와 요소들을 포함할 수 있습니다.<br>
이러한 요소들 중 하나가 'option' 태그입니다.<br>
'option' 태그는 드롭다운 목록, 리스트박스 등에서 사용자가 선택할 수 있는 개별 항목을 정의합니다. <br>이 태그는 항상 'select 또는 'datalist' 요소 내부에 위치해야 합니다.
<br>

✔ 태그의 의미 및 특징 <br>
- option 태그는 select 내부에서 개별 선택 가능한 아이템을 정의합니다. <br>
- value: 서버로 전송될 때 사용될 값입니다. value 속성이 지정되지 않은 경우, 옵션의 텍스트 내용이 값으로 사용됩니다. <br>
- selected: 이 속성이 설정되면, 페이지 로드 시 해당 옵션이 기본적으로 선택됩니다. <br>
- disabled: 옵션을 비활성화하여 사용자가 선택할 수 없게 합니다. <br>
- label: 옵션을 설명하는 더 짧고 명확한 라벨을 제공할 때 사용합니다. 일반적으로 보이는 텍스트와 다를 수 있습니다.

#### 🎈 04. button 태그
✔ 태그의 의미<br>

HTML에서 'button'태그는 사용자가클릭할 수 있는 버튼을 정의할 때 사용됩니다.<br>
이 버튼은 폼 제출, 명령 실행, 사용자 상호작용 등 다양한 기능을 수행할 수 있으며, <form> 태그 안팎에서 사용될 수 있습니다.<br>
<br>

✔ button 태그의 특징
- 유연성: 'button' 태그는 텍스트 또는 이미지와 같은 HTML 요소를 포함할 수 있어, 다양한 스타일과 내용의 버튼을 만들 수 있습니다. <br>
- 속성<br>
  1) type: 버튼의 유형을 지정합니다. 기본값은 "submit"이며, 폼을 제출할 때 사용됩니다. 다른 값으로는 "button", "reset"이 있습니다. "button"은 표준 버튼을, "reset"은 폼 입력 필드를 초기화하는 버튼을 만듭니다.<br>

  2) disabled: 이 속성이 설정되면 버튼은 비활성화되어 사용자가 클릭할 수 없습니다.<br>

  3) form: 버튼이 폼과 연결될 때, 해당 폼의 ID를 지정합니다. 이는 버튼이 해당 폼 외부에 위치할 때 유용합니다.<br>

✅ 예제 코드

  ````html
  <!DOCTYPE html>
<html>
<head>
    <title>Button Example</title>
</head>
<body>
    <!-- 일반 버튼 -->
    <button type="button" onclick="alert('Clicked!')">Click Me!</button>

    <!-- 폼 제출 버튼 -->
    <form action="/submit_form" method="post">
        <button type="submit">Submit</button>
    </form>

    <!-- 폼 리셋 버튼 -->
    <form>
        <input type="text" name="name" placeholder="Enter your name">
        <button type="reset">Reset</button>
    </form>

    <!-- 비활성화된 버튼 -->
    <button type="button" disabled>Disabled Button</button>
</body>
</html>
  ````
      
      
      
실행하면 다음과 같은 사진이 뜹니다.
![image](https://github.com/Hyeji1364/class2024/assets/161557112/d882e81d-187a-4cf5-b19e-c58b851709b4)
