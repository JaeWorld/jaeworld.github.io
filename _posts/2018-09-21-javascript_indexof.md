---
layout: post
title: (Javascript) indexOf 메소드
comments: true
tags:
- Javascript
---



### indexOf()

---



자바스크립트 메소드 `indexOf()` 에 대해 알아보자.



```javascript
strObj.indexOf(subString[, startIndex])
```



`indexOf()`는 문자열 내에서 특정한 문자열의 index값을 리턴한다. 찾고자 하는 문자열이 존재하지 않는다면 -1을 리턴한다.



##### 인자

---

* strObj 

  필수인자.

* subString

  필수인자. 검색하고자 하는 특정 문자열

* startIndex

  선택인자. 검색을 시작할 index값을 지정 가능. 생략시 처음부터 검색.


##### 예제 코드

---

```javascript
var title = 'javascript'

title.indexOf('s') // 4

title.indexOf('s', 5) // -1 (index 5부터 검색 시작했기때문)

title.indexOf('ript') // 6

title.indexOf('b') // -1 
```



```javascript
var title = '자바스크립트'

title.indexOf('크') // 3

title.indexOf('바') // 1

title.indexOf('립트') // 4

title.indexOf('가') // -1
```

