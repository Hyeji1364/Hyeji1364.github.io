---
layout: post
title: 자바스크립트 자료형
date: 2024-04-08 01:56 +0900
description: 
image: ../assets/img/Javascript.jpg
category: Javascript
tags: js javascript 자바스크립트 자료형
published: true
sitemap: true
---

## 자바스크립트



#### 자료형

<hr />

> 설명

자바스크립트에서 사용되는 자료형은 크게 원시 타입(Primitive Type)과 참조 타입(Reference Type)으로 나눌 수 있습니다.
각각의 자료형은 자바스크립트 프로그래밍에서 데이터를 다루는 방식을 결정합니다.
아래에서 각 자료형의 특징과 예시를 살펴보겠습니다.


> 원시 타입 (Primitive Type)

* 숫자형 (Number): 정수 및 부동소수점 숫자를 나타냅니다.
예 : let n = 123; n = 12.345;

* 문자열(String): 텍스트 형태의 데이터를 나타냅니다.
예: let str = "Hello";

* 불린형(Boolean): 참(true)또는 거짓(false)의 논리적 값입니다.
예: let isTrue = false;

* Null: 존재하지 않거나 유효하지 않은 주소를 나타냅니다.
예: let age = null;

* Undefined: 값이 할당되지 않은 상태를 나타냅니다.
예: let x;


> 참조 타입 (Reference Type)

* 객체 (Object): 여러 속성을 하나의 단위로 구성한 데이터 구조입니다.
예: let user = {name: "John" , age : 30};

* 배열(Array): 순서가 있는 데이터 집합입니다.
예: let numbers = [1, 2, 3, 4, 5];

* 함수(Function): 특정 작업을 수행하는 코드의 집합입니다.
예: function sayHello() {alert("Hello");}