---
layout: post
title: (CSS) display 속성
comments: true
tags:
- CSS
---



### display 속성

---



CSS의 display 속성에 대해 공부해보자.



`display` 속성은 요소들을 표시하는 방법을 정의하는 속성이다. 다음과 같은 4개의 속성이 사용된다.

* `none`
* `block`
* `inline`
* `inline-block`

각각의 속성값을 살펴보자.



##### none

---

요소를 보이지 않게 한다. 



##### block

---

기본적으로 가로 길이가 100%이다. `block` 을 연속으로 배치하면 줄바꿈이 된다. `width` `height` 속성을 지정 할 수 있다. `<div>` `<p>` 등의 태그가 해당된다.



##### inline

---

줄바꿈이 되지 않는다. `width` `height` 속성을 지정할 수 없다.

`<span>` `<a>` 등의 태그가 해당된다.



##### inline-block

---

`block` 과 `inline` 의 속성을 결합한 형태이다. 줄바꿈이 되지 않으며 `width` `height` 속성을 지정 가능하다.



##### 예제

---

간단한 예제를 통해 살펴보자.

```html
<!DOCTYPE html>
<html>
<head>
</head>
<body>
  <div class="container">
    <div class="none">none</div>
    <div class="block">block</div>
    <div class="inline">inline</div>
    <div class="inline-block">inline-block</div>
  <div>
</body>
</html>
```



```css
.container > div {
  border: 2px solid black;
  margin: 3px
}

.none {
  display: none;
}

.block {
  display: block;
  height: 50px;
  width: 100px;
}

.inline {
  display: inline;
  height: 50px;
  width: 100px;
}

.inline-block {
  display: inline-block;
  height: 50px;
  width: 100px;
}
```

위 예제 코드는 아래와 같은 결과를 얻는다.

![display](https://user-images.githubusercontent.com/28145780/47604827-b5082100-da39-11e8-88ca-e7852efe8e50.png)

