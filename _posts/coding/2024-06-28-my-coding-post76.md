---
layout: post
title:
date: 2024-06-28 10:00 +0900
description: javascript 이벤트 버블링과 이벤트 캡처
image: https://github.com/Hyeji1364/class2024/assets/161557112/d817744a-9d22-4d92-a9c8-aafc9026990b
category: Javascript
tags: Javascript
published: true
sitemap: true
---

# Javascript

## 자바스크립트의 이벤트 버블링과 이벤트 캡처

자바스크립트에서 이벤트는 특정 요소에서 발생한 후, DOM 트리 구조를 따라 전파됩니다. <br>
이 전파 방식에는 두 가지가 있습니다.<br>
`이벤트 버블링(Event Bubbling)`과 `이벤트 캡처(Event Capturing)`입니다. <br>
이번 글에서는 이 두 가지 전파 방식에 대해 설명하고, 각각의 예시와 이벤트 전파를 막는 방법에 대해 알아보겠습니다.

### 🌀 이벤트 버블링(Event Bubbling)

이벤트 버블링은 특정 요소에서 이벤트가 발생했을 때, 해당 이벤트가 DOM 트리 구조에서 최하위 요소부터 최상위 요소로 순차적으로 전파되는 특성입니다. <br>
예를 들어, `div > div > div` 구조에서 최하위 `div`에 이벤트가 발생하면, 해당 이벤트가 최하위 div에서 시작하여 상위 div로 전파됩니다.
<br>

#### 이벤트 버블링 예제

```javascript
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Event Bubbling Example</title>
</head>
<body>
    <div id="outer" style="padding: 20px; border: 1px solid black;">
        Outer Div
        <div id="middle" style="padding: 20px; border: 1px solid red;">
            Middle Div
            <div id="inner" style="padding: 20px; border: 1px solid blue;">
                Inner Div
            </div>
        </div>
    </div>

    <script>
        document.getElementById('outer').addEventListener('click', () => {
            alert('Outer Div Clicked');
        });

        document.getElementById('middle').addEventListener('click', () => {
            alert('Middle Div Clicked');
        });

        document.getElementById('inner').addEventListener('click', () => {
            alert('Inner Div Clicked');
        });
    </script>
</body>
</html>
```

위 예제에서 가장 안쪽의 Inner Div를 클릭하면, Inner Div Clicked 메시지가 먼저 표시되고, 그 다음 Middle Div Clicked, 마지막으로 Outer Div Clicked 메시지가 순차적으로 표시됩니다. <br>
이는 이벤트가 버블링되어 상위 요소로 전파되기 때문입니다.
<br>

### 📸 이벤트 캡처

이벤트 캡처는 이벤트가 DOM 트리 구조에서 최상위 요소부터 최하위 요소로 전파되는 방식입니다. <br>
이를 사용하려면 addEventListener 메서드의 옵션 객체에 capture: true 설정을 추가해야 합니다.
<br>

#### 이벤트 캡처 예제

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Event Capturing Example</title>
  </head>
  <body>
    <div id="outer" style="padding: 20px; border: 1px solid black;">
      Outer Div
      <div id="middle" style="padding: 20px; border: 1px solid red;">
        Middle Div
        <div id="inner" style="padding: 20px; border: 1px solid blue;">
          Inner Div
        </div>
      </div>
    </div>

    <script>
      document.getElementById("outer").addEventListener(
        "click",
        () => {
          alert("Outer Div Clicked");
        },
        { capture: true }
      );

      document.getElementById("middle").addEventListener(
        "click",
        () => {
          alert("Middle Div Clicked");
        },
        { capture: true }
      );

      document.getElementById("inner").addEventListener(
        "click",
        () => {
          alert("Inner Div Clicked");
        },
        { capture: true }
      );
    </script>
  </body>
</html>
```

위 예제에서 Inner Div를 클릭하면, Outer Div Clicked 메시지가 먼저 표시되고, 그 다음 Middle Div Clicked, 마지막으로 Inner Div Clicked 메시지가 순차적으로 표시됩니다. <br>
이는 이벤트가 캡처링되어 하위 요소로 전파되기 때문입니다.
<br>

### 이벤트 전파 막기 : stopPropagation()

이벤트 전파를 막으려면 stopPropagation() 메서드를 사용합니다. <br>
이 메서드는 이벤트가 더 이상 상위 또는 하위 요소로 전파되지 않도록 합니다.

#### 이벤트 전파 막기 예제

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Stop Propagation Example</title>
  </head>
  <body>
    <div id="outer" style="padding: 20px; border: 1px solid black;">
      Outer Div
      <div id="middle" style="padding: 20px; border: 1px solid red;">
        Middle Div
        <div id="inner" style="padding: 20px; border: 1px solid blue;">
          Inner Div
        </div>
      </div>
    </div>

    <script>
      document.getElementById("outer").addEventListener("click", () => {
        alert("Outer Div Clicked");
      });

      document.getElementById("middle").addEventListener("click", () => {
        alert("Middle Div Clicked");
      });

      document.getElementById("inner").addEventListener("click", (event) => {
        alert("Inner Div Clicked");
        event.stopPropagation(); // 이벤트 전파를 막음
      });
    </script>
  </body>
</html>
```

위 예제에서 Inner Div를 클릭하면, Inner Div Clicked 메시지만 표시되고, 상위 요소로 이벤트가 전파되지 않습니다. <br>
이는 event.stopPropagation() 메서드가 이벤트 전파를 막았기 때문입니다.
<br>

## 결론 ✨

이벤트 버블링과 이벤트 캡처는 자바스크립트에서 이벤트가 전파되는 두 가지 방식입니다. <br>
이벤트 버블링은 하위 요소에서 상위 요소로 이벤트가 전파되며, 이벤트 캡처는 상위 요소에서 하위 요소로 전파됩니다. <br>
addEventListener 메서드의 capture 옵션을 사용하여 이벤트 캡처를 활성화할 수 있으며, stopPropagation() 메서드를 사용하여 이벤트 전파를 막을 수 있습니다. <br>
이 두 가지 전파 방식을 이해하고 적절히 활용하면, 보다 효율적이고 제어된 이벤트 처리를 할 수 있습니다.
