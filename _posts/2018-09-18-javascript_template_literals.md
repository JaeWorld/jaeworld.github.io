---
layout: post
title: (Javascript) 템플릿 리터럴
comments: true
toc: true
toc_sticky: true
use_math: true

categories:
  - JavaScript
tags:
  - JavaScript
---



### 템플릿 리터럴 (Template literals)

---



템플릿 리터럴은 ES6에서 새로 도입된 문자열 표기법이다.

템플릿 리터럴은 기존의 일반 문자열에서 사용되던 따옴표 (' ' , " ") 대신 백틱 (``)을 사용한다. (esc키 바로 아래에 있다.)



예제코드를 보며 알아보자.

---

```javascript
console.log(`템플릿 리터럴을 사용한 문자열 출력`)
// 템플릿 리터럴을 사용한 문자열 출력
```

줄바꿈이 허용된다. 여러 줄에 걸쳐 작성이 가능하다.

```javascript
console.log(`템플릿 리터럴을
사용한
문자열 출력`)
/*
템플릿 리터럴을
사용한
문자열 출력
*/
```



템플릿 리터럴로 문자열에 표현식을 삽입할 수 있다.

`${ }` 을 이용한다.

```javascript
// ES5 일반 문자열

const name = "Jae"
const age = 21
const job = "Student"

info = 'Name is ' + name + ', Age is ' + age + ', Job is ' + job
console.log(info)
// Name is Jae, Age is 21, Job is Student

// ES6 템플릿 리터럴

const name = "Jae"
const age = 21
const job = "Student"

info = `Name is ${name}, Age is ${age}, Job is ${job}`
console.log(info)
// Name is Jae, Age is 21, Job is Student
```

ES5의 문자열 활용 방식은 문자열과 변수가 `+` 로 난잡하게 조합돼있어 보기 불편하다. 템플릿 리터럴을 사용하여 간편하게 문자열과 변수를 합칠 수 있다.



변수 대입 뿐만 아니라 연산도 가능하다.

```javascript
var a = 10
var b = 20

console.log(`a+b: ${a+b}
a*b: ${a*b}`)

/*
a+b: 30
a*b: 200
*/
```

