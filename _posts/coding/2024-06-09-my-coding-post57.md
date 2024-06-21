---
layout: post
title: React의 특징 - VirtualDOM
date: 2024-06-09 10:00 +0900
description: React의 특징 - VirtualDOM
image: ../assets/img/react03.png
category: React
tags: React
published: true
sitemap: true
---

# REACT

## 🍳 Virtual DOM, 작동원리

이번 시간에는 리액트의 특징 중 하나인 Virtual DOM에 대해 알아보겠습니다. <br>
리액트(React)는 사용자 인터페이스를 효율적으로 구축하기 위해 만들어진 자바스크립트 라이브러리입니다. <br>
리액트의 핵심 기능 중 하나는 Virtual DOM입니다. <br>
이를 이해하기 위해 먼저 DOM과 Virtual DOM의 차이점을 알아보겠습니다.

<br>

## DOM(Document Object Model)

DOM은 HTML 문서를 구조화하여 브라우저가 내용을 렌더링하고 사용자와 상호작용할 수 있도록 합니다. <br>
HTML 문서가 로드되면, 브라우저는 이를 파싱하여 트리 구조의 DOM을 생성합니다. <br>
이 DOM은 웹 페이지의 각 요소를 노드로 표현하며, 자바스크립트를 통해 이 노드들을 조작할 수 있습니다. <br>
그러나, DOM 조작은 느리고 비효율적일 수 있습니다. 특히, 복잡한 애플리케이션에서 많은 요소를 빈번하게 업데이트해야 할 때 성능 문제가 발생할 수 있습니다.

## 💫 Virtual DOM : 리액트의 핵심 개념

Virtual DOM은 실제 DOM의 효율적인 업데이트를 위해 사용됩니다. <br>
Virtual DOM은 가상의 DOM 트리로, 메모리 내에서 실제 DOM의 사본을 유지합니다. <br>
이 가상 트리는 매우 가볍고 빠르게 조작할 수 있습니다. <br>
리액트는 Virtual DOM을 이용해 변경 사항을 관리하고, 실제 DOM에 최소한의 업데이트만 수행합니다.

### Virtual DOM의 작동 원리

##### 1. 초기 렌더링 (Initial Render)

컴포넌트가 처음 렌더링될 때, 리액트는 Virtual DOM을 생성합니다. 이 Virtual DOM은 실제 DOM의 초기 상태를 반영합니다.

##### 2. 상태 변화 (State Changes)

컴포넌트의 상태(state)나 속성(props)이 변경되면, 리액트는 새로운 Virtual DOM을 생성합니다. 이 새로운 Virtual DOM은 변경된 상태를 반영합니다.

##### 3. 다이프 알고리즘(Diffing Algorithm)

리액트는 기존의 Virtual DOM과 새로운 Virtual DOM을 비교(diffing)하여 변경된 부분을 찾습니다. <br>
이 과정은 매우 효율적으로 수행되며, 변경된 부분만을 찾는 데 집중합니다.

##### 4. 조정 (Reconciliation)

리액트는 비교 과정을 통해 변경된 부분을 실제 DOM에 최소한의 업데이트로 반영합니다. <br>
이 과정에서 필요한 경우에만 실제 DOM을 조작하여 성능을 최적화합니다. <br>
예를 들어, 단순한 텍스트 변경이나 속성 업데이트와 같이 필요한 부분만 업데이트합니다.

<br>

## 예시

가령, 사용자 인터페이스에서 버튼을 클릭하여 상태가 변경되면, 리액트는 다음과 같은 과정을 거칩니다.

<br>

- 버튼 클릭으로 상태가 변경됨.
- 리액트는 새로운 Virtual DOM을 생성하여 변경된 상태를 반영.
- 새로운 Virtual DOM과 이전 Virtual DOM을 비교하여 달라진 부분을 식별.
- 변경된 부분만 실제 DOM에 업데이트.

### 장점

- 성능 최적화: 실제 DOM 조작을 최소화하여 성능을 최적화합니다.
- 개발 편의성: 개발자가 직접 DOM을 조작하지 않아도 되므로 코드가 간결하고 유지보수가 용이합니다.
- 일관된 상태 관리: 상태 변화에 따른 UI 업데이트가 자동으로 관리되므로 일관된 사용자 경험을 제공합니다.

<br>

## 결론 ✨

리액트의 Virtual DOM은 실제 DOM의 효율적인 업데이트를 가능하게 하여 성능을 최적화하는 중요한 기술입니다. <br>
Virtual DOM을 사용하면 복잡한 UI를 간단하게 관리하고, 성능 문제를 최소화할 수 있습니다. <br>
이를 통해 리액트는 현대적인 웹 애플리케이션 개발에 적합한 강력한 도구로 자리잡았습니다. <br>
리액트의 DOM과 Virtual DOM의 원리를 이해하면, 리액트를 더욱 효과적으로 활용할 수 있습니다.
