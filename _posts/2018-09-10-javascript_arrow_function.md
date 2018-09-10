---

layout: post
title: (Javascript) arrow 함수
comments: true
tags:
- Javascript
- ES6
---



### arrow 함수

---

arrow 함수는 ES6 에서 새로 도입된 개념이다.

화살표(=>)를 통해 함수를 선언한다. function 키워드를 이용하는 것 보다 간단하게 생성할 수  있다는 장점이 있다. 



##### 사용 방법

구문은 다음과 같다.

```javascript
// 인자를 받지 않는 함수
() => { code... }

// 인자를 받는 함수
(param) => { code... }

// 인자를 여러개 받는 함수
(param1, param2, ...) => { code... }
```



##### 예제 코드

이전 ES5의 function 키워드를 이용한 함수 선언 방식과 ES6의 화살표 함수를 비교해보자.

```javascript
// 기존 function키워드를 통한 선언

var info = function(name) {
    return name
}

// 화살표 (=>) 를 통한 선언

var info = (name) => {
    return name
}
```



```javascript
// 기존 function키워드를 통한 선언

var add = function(a, b) {
    return a+b
}

// 화살표 (=>) 를 통한 선언

var add = (a, b) => {
    return a+b
}
```



