---
layout: post
title: javascript 얕은복사와 깊은 복사
date: 2024-06-27 10:00 +0900
description: javascript 얕은복사와 깊은 복사
image: https://github.com/Hyeji1364/class2024/assets/161557112/0b79ea7d-bee7-4e53-9472-010f2aa067cf
category: Javascript
tags: Javascript
published: true
sitemap: true
---

# Javascript

## 자바스크립트의 얕은 복사와 깊은 복사

자바스크립트에서 객체를 복사하는 방법에는 크게 두 가지가 있습니다.<br>
얕은 복사(Shallow Copy)와 깊은 복사(Deep Copy)입니다. <br>
이 두 가지 방법은 객체를 복사할 때 내부 객체의 참조 여부에 따라 다릅니다. <br>
이번 글에서는 얕은 복사와 깊은 복사의 차이점을 알아보고, 각각의 복사 방법을 자세히 설명하겠습니다.
<br>

### 얕은 복사(Shallow Copy)

얕은 복사는 객체를 복사할 때 최상위 레벨의 속성들만 복사하고, 객체 안에 있는 객체의 경우 원본 객체를 참조하는 복사 방법입니다. <br>
따라서, 복사된 객체 내부의 객체를 수정하면 원본 객체에도 영향을 미칩니다.

<br>

#### 얕은 복사 방법

1.  Object.assign(): Object.assign() 메서드는 얕은 복사를 수행합니다.
2.  스프레드 연산자(...): 스프레드 연산자를 사용하여 객체를 얕은 복사할 수 있습니다.
    <br>

#### 얕은 복사 예제

```javascript
// 원본 객체
const original = {
  name: "John",
  address: {
    city: "New York",
  },
};

// Object.assign()을 사용한 얕은 복사
const shallowCopy1 = Object.assign({}, original);

// 스프레드 연산자를 사용한 얕은 복사
const shallowCopy2 = { ...original };

// 내부 객체를 수정
shallowCopy1.address.city = "Los Angeles";

console.log(original.address.city); // 'Los Angeles' (원본 객체도 변경됨)
console.log(shallowCopy2.address.city); // 'Los Angeles' (얕은 복사된 객체도 동일하게 변경됨)
```

위 예제에서 `shallowCopy1`과 `shallowCopy2`는 모두 얕은 복사를 수행했기 때문에, 내부 객체 `address`는 원본 객체와 동일한 참조를 가집니다. 따라서, `address.city`를 수정하면 원본 객체에도 영향을 미칩니다.

<br>

## 깊은 복사 (Deep Copy)

깊은 복사는 객체를 복사할 때 모든 레벨의 속성을 재귀적으로 복사하여 원본 객체와의 참조를 완전히 끊는 방법입니다. <br>
깊은 복사된 객체는 원본 객체와 독립적으로 존재하며, 내부 객체를 수정하더라도 원본 객체에는 영향을 미치지 않습니다.
<br>

### 깊은 복사 방법

1.  JSON.parse()와 JSON.stringify()
    가장 간단한 방법 중 하나로, 객체를 JSON 문자열로 변환한 후 다시 객체로 변환하여 깊은 복사를 수행합니다. 하지만 이 방법은 함수, `undefined`, `Symbol` 등을 복사할 수 없습니다.

2.  재귀적 복사
    객체의 모든 속성을 재귀적으로 순회하여 복사하는 방법입니다.

3.  라이브러리 사용
    Lodash와 같은 라이브러리의 `_.cloneDeep()` 메서드를 사용할 수 있습니다.

### 깊은 복사 예제

```javascript
// 원본 객체
const original = {
  name: "John",
  address: {
    city: "New York",
  },
};

// JSON.parse()와 JSON.stringify()를 사용한 깊은 복사
const deepCopy1 = JSON.parse(JSON.stringify(original));

// Lodash 라이브러리를 사용한 깊은 복사 (Lodash를 설치해야 함)
// const _ = require('lodash');
// const deepCopy2 = _.cloneDeep(original);

// 내부 객체를 수정
deepCopy1.address.city = "San Francisco";

console.log(original.address.city); // 'New York' (원본 객체는 변경되지 않음)
console.log(deepCopy1.address.city); // 'San Francisco' (깊은 복사된 객체만 변경됨)
```

위 예제에서 deepCopy1은 깊은 복사를 수행했기 때문에, 내부 객체 address는 원본 객체와 독립적으로 존재합니다.<br>
따라서, address.city를 수정해도 원본 객체에는 영향을 미치지 않습니다.

## 결론 ✨

자바스크립트에서 객체를 복사할 때는 얕은 복사와 깊은 복사의 차이를 이해하는 것이 중요합니다. <br>
얕은 복사는 최상위 레벨의 속성만 복사하며, 내부 객체는 원본 객체를 참조합니다. 반면, 깊은 복사는 모든 레벨의 속성을 재귀적으로 복사하여 원본 객체와의 참조를 완전히 끊습니다. <br>
복사 방법을 선택할 때는 객체의 구조와 복사 후 수정될 가능성을 고려해야 합니다. <br>
이 두 가지 방법을 적절히 활용하면, 보다 효율적이고 안전한 코드를 작성할 수 있습니다.
