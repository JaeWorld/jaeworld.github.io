---
layout: post
title: (CSS) :link :visited :hover :active 셀렉터
comments: true
tags:
- CSS
---



### :link :visited :hover :active

---



CSS의 셀렉터 `:link` `:visited` `:hover` `:active` 에 대해 공부해보자.

위 셀렉터들은 주로 `<a>` 태그에 사용된다.

---

* `:link`

  방문하지 않은 링크에 대한 셀렉터

* `:visited` 

  방문한 링크에 대한 셀렉터

* `:hover`

  마우스가 올려져 있는 상태에 대한 셀렉터

* `:active`

  클릭한 상태에 대한 셀렉터

---

예제를 통해 살펴보자.

```html
<!DOCTYPE html>
<html>
<head>
  <style>
    .testLink:link {
      color: green;
    }
    .testLink:visited {
      color: red;
    }
    .testLink:hover {
      background-color: grey;
    }
    .testLink:active {
      background-color: yellow;
    }
  </style>
</head>
<body>
  <a class="testLink" href="www.naver.com">www.naver.com</a>
  <br>
  <a class="testLink" href="www.google.com">www.google.com</a>
</body>
</html>
```



![cssselector](https://user-images.githubusercontent.com/28145780/47614117-ce62a900-dadd-11e8-8c7c-a8ee8e6fdea5.gif)

링크의 색은 초록색이며, 마우스를 올리면(:hover) 배경색이 회색으로 변하고, 클릭시 배경색이 노란색으로 변한다.