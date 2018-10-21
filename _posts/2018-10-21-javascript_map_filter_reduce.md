---
layout: post
title: (Javascript) map, filter, reduce 함수
comments: true
tags:
- Javascript
---



### map, filter, reduce 함수

---



자바스크립트에서 배열을 다루는데 사용되는 `map`, `filter`, `reduce` 메소드를 공부해보자. 



##### map 함수

---

`map` 함수는 배열의 모든 요소들을 콜백함수에 넣은 결과값을 모은 새로운 배열을 생성한다.



```javascript
const arr = [1, 3, 5, 6]
const newArr = arr.map(x => x * 2)
// [2, 6, 10, 12]
```





##### filter 함수

---

`filter` 함수는 배열의 요소중 콜백함수의 조건을 만족하는 요소를 모은 새로운 배열을 생성한다.



```javascript
const arr = [1, 2, 3, 4]
const newArr = arr.filter(x => x % 2 === 0)
// [2, 4]

const arr = ['apple', 'orange', 'strawberry']
const newArr = arr.filter(x => x.length < 8)
// ["apple", "orange"]
```





##### reduce 함수

---

`reduce` 함수는 누산기와 배열의 요소들에 대하여 배열을 왼쪽에서 오른쪽으로 순환하며 하나의 값으로 줄인다.

매개변수로 콜백함수를 받는다. 콜백함수는 반환값을 누적하는 누산기(accumulator)와  현재 처리되고 있는 요소를 받아 작업을 수행한다.



```javascript
const arr = [1, 2, 3, 4]
const newArr = arr.reduce((sum, value) => sum + value)
// 10
```

