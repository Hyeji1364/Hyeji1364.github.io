---
layout: post
title: 시멘틱 태그
date: 2024-05-14 10:00 +0900
description: 시멘틱 태그
image: ../assets/img/tag.png
category: coding
tags: HTML CSS 시멘틱태그
published: true
sitemap: true
---

## 시멘틱 태그
오늘은 HTML의 시멘틱 태그에 대해 알아보겠습니다.


HTML의 `시멘틱 태그`(semantic tag)는 문서의 구조와 의미를 명확히 하기 위해 사용되는 HTML 태그입니다.<br>
시멘틱 태그는 콘텐츠의 의미를 정의하며, 검색 엔진과 브라우저, 그리고 다른 사용자에게 콘텐츠의 목적을 더 잘 이해할 수 있도록 돕습니다.<br>
시멘틱 태그를 사용하면 접근성 향상, SEO 개선, 코드 유지보수성 향상 등의 이점을 얻을 수 있습니다.<br>

💡 여기서 SEO(Search Engine Optimization, 검색 엔진 최적화)는 웹사이트나 웹페이지를 검색 엔진의 검색 결과에서 더 높은 순위에 노출시키기 위한 다양한 전략과 기법을 의미합니다.<br>
SEO의 궁극적인 목표는 검색 엔진을 통해 웹사이트에 더 많은 트래픽을 유도하고, 이를 통해 비즈니스 목표를 달성하는 것입니다.<br>

### 주요 시멘틱 태그와 그 역할

#### 01. header
- 문서나 섹션의 머리글 부분을 정의합니다.
- 일반적으로 로고, 네비게이션, 제목 등을 포함합니다.

````html
<header>
  <h1>My Website</h1>
  <nav>
    <ul>
      <li><a href="#home">Home</a></li>
      <li><a href="#about">About</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </nav>
</header>
````

#### 02.nav
- 네비게이션 링크를 정의합니다.
- 사이트나 페이지의 주요 링크를 그룹화합니다.

````html
<nav>
  <ul>
    <li><a href="#home">Home</a></li>
    <li><a href="#services">Services</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>
````
#### 03. main
- 문서의 주요 콘텐츠를 정의합니다.
- 문서에서 주요 부분을 감싸는 태그로, 페이지의 유일한 주요 콘텐츠를 포함합니다.

````html
<main>
  <h2>Welcome to My Website</h2>
  <p>This is the main content of the page.</p>
</main>
````

#### 04.section
- 문서의 독립적인 섹션을 정의합니다.
- 주제별로 그룹화된 콘텐츠를 포함합니다.

````html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
````
#### 05. article
- 독립적인 콘텐츠를 정의합니다.
- 블로그 글, 뉴스 기사, 포럼 게시물 등 독립적으로 배포 가능한 콘텐츠를 포함합니다.

````html
<article>
  <h2>Breaking News</h2>
  <p>Today's breaking news is...</p>
</article>
````
#### 06. aside
- 본문과 간접적으로 관련된 콘텐츠를 정의합니다.
- 사이드바, 광고, 관련 링크 등을 포함합니다.

````html
<aside>
  <h3>Related Articles</h3>
  <ul>
    <li><a href="#article1">Article 1</a></li>
    <li><a href="#article2">Article 2</a></li>
  </ul>
</aside>
````
#### 07. footer
- 문서나 섹션의 바닥글 부분을 정의합니다.
- 저작권 정보, 연락처, 사이트 맵 등을 포함합니다.

````html
<footer>
  <p>&copy; 2024 My Website. All rights reserved.</p>
</footer>
````

#### 08. figure 및 figcaption
- 이미지나 다이어그램 등의 자율적인 콘텐츠를 정의하며, 그에 대한 설명을 포함합니다.

````html
<figure>
  <img src="image.jpg" alt="A description of the image">
  <figcaption>Image description</figcaption>
</figure>
````

시멘틱 태그를 올바르게 사용하면 웹 페이지가 더 구조적이고 의미 있게 되어 다양한 사용자와 기계가 콘텐츠를 더 효과적으로 활용할 수 있습니다.
