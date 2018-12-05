---
layout: post
title: (Javascript) sort() 메소드
comments: true
tags:
- Javascript
---



### sort() 메소드

---



자바스크립트의 `sort()` 메소드를 공부해보자.

```javascript
arr.sort()
```

`sort()` 메소드는 배열을 정렬하여 반환하는 메소드이다. 새로운 배열을 반환하는 것이 아니라 원래 배열을 반환한다는 점에 주의하자. 



##### 사용법

---



기본적으로 `sort()` 메소드는 배열의 요소를 낮은것부터 높은 순으로 정렬한다.

```javascript
const arr = [5, 2, 8, 4]

arr.sort() 
console.log(arr) 
// [2, 4, 5, 8]
```



`sort()` 메소드에 함수식을 인자로 넣어 정렬 순서를 원하는대로 지정할 수 있다.

```javascript
// 오름차순 정렬
const arr = [5, 2, 8, 4]

arr.sort(function(a, b) {
    return a - b
}) 
console.log(arr) 
// [2, 4, 5, 8]
```



```javascript
// 내림차순 정렬
const arr = [5, 2, 8, 4]

arr.sort(function(a, b) {
    return b - a
}) 
console.log(arr) 
// [8, 5, 4, 2]
```



아래와 같이 배열 요소들의 속성값을 기준으로 정렬할 수도 있다.



```javascript
// 길이로 오름차순 정렬 
const arr = ['whiskey', 'beer', 'vodka']

arr.sort(function(a, b) {
  return a.length - b.length
})
console.log(arr)
// ["beer", "vodka", "whiskey"]
```



```javascript
// 길이로 내림차순 정렬
const arr = ['whiskey', 'beer', 'vodka']

arr.sort(function(a, b) {
  return b.length - a.length
})
console.log(arr)
// ["whiskey", "vodka", "beer"]
```





