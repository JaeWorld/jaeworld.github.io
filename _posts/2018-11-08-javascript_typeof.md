---
layout: post
title: (Javascript) typeof 연산자
comments: true
tags:
- Javascript
---



### typeof 연산자

---



자바스크립트의 `typeof` 에 대해 공부해보자.



##### typeof 연산자란

---

`typeof` 는 해당 값의 타입을 가리키는 문자열을 반환한다.

특정값이 타입이 무엇인지 알고 싶을때 사용한다. 예제를 통해 사용해보자.



##### 예제

---

```javascript
var num = 25
var str = 'Hi there'
var bool = false
var arr = [1, 2, 3]
var undef = undefined
var func = function() {}

console.log(typeof num) // number
console.log(typeof str) // string
console.log(typeof bool) // boolean
console.log(typeof arr) // object
console.log(typeof undef) // undefined
console.log(typeof func) // function
```

