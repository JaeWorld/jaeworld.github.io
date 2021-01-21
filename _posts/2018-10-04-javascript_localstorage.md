---
layout: post
title: (Javascript) localStorage
comments: true
toc: true
toc_sticky: true
use_math: true

categories:
  - JavaScript
tags:
  - JavaScript
---



### localStorage

---



`localStorage` 에 대해 알아보자.

프로그램을 개발할때 유저가 입력한 정보를 저장해야 할때가 있다.  페이지를 새로고침하거나 페이지 이동을 하더라도 입력한 정보를 저장하고싶을때 `localStorage` 를 이용한다.



##### 메소드

---

`localStorage` 의 메소드는 아래와 같다.

* `setItem()`  : localStorage에 key와 value를 추가
* `getItem()` : key를 통해 value를 가져옴
* `removeItem()` : key를 통해 아이템 제거
* `clear()` : localStorage 비우기



예제 코드로 살펴보자.



##### 예제 코드

---

```javascript
let books = []

localStorage.setItem('books', JSON.stringify(books))

const data = JSON.parse(localStorage.getItem('books'))
```

* `localStorage.setItem('book', JSON.stringify(books))` 를 통해 `books` 오브젝트를 localStorage에 추가한다. 주의할 점은 localStorage에 오브젝트를 추가하기 위해서는 오브젝트를 문자열로 변환하여 추가해야 한다는 점이다. `JSON.stringify()` 를 사용하여 오브젝트를 문자열로 변환 후 추가한다.

* `JSON.parse(localStorage.getItem('books'))` 를 통해 localStorage에서 오브젝트를 가져온다. localStorage에서 오브젝트를 가져오기 올때는 `JSON.parse()` 를 사용하여 다룰 수 있는 데이터 형태로 변환하여 가져온다.

