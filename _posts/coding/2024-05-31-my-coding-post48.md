---
layout: post
title: 자바스크립트 객체지향
date: 2024-05-31 10:00 +0900
description: 자바스크립트 객체지향
image: ../assets/img/javascript13.png
category: Javascript
tags: Javascript 객체 객체지향 
published: true
sitemap: true
---

# Javascript

## 객체 지향

오늘은 자바스크립트의 속성인 객체 지향에 대해 알아보겠습니다.<br>
자바스크립트는 객체 지향 프로그래밍을 지원하는 언어입니다.<br>
객체지향을 쉽게 말하면, <span style="color:red">필요한 데이터를 추상화시켜 상태와 행위를 가진 객체</span>입니다.
객체와 클래스 개념을 활용하여 프로그램을 구조화할 수 있습니다.<br>


### 1. 객체(Object)
객체는 속성과 메서드를 가지는 독립적인 단위입니다.<br>
객체는 자바스크립트의 거의 모든 것에 해당하며, 객체를 사용하여 데이터를 구조화하고 기능을 구현할 수 있습니다.

````javascript
let person = {
  name: "John",
  age: 30,
  greet: function() {
    console.log("Hello, my name is " + this.name);
  }
};

person.greet(); // Hello, my name is John
````

### 2. 클래스(Class)
ES6부터 자바스크립트는 `class` 키워드를 도입하여 클래스 기반 객체지향 프로그래밍을 더 쉽게 구현할 수 있게 되었습니다.<br>
클래스는 객체를 생성하기 위한 템플릿으로, 속성과 메서드를 정의합니다.

````javascript
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  greet() {
    console.log("Hello, my name is " + this.name);
  }
}

let john = new Person("John", 30);
john.greet(); // Hello, my name is John
````

### 3. 상속
상속은 한 클래스가 다른 클래스의 속성과 메서드를 상속받아 재사용할 수 있는 기능입니다.<br>
자바스크립트에서는 `extends` 키워드를 사용하여 상속을 구현합니다.

````javascript
class Employee extends Person {
  constructor(name, age, jobTitle) {
    super(name, age);
    this.jobTitle = jobTitle;
  }

  work() {
    console.log(this.name + " is working as a " + this.jobTitle);
  }
}

let jane = new Employee("Jane", 28, "Software Engineer");
jane.greet(); // Hello, my name is Jane
jane.work();  // Jane is working as a Software Engineer
````
