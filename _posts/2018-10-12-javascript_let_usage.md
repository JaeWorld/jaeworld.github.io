---
layout: post
title: (Javascript) let 변수가 등장한 이유
comments: true
toc: true
toc_sticky: true
use_math: true

categories:
  - JavaScript
tags:
  - JavaScript
---



### let 변수가 등장한 이유

---



ES6에서 새롭게 추가된 let 변수가 등장한 이유가 궁금해졌다. 

우선 let 변수와 기존 var 변수의 특징을 정리해보자.



---

##### var 변수의 특징

- 함수 밖에서 선언시 전역범위, 함수 내에서 선언시 함수범위를 가진다.

- functional level scope이다.

- 같은 이름의 변수를 선언할 수 있다.

- 변수의 재할당이 가능하다.

- 호이스팅이 자유롭다.


##### let 변수의 특징

* let 변수는 Block level scope이다. 즉, { } 안에서 선언된 let 변수는 그 코드블럭 { } 안에서만 유효하다.
* 같은 이름의 변수를 선언할 수 없다. 
* 변수의 재할당이 자유롭다.
* 호이스팅시 TDZ(Temporal Dead Zone)가 일어난다.

---





##### let 변수가 등장한 이유

---

let 변수가 등장한 이유는 기존 var 변수의 모호한 스코프 범위 때문이다. var 변수는 functional scope을 가지며, 호이스팅이 자유롭다는 점으로 인해 예상치 못한 결과가 많이 나타난다. let 변수를 사용하여 var 의 문제점을 해결할 수 있다.

간단한 코드로 살펴보자.

```javascript
function testVar() {
  var i = 1
  if (true) {
    var i = 2
    console.log(i)  // 2
  }
  console.log(i)  // 2
}

function testLet() {
  let i = 1
  if (true) {
    let i = 2
    console.log(i)  // 2
  }
  console.log(i)  // 1
}
```

`testVar()` 함수에서 변수 `i` 는 var로 선언되어 functional scope를 가지므로 처음 값이었던 1이 if문 내부에서 선언된 `i`로 인해 2로 변경되었다.

반면 `testLet()` 함수의 변수 `i`는 let로 선언되어 Block scope를 가진다. 그렇기에 if문 내부의 `i`의 유효범위는 if문의 블럭이 되므로 기존 `i`의 값에 영향을 주지 않는다.



##### 정리

---

공부한 결과, let 은 다음과 같은 목적으로 사용한다.

* 변수의 scope를 명확하게 하기 위해
* 호이스팅으로 인한 혼란을 줄이기 위해
* 예상치 못한 결과를 피하기 위해

