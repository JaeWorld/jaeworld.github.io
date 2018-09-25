---
layout: post
title: (Javascript) JSON 메소드
comments: true
tags:
- Javascript
---

 

### JSON 메소드

---



추석이지만 꾸준히 업로드해보자아.

이번엔 JSON 관련 메소드를 공부해보자.

자바스크립트에는 JSON을 처리하기 위한 메소드로 `JSON.stringify()` `JSON.parse()` 가 있다. 



##### JSON.stringify()

---

`JSON.stringify()` 메서드는 자바스크립트 객체를 인자로 받아  **JSON 형식의 문자열을 반환**한다. 



```javascript
JSON.stringify({}) 
// '{}'

JSON.stringify('name')
// '"name"'

JSON.stringify([1, 2, 'three'])
// '[1, 2, "three"]'

JSON.stringify({x: 5, y: 8})
// '{"x": 5, "y": 8}
```



##### JSON.parse()

---

`JSON.parse()` 메서드는 `JSON.stringify()` 와는 반대로 JSON 형식의 문자열을 인자로 받아 **자바스크립트 객체로 반환**한다.



```Javascript
JSON.parse('{}')
// {}

JSON.parse('"name"')
// "name"

JSON.parse('[1, 2, "three"]')
// [1, 2, "three"]

JSON.parse('{"x": 5, "y": 8}')
// { x: 5, y: 8 }
```



