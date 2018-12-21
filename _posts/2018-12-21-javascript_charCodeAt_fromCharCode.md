---
layout: post
title: (Javascript) 유니코드, 문자열 변환
comments: true
tags: 
- Javascript
---



### 유니코드, 문자열 변환하기

---



자바스크립트에서 유니코드를 문자열로, 문자열을 UTF-16 코드로 변환하는 방법을 공부해보자.



> *참고: 코드 표*



> ![image](https://user-images.githubusercontent.com/28145780/50318998-3ba42080-0508-11e9-902d-b6f6192eff54.png)



##### 문자열을 유니코드로 - charCodeAt()

---

특정 문자의 UTF-16 코드를 반환하는 `charCodeAt()` 메소드를 사용한다. 

```javascript
str.charCodeAt(index)
```

문자열내에 주어진 `index` 를 가진 문자의 유니코드를 반환한다.



```javascript
var str = "abAB"

str.charCodeAt(0) // 97
str.charCodeAt(1) // 98
str.charCodeAt(2) // 65
str.charCodeAt(3) // 66
```



##### 유니코드를 문자열로 - fromCharCode()

---

`fromCharCode()` 메소드를 사용한다.

```javascript
String.fromCharCode(num)
```

특정 UTF-16 코드(`num`)를 받아 코드가 나타내는 문자를 반환한다.

 

```javascript
String.fromCharCode(53) // "5"
String.fromCharCode(65) // "A"
String.fromCharCode(100, 111, 103) // "dog"
```

