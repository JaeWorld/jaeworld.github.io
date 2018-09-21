---
layout: post
title: (Javascript) splice 메소드
comments: true
tags:
- Javascript
---



### splice()

---



자바스크립트 메소드 `splice()` 에 대해 알아보자.

```javascript
array.splice(start)
array.splice(start, deleteCount)
array.splice(start, deleteCount, item1, item2)
```

`splice()` 는 배열에 있는 요소를 삭제하고, 새 요소를 추가할 수 있다.



##### 인자

---

* start

  요소를 제거할 위치이다.

* deleteCount

  배열에서 제거할 요소의 개수이다. 0으로 지정시 요소를 제거하지 않는다.

* item

  배열에 추가할 요소이다. 제거된 요소 대신 배열에 삽입된다. 지정하지 않을시 요소를 추가하지 않는다.





##### 예제 코드

---

```javascript
var arr = [1, 2, 3, 4, 5]

arr.splice(2, 1)
// [1, 2, 4, 5]
// index 2 요소 1개 제거

arr.splice(3, 1, 6)
// [1, 2, 3, 6, 5]
// indx 3 요소 1개 제거, 제거된 요소 대신 6 삽입
```



```javascript
var arr = ['2', '5', '3', '10', '7']

arr.splice(1, 2)
// ['2', '10', '7']
// index 1 부터 요소 2개 제거

arr.splice(1, 2, '8')
// ['2', '8', '10', '7']
// index 1 부터 요소 2개 제거, 삭제된 요소 대신 '8' 삽입
```

