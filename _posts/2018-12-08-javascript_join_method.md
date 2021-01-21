---
layout: post
title: (Javascript) join() 메소드
comments: true
toc: true
toc_sticky: true
use_math: true

categories:
  - JavaScript
tags:
  - JavaScript
---



### join() 메소드

---



자바스크립트의 `join()` 메소드에 대해 공부해보자.



```javascript
arr.join()
```



`join()` 메소드는 배열의 원소들을 문자열로 변환할때 사용된다. 구분 문자를 사용해 원소들을 구분한다. 직접 예제 코드를 보며 공부해보자.



##### 예제

---



```javascript
var arr = ['korea', 'canada', 'france']

arr.join()
// korea,canada,france
```

`join()` 메소드는 배열의 원소들을 문자열로 변환한다. 구분 문자를 별도로 지정하지 않는다면 `,` 로 구분된다.



```javascript
var arr = ['korea', 'canada', 'france']

arr.join('/')
// korea/canada/france

arr.join(' - ')
// korea - canada - france

arr.join(' ')
// korea canada france
```

구분 문자를 지정하면 배열의 원소들이 해당 문자로 구분된다.

