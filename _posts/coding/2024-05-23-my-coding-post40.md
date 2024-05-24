---
layout: post
title: 자바스크립트 프로토타입
date: 2024-05-23 10:00 +0900
description: 프로토타입
image: ../assets/img/javascript06.png
category: Javascript
tags: javascript 프로토타입
published: true
sitemap: true
---

# JAVASCRIPT

## 프로토타입

자바스크립트의 프로토타입은 객체지향 프로그래밍의 중요한 개념 중 하나입니다.<br>
프로토타입은 객체의 상속을 지원하며, 객체가 다른 객체로부터 속성과 메서드를 상속받을 수 있게 합니다. <br>
자바스크립트는 클래스 기반 상속이 아닌 프로토타입 기반 상속을 사용합니다.

<hr />

## 기본 개념
📍 프로토타입 객체 (Prototype Object)
- 모든 자바스크립트 객체는 다른 객체로부터 상속을 받습니다. 기본적으로 객체는 Object의 프로토타입 객체를 상속받습니다.

📍 프로토타입 체인 (Prototype Chain):
- 객체가 속성이나 메서드를 찾을 때, 해당 객체에 없으면 프로토타입 체인을 따라 상위 프로토타입 객체에서 찾습니다.<br>
최종적으로 Object.prototype까지 검색합니다.

### 프로토타입의 활용

1. 객체 생성 및 프로토타입 설정

````javascript
function Person(name, age) {
  this.name = name;
  this.age = age;
}

Person.prototype.greet = function() {
  console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
};

let john = new Person('John', 30);
john.greet(); // "Hello, my name is John and I am 30 years old."
````
여기서 Person.prototype은 모든 Person 객체가 공유하는 속성과 메서드를 정의하는 객체입니다.<br>
greet 메서드는 john 객체에서 직접 정의된 것이 아니라, Person.prototype에서 상속된 것입니다.
<br>

2. 프로토타입 체인

````javascript
console.log(john.__proto__ === Person.prototype); // true
console.log(Person.prototype.__proto__ === Object.prototype); // true
console.log(Object.prototype.__proto__ === null); // true
````
john 객체는 Person.prototype을 상속받고, Person.prototype은 Object.prototype을 상속받습니다. 최종적으로 Object.prototype의 프로토타입은 null입니다.

3. 프로토타입 상속

````javascript
function Employee(name, age, jobTitle) {
  Person.call(this, name, age);
  this.jobTitle = jobTitle;
}

Employee.prototype = Object.create(Person.prototype);
Employee.prototype.constructor = Employee;

Employee.prototype.work = function() {
  console.log(`${this.name} is working as a ${this.jobTitle}.`);
};

let alice = new Employee('Alice', 28, 'Developer');
alice.greet(); // "Hello, my name is Alice and I am 28 years old."
alice.work(); // "Alice is working as a Developer."
````
여기서 Employee는 Person을 상속받으며, Employee.prototype은 Person.prototype을 기반으로 합니다.<br> Object.create를 사용하여 Employee.prototype을 설정하고, constructor 속성을 올바르게 설정합니다.<br>


### ES6 클래스와 프로토타입
ES6에서는 클래스 문법이 도입되어, 프로토타입 기반 상속을 더 쉽게 사용할 수 있습니다. 그러나 내부적으로는 여전히 프로토타입을 사용합니다.
````javascript
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  greet() {
    console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
  }
}

class Employee extends Person {
  constructor(name, age, jobTitle) {
    super(name, age);
    this.jobTitle = jobTitle;
  }

  work() {
    console.log(`${this.name} is working as a ${this.jobTitle}.`);
  }
}

let bob = new Employee('Bob', 25, 'Designer');
bob.greet(); // "Hello, my name is Bob and I am 25 years old."
bob.work(); // "Bob is working as a Designer."
````
### ✅ 정리
- 프로토타입: 객체가 다른 객체로부터 속성과 메서드를 상속받을 수 있게 하는 메커니즘.
- 프로토타입 체인: 객체가 속성을 검색할 때 프로토타입을 따라 상위 객체를 탐색하는 과정.
- ES6 클래스: 프로토타입 기반 상속을 더 쉽게 사용할 수 있는 문법, 그러나 내부적으로는 프로토타입을 사용.

자바스크립트의 프로토타입 개념을 이해하면 객체지향 프로그래밍과 상속을 더 효과적으로 활용할 수 있습니다.







