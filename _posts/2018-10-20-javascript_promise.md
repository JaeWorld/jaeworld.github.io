---
layout: post
title: (javascript) Promise
comments: true
toc: true
toc_sticky: true
use_math: true

categories:
  - JavaScript
tags:
  - JavaScript
---



### Promise

---



자바스크립트 Promise 에 대해 공부해보자.



##### Promise란

---

Promise는 자바스크립트에서 비동기 작업을 수행하기 위해 사용된다. 



##### Promise 사용하기

---



Promise의 구문은 아래와 같다.

```javascript
new Promise(function(resolve, reject) { ... })
```

Promise 생성자는 `resolve` ,`reject` 두가지 함수를 매개 변수로 가지는 함수를 인자로 받는다. 비동기 작업이 성공적으로 완료되었다면 결과값이 반환되고 `resolve` 함수가 호출된다. 작업이 실패했을때는 `reject` 가 호출되어 오류를 반환한다.

간단한 예제로 살펴보자.

##### resolve

```javascript
function myFunc() {
  return promise = new Promise(function (resolve, reject) {
    resolve('Hello')
  })
}

myFunc()
  .then(function(res) {
  console.log(res)
}) // Hello
```

`myFunc` 함수는 promise 객체를 리턴한다. `resolve` 함수가 호출되었으므로 결과값인 `'Hello'` 이 반환된다. 결과값은 `then` 메소드 내의 `res` 로 전달되어 Hello 가 출력된다.

작업이 성공적일때는, `resolve` 함수가 호출되며, 결과값을 리턴받는다. `then` 메소드를 통해 결과값을 받아 처리할 수 있다.

##### reject

```javascript
function myFunc() {
  return promise = new Promise(function (resolve, reject) {
    reject(new Error('There is an Error'))
  })
}

myFunc()
  .then().catch(function(err) {
  console.log(err)
}) // Error: There is an Error
```

`myFunc` 함수는 promise 객체를 리턴한다. `reject` 함수가 호출되었으므로 `Error` 객체가 반환된다. 반환된 오류 객체는 `catch` 메소드 내의 `err` 로 전달되어 Error 가 출력된다.

작업이 실패했을때는, `reject` 함수가 호출되며, 오류 객체를 리턴받는다. `catch` 메소드를 통해 오류 객체를 받아 오류를 출력한다.
