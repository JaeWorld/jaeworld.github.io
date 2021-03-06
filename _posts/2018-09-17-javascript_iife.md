---
layout: post
title: (Javascript) 즉시실행함수
comments: true
toc: true
toc_sticky: true
use_math: true

categories:
  - JavaScript
tags:
  - JavaScript
---



### 즉시실행함수 (Immediately-invoked function expression)

---

##### 즉시실행함수

---

자바스크립트의 즉시실행함수에 대해 알아보자.

즉시실행함수는 함수를 정의함과 동시에 실행되는 함수를 말한다. 형태는 아래와 같다.

```javascript
// 두가지 모두 같은 기능 수행
(function() {
    console.log("Hello world")
})()

(function() {
    console.log("Hello world")
}())
```

함수선언 바로 뒤에 괄호 () 를 추가하여 즉시실행함수를 만들 수 있다.

일반적으로 함수는 함수 정의, 변수에 함수 저장 과정을 거쳐 실행되지만, 즉시실행함수는 함수가 선언되자마자 실행된다. 괄호안에 값을 넣어 함수에 인자로 넘겨줄수도 있다.



```javascript
(function() {
  var name = "Jae"
  console.log(name)
}())

// Jae
```

```javascript
(function(score) {
    console.log(score)
})(95)

// 95
```



위 함수는 별도의 과정없이 코드를 실행하자마자 실행된다.



##### 사용 이유

---

그렇다면 즉시실행함수를 사용하는 이유는 무엇일까?

* 초기화에 사용된다.

  즉시실행함수는 선언되자마자 실행되기 때문에 같은 함수를 다시 호출할 수 없다. 그런 특성때문에 초기화 부분에 많이 사용된다.

* 전역 변수 선언을 피하기 위해 사용된다. 

  자바스크립트에서 변수는 기본적으로 전역 유효 범위를 가진다. 하지만 함수 내부에서 정의된 변수들은 함수 내에서만 유효하다. 이 점을 활용해 외부에서 함수 내부의 변수에 접근이 불가능하도록 함으로써 변수의 충돌을 방지할 수 있다. 특히 라이브러리 사용시, 즉시실행함수 내부에 라이브러리 코드를 추가하면 전역컨텍스트에 영향을 주지 않게되어 라이브러리간의 충돌을 피할 수 있다.
