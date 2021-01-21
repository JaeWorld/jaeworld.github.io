---
layout: post
title: (Javascript) 1급 객체
comments: true
toc: true
toc_sticky: true
use_math: true

categories:
  - JavaScript
tags:
  - JavaScript
---



### 1급 객체

---

##### 1급 객체

자바스크립트에서의 1급 객체에 대해 알아보자.

우선 1급 객체는 다음 조건을 만족해야 한다.



>- 변수나 데이터 구조안에 할당할 수 있다.
>- 파라미터로 전달 할 수 있다.
>- 리턴값으로 사용할 수 있다.



즉, 자바스크립트에서 일반 자료형들은 모두 1급 객체이다.



##### 1급 함수

자바스크립트에서는 함수도 1급 객체로 취급된다. 그러므로 함수도 1급 객체의 조건을 만족한다.

쉽게 말해, 자바스크립트에서는 함수를 일반 자료형처럼 사용할 수 있다고 생각하면 된다.



---

##### 예시 코드

```javascript
first = "Jae"
last = "Suh"

var callName = function() {  
    return function() {  // 함수를 리턴값으로 사용하였다.
      console.log(first + last)
    }
}

var call = callName()  // 변수에 함수를 할당하였다.
call() 
// JaeSuh
```

위와 같이 함수는 1급 객체이므로 객체처럼 할당, 반환이 가능하다.
