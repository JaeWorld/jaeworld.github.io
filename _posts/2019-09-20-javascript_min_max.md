```
layout: post
title: (Javascript) 배열에서 가장 큰 수, 가장 작은 수 찾기
tags: 
- Javascript
```

### 배열에서 가장 큰 수,가장 작은 수 찾기

---

자바스크립트에서 배열 내의 가장 큰 수, 작은 수를 찾는 방법을 공부해보자.

### Math 객체

---

자바스크립트에 내장된 Math 객체를 사용할 수 있다.

Math 객체는 가장 큰 수, 작은 수를 찾는 max, min 메소드를 가진다. 숫자 배열을 인자로 넘기기 위해 apply 메소드를 사용한다.

```javascript
// Max 찾기
Math.max.apply(null, arr)

// Min 찾기
Math.min.apply(null, arr)
```

### reduce 메소드

---

```javascript
// Max 찾기
var max = arr.reduce((prev, curr) => {
    return prev > curr ? prev : curr
})

// Min 찾기
var min = arr.reduce((prev, curr) => {
    return prev > curr ? curr : prev
})
```

### For 문

---

```javascript
// Max 찾기
var max = 0
for(var i=0; i<arr.length; i++) {
    if(arr[i] > max) {
      max =arr[i]
    }
}

// Min 찾기
var min = 0
for(var i=0; i<arr.length; i++) {
    if(arr[i] < min) {
        min = arr[i]
    }
}
```