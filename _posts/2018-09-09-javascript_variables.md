---
layout: post
title: (Javascript) var, let, const
comments: true
tags:
- Javascript
- ES6
---



### var 변수

---

기존의 var 변수는 전역변수를 선언할때, 변수의 유효범위가 어디인지, 호이스팅이 일어나는지에 따라 부수 효과가 일어나기 쉽다는 단점이 존재한다. 

var변수의 이러한 단점을 보완하고자 ES6에서 새로이 let, const 개념을 도입했다.

##### 

### let 변수

---

let 변수는 var변수의 스코프 범위, 호이스팅 문제를 해결하기 위해 도입되었다. 다음과 같은 특징을 가진다.

* 함수 안에 작성한 let변수는 함수가 스코프이다.
* 함수 내에 if(a == b) {let sports = "축구"} 형태로 코드를 작성했을 때, sport변수의 스코프는 함수가 아닌 if문의 블록 {} 이다.
* 블록 {} 밖에 같은 이름의 변수가 있어도 스코프가 다르므로 각각의 변수에 다른 값을 할당할 수 있다.
* 블록 내의 블록이 작성되면 각각의 블록이 스코프이다.
* 같은 스코프에서 같은 이름의 let변수를 선언할 수 없다.
* 호이스팅이 되지 않는다.



##### 사용 방법

```javascript
// ex1 선언만 이루어짐
let grade

// ex2 하나의 변수 선언, 초기화
let name = "Jae"

// ex3 여러개의 변수 선언, 초기화
let score1 = 20, score2 = 30, score3 = 15
```

위 예제와 같이 선언할 수 있다.



다음과 같은 선언은 불가하다.

```javascript
let name = "Jae"

let name = "Son"

// 같은 스코프에서 같은 이름의 let변수 선언 불가
```

```javascript
let month = 8, let day = 6

// 콤마로 구분해 여러 변수 선언시 변수마다 let 사용 불가. 
// 아래와 같이 선언해야 함

let month = 8, day = 6
```

```javascript
let grade = 5, var room = 3

// 콤마로 구분해 선언시 let변수와 var변수 동시에 선언 불가
```



##### 예시코드

* 블록 { } 스코프

```javascript
let name = "Son"  // 이 변수의 스코프는 전역
if (name) {
  let name = "Lee" // 이 변수의 스코프는 블록
  console.log("블록: ", name)
}
console.log("전역: ", name)

/*
블록: Lee
전역: Son
*/
```



* 힘수 스코프

```javascript
let name = "Son"  // 이 변수의 스코프는 전역
function get() {
  let name = "Lee"  // 이 변수의 스코프는 함수
  console.log("함수 :", name)
}
get()
console.log("전역: ", name)

/*
함수: Lee
전역: Son
*/
```



### const 변수

---

const 변수는 값을 변경할 수 없다. 



##### 사용 방법

```javascript
const score1 = 10, score2 = 20, score3 = 15
```



##### 예시코드

```javascript
const name = "Son"

try {
  name = "Lee"
} catch (e) {
  console.log("const값 변경불가")
}

// const값 변경불가
```

