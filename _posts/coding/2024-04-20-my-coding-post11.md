---
layout: post
title: HTML
date: 2024-04-20 22: +0900
description: 
image: ../assets/img/htmlgif.gif
category: HTML
tags: HTML 텍스트
published: true
sitemap: true
---

## HTML

### 텍스트 및 목록 관련 요소

오늘은 제일 기본이 되는 HTML의 텍스트 관련 요소와
목록 관련 요소에 대해서도 간략하게 알아보겠습니다.

<hr />

> ### 💛 텍스트 관련 요소

#### <mark> 요소유형 : 인라인 요소 </mark>

🎈em
<br>
<em>
강조하고 싶은 텍스트를 정의하기 위한 태그, 기울임체로 표시됨

🎈strong
<br>
<strong>
중요한 텍스트를 정의하기 위한 태그이며 굵은체로 표시

🎈mark
<br>
<mark>
주의깊게 볼 텍스트 부분을 강조하기 위한 태그이며 노란색으로 표시됨

🎈b
<br>
<b>
의미를 갖고 있지 않으며 단순히 텍스트를 굵은체로 표시함

🎈 small
<br>
<small>
주의 사항, 법적 제한, 저작권 등을 정의하기 위한 태그이며 작은 글씨로 표시됨

🎈 sub
<br>
<sub>
아래첨자 텍스트를 정의하기 위한 태그
</sub>

🎈 sup
<br>
<sup>
위첨자 텍스트를 정의하기 위한 태그
</sup>

---

> ### 💛 목록 관련 요소

#### <mark>블록 레벨 요소</mark>

<br>

#### 🎈 순서 목록 'ol'
* Order List의 약자로 순서 목록을 정의할 때 사용하는 태그입니다.

* 자식 요소로 반드시 li 태그를 정의해주어야 하며, li 태그 이외의 다른 태그는 자식 요소로 올 수 없습니다.


````html
<ol>
    <li></li>
</ol>
````

❌ 잘못된 예:
````html
<ol>
</ol>
````

````html
<ol>
    <p></p>
</ol>
````

````html
<ol>
    <div>
        <li></li>
    </div>
</ol>
````
<br>


#### 🎈비순서 목록 'ui'

* Unorder List의 약자로 비순서 목록을 정의할 때 사용하는 태그입니다.

* 자식 요소로 반드시 li 태그를 정의해주어야 하며, li 태그 이외의 다른 태그는 자식 요소로 올 수 없습니다.
<br>

⭕ 올바른 예 :
````html
<ul>
    <li></li>
</ul>
````

❌ 잘못된 예:
````html
<ul>
</ul>
````

````html
<ul>
    <p></p>
</ul>
````

````html
<ul>
    <div>
        <li></li>
    </div>
</ul>
````

#### ✔ 'li'
* list items로 항목을 정의할 때 사용하는 태그입니다.
ol, ul 태그의 자식 요소입니다.

* 텍스트, 인라인 요소, 블록 레벨 요소를 모두 포함할 수 있습니다.

````html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>순서 목록</title>
</head>
<body>
    <h1>반응형 웹퍼블리싱 학습 순서</h1>
    <ol>
        <li>html</li>
        <li>css</li>
        <li>javascript</li>
        <li>jquery</li>
        <li>exercise</li>
    </ol>
</body>
</html>
````
<br>

✔ HTML 문서의 디자인 콘텐츠 구성은 대부분 <mark>비순서</mark> 목록으로 되어 있기 때문에, 그만큼 'ul' 태그가 많이 사용됩니다. ul 태그에서는 중첩된 ul 구조를 이해하고 마크업 할 수 있어야 하는데, HTML 문서에서 많이 사용되는 주 메뉴(2단 메뉴)가 중첩된 ul 구조를 가지고 있기 때문입니다.

그럼 여기서 ul과 li를 사용한 메뉴의 예시를 보겠습니다.

````html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>

<body>
    <ul>
        <li>
            <a href="#">메뉴1</a>
            <ul><!--메뉴1의 서브메뉴-->
                <li><a href="#">메뉴1_1</a></li>
                <li><a href="#">메뉴1_2</a></li>
                <li><a href="#">메뉴1_3</a></li>
            </ul>
        </li>
        <li><a href="#">메뉴2</a>
            <ul><!--메뉴2의 서브메뉴-->
                <li><a href="#">메뉴2-1</a></li>
                <li><a href="#">메뉴2-2</a></li>
                <li><a href="#">메뉴2-3</a></li>
            </ul>
        </li>
        <li><a href="#">메뉴3</a>
            <ul><!--메뉴3/의 서브메뉴-->
                <li><a href="#">메뉴2-1</a></li>
                <li><a href="#">메뉴2-2</a></li>
                <li><a href="#">메뉴2-3</a></li>
            </ul>
        </li>
    </ul>
</body>
</html>
````

![image](https://github.com/Hyeji1364/Hyeji1364.github.io/assets/161557112/5f18bde6-c458-42d8-839e-9308de1e364f)

3단 구조 마크업도 방법은 동일합니다.

#### 🎈설명 목록 'dl'

* Description List의 약자로 용어에 대한 설명 목록을 정의할 때 사용하는 태그입니다.

* 자식 요소로 반드시 'dt'태그와 'dd'태그를 정의해 주어야 하며 dl > dt > dd순으로 마크업해야 합니다. dl 태그는 dt, dd 이외의 태그는 자식 요소로 올 수 없지만, dt, dd을 한 쌍으로 묶는 div태그는 예외적으로 올 수 있습니다.

*️⃣ dt<br>

* Description Term의 약자로 설명 목록의 용어를 정의합니다.

* 텍스트, 인라인 요소, 블록 레벨 요소를 모두 포함할 수 있습니다.

*️⃣ dd <br>

* Description Details의 약자로 용어에 대한 세부 설명을 정의합니다.

* 텍스트, 인라인 요소, 블록 레벨 요소를 모두 포함할 수 있습니다.

⭕ 올바른 예 :
````html
<dl>
    <dt></dt>
    <dd></dd>
</dl>
````

````html
<dl>
    <dt></dt>
    <dd></dd>
    <dt></dt>
    <dd></dd>
</dl>
````

````html
<dl>
    <div>
        <dt></dt>
        <dd></dd>
    </div>
</dl>
````
<br>

❌ 잘못된 예:
````html
<dl>
    <div>
        <dt></dt>
        <dd></dd>
        <dd></dd>
    </div>
</dl>
````

````html
<dl>
    <dd></dd>
    <dt></dt>
</dl>
````
➡ 순서는 dl > dt > dd순으로 와야 한다!

````html
<dl>
    <p>
        <dt></dt>
        <dd></dd>
    </p>
</dl>
````


