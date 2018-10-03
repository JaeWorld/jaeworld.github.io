---
layout: post
title: (Javascript) 이벤트 위임
comment: true
tags:
- Javascript
---



### 이벤트 위임(Event delegation)

---



자바스크립트의 이벤트 위임에 대해 알아보자.

이벤트 위임이란 각각의 자식 요소에 이벤트 핸들러를 바인딩 하는 대신 하나의 부모 요소에 이벤트 핸들러를 바인딩 하는 방법이다. 

예제 코드를 보며 자세히 살펴보자.



---

* ##### 이벤트 위임을 사용하지 않은 코드

```html
<!DOCTYPE html>
<html>
<head>
  <title>Test</title>
</head>
<body>
  <ul id="item-list">
    <li id="item1">1</li>
    <li id="item2">2</li>
    <li id="item3">3</li>
  </ul>
  <script>    
    document.getElementById('item1').addEventListener('click', function(){console.log('clicked')})
    document.getElementById('item2').addEventListener('click', function(){console.log('clicked')})
    document.getElementById('item3').addEventListener('click', function(){console.log('clicked')}) 
</script>  
</body>
</html>
```



`ul` 내부에 있는 각각의 `li` 요소에 이벤트 리스너를 등록하였다. 이러한 방식은 요소의 개수가 많아질 경우 작성이 불편해지며, 동적으로 새로운 `li`요소가 추가되는 경우, 새로 추가된 요소에 이벤트 리스너를 등록하지 못한다는 단점이 있다. 이를 해결하기 위해 이벤트 위임을 사용한다.



* ##### 이벤트 위임을 사용한 코드

```html
<!DOCTYPE html>
<html>
<head>
  <title>Test</title>
</head>
<body>
  <ul id="item-list">
    <li id="item1">1</li>
    <li id="item2">2</li>
    <li id="item3">3</li>
  </ul>
  <script>    
    document.getElementById('item-list').addEventListener('click', function(e){console.log('clicked')})
</script>  
</body>
</html>
```

자식요소인 `li`에 이벤트 리스너를 등록하는 대신 그들의 부모요소인 `ul` 에 이벤트 리스너를 등록하였다. 부모요소에 이벤트를 등록하였기 때문에 자식요소들의 개수가 많아져도 간편히 이벤트 리스너를 등록할 수 있다. `ul` 요소 아래에 동적으로 `li` 요소를 추가하더라도 새로 이벤트 리스너를 등록할 필요없이 알아서 등록된다.



##### 장점

---

정리하자면 이벤트 위임을 다음과 같은 장점이 있다.

* 요소의 개수와 상관없이 부모요소에 이벤트를 등록함으로써 편리하게 이벤트를 등록가능하며 이는 곧 속도의 향상으로 이어진다.
* 동적으로 요소를 추가하더라도 별도의 이벤트 등록 없이도 이벤트가 등록된다.



