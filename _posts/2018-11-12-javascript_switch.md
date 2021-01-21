---
layout: post
title: (Javascript) switch문
comments: true
toc: true
toc_sticky: true
use_math: true

categories:
  - JavaScript
tags:
  - JavaScript
---



### switch문

---



자바스크립트의 switch문을 공부해보자.

switch문은 표현식의 값을 확인하여 값이 일치하는 case문 내의 코드를 실행하는 조건문이다.



##### 문법

---

switch문의 문법은 아래와 같다.



```javascript
switch(표현식) {
    case value1:
        // value1일때 실행 코드
       	break
    case value2:
        // value2일떄 실행 코드
        break
    case value3:
        // value3일때 실행 코드
        break
    default:
    	// 위 조건들이 해당되지 않을 경우 실행 코드   
}
```



##### 예제

---

예제를 통해 사용해보자.

```javascript
country = 'Korea'

switch(country) {
  case 'China':
    console.log('Made in China')
    break
  case 'Korea':
    console.log('Made in Korea')
    break
  case 'Japan':
    console.log('Made in Japan')
    break
  case 'USA':
    console.log('Made in USA')
    break
  default:
    console.log('Made in Mars')
}

// Made in Korea
```



표현식 `country` 의 값을 확인한 후 해당 값을 가지는 `case` 내의 코드를 실행한다. 예제에서는 `country` 의 값이 `Korea`  이므로 `'Made in Korea'` 가 출력된다.



