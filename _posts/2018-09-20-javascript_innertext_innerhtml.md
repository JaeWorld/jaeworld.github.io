---
layout: post
title: (Javascript) innerText 와 innerHTML
comments: true
tags:
- Javascript
---



### `innerText` 와 `innerHTML` 의 차이

---



자바스크립트로 HTML을 다룰때 DOM요소내의 내용을 조작하는  `innerText` , `innerHTML`. 두 가지의 차이점이 궁금해졌다. 어떤 차이가 있을까?

예제 코드를 보며 확인해 보자



##### innerText

---

```html
<!DOCTYPE html>
<html>
<head>
  <title>Test</title>
</head>
<body>
  <div id="task">소설 읽기</div>
  // innerText를 사용
  <script>
  	var task = document.getElementById('task').innerText = '<h3>만화 보기</h3>'
  </script>
</body>
</html>
```

* 결과

  > \<h3>만화 보기\</h3>



  `<h3>` 태그를 포함한 문자열이 그대로 출력된다.


##### innerHTML

---

```html
<!DOCTYPE html>
<html>
<head>
  <title>Test</title>
</head>
<body>
  <div id="task">소설 읽기</div>
  // innerText를 사용
  <script>
  	var task = document.getElementById('task').innerText = '<h3>만화 보기</h3>'
  </script>
</body>
</html>
```

* 결과

  > ### 만화 보기



  태그가 적용된 문자열이 출력된다.



---

##### 결론

`innerText`는 문자열 그대로를 리턴하는 반면,

`innerHTML`은 태그를 적용시켜, 즉 문자열을 html로 인식하여 리턴한다.
