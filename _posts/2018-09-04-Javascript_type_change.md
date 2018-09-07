---
layout: post
title: (Javascript) 타입 변경
comments: true
tags:
- Javascript
---



##### 자바스크립트에서 타입 변환

---



자바스크립트에서는 변수 선언시 타입을 지정해 주지 않는다.

그러므로 변수에는 어느 형태의 값이든 담길 수 있다.

하지만 때로는 변수의 타입을 특정해야 할 필요가 있다.

문자형을 숫자형으로, 숫자형을 문자형으로 변환하는 방법을 알아보자.



---

##### 변수 선언



자바스크립트에서는 다음과 같이 변수를 선언한다.

```javascript
// 변수 a를 숫자 10으로 선언
var a = 10

// 변수 b를 문자열 10으로 선언
var b = '10'
```

다른 언어에서와는 달리 `var` 형이 숫자, 문자열 모두를 담고 있다.

`int` `String` `double` 같은 형으로 선언하지 않는다.



---

##### 문자형을 숫자형으로 (String to Number)



문자형의 변수를 정수형으로 변환하는 방법은 다음과 같다.

```javascript
// 문자열을 정수형으로 반환
var 변수 = parseInt(문자열)

// 문자열을 실수형으로 반환
var 변수 = parseFloat(문자열)

// 문자열을 정수/실수형으로 반환
var 변수 = Number(문자열)
```



예시코드로 확인해보자.

```javascript
var a = '25'
var b = '3.14'

// a의 정수형
var a_int = parseInt(a)
// b의 실수형
var b_float = parseFloat(b)
// a의 정수형
var a_num = Number(a)
// b의 실수형
var b_num = Number(b)

console.log(a_int)
// 25
console.log(b_float)
// 3.14
console.log(a_num)
// 25
console.log(b_num)
// 3.14
```



---

##### 숫자형을 문자형으로 (Number to String)



숫자형을 문자형으로 변환하는 방법을 다음과 같다.

```javascript
// 숫자형을 문자형으로 변환
var 변수 = String(숫자형)

// 숫자를 문자형으로 변환(숫자의 진법을 변경할 수 있음)
var 변수 = 숫자형.toString(진법)

// 숫자를 문자형으로 변환(소수점자리수 지정가능)
var 변수 = 숫자형.toFixed(소수자리수)

// 숫자와 문자열을 합친 문자열
var 변수 = 숫자 + "문자열"
```



예제 코드로 확인 고고

```javascript
var a = 16
var b = 3.14

// a, b의 문자형
var a_string = String(a)
var b_string = String(b)

// a의 문자형(2진수)
var a_toString = a.toString(2)

// b의 문자형(소수점 첫째자리까지 표현)
var b_toFixed = b.toFixed(1)

// a와 문자열 합침
var concat = a + 'bit'

console.log(a_string)
// "16"
console.log(b_string)
// "3.14"
console.log(a_toString)
// "10000"
console.log(b_toFixed)
// "3.1"
console.log(concat)
// "16bit"
```



---



기본적인 것인데 확실히 알고있지 않아서 따로 확실히 정리해 두었다.
