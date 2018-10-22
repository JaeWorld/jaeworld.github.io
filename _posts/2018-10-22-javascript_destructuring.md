---
layout: post
title: (Javascript) 디스트럭처링
comments: true
tags:
- Javascript
- ES6
---



### 디스트럭처링

---



디스트럭처링에 대해 공부해보자.



##### 디스트럭처링이란

---

디스트럭처링(Destructing)은 배열이나 오브젝트의 요소들을 한 번에 변수에 할당할 수 있도록하는 기능이다.

예제로 살펴보자.

```javascript
let one, two, three
[one, two, three] = [1, 2, 3]

console.log(one)  // 1
console.log(two)  // 2
console.log(three)  // 3
```

위와 같이 배열 [1, 2, 3]을 분할하여 `one` , `two` , `three` 변수에 할당하였다. 그 결과 `one` 은 1, `two` 는 2, `three` 는 3이란 값을 할당받게 되었다.



##### 배열 디스트럭처링

---

배열을 디스트럭처링하면 오른쪽 배열의 요소를 분할하여 왼쪽 변수에 할당한다.

몇가지 예제로 살펴보자.

```javascript
let one, two, three, four
[one, two, three, four] = [1, 2, 3, 4]

console.log('one:',one, 'two:',two, 'three:',three , 'four:',four)
// one: 1 two: 2 three: 3 four: 4
```



```javascript
let one, two, three, four
[one, two, three, four] = [1, 2, 3]

console.log('one:',one, 'two:',two, 'three:',three , 'four:',four)
// one: 1 two: 2 three: 3 four: undefined
```



```javascript
let one, two, three, four
[one, two, [three, four]] = [1, 2, [3, 4]]

console.log('one:',one, 'two:',two, 'three:',three , 'four:',four)
// one: 1 two: 2 three: 3 four: 4
```



아래처럼 변수 이름을 생략하고 콤마를 작성하여 해당 인덱스를 건너뛰고 다음 변수로 이동할 수 있다.

```javascript
let one, two, three, four
[one, , , four] = [1, 2, 3, 4]

console.log('one:',one, 'four:',four)
// one: 1 four: 4
```





##### 오브젝트 디스트럭처링

---

오브젝트를 디스트럭처링할때는 오른쪽 오브젝트를 분할하여 같은 이름의 키를 가진 왼쪽 변수에 값을 할당한다.

예제로 살펴보자.

```javascript
let {one, two} = {one: 1, two: 2}

console.log('one:',one, 'two:',two)
// one: 1 two: 2
```



사전에 선언된 변수를 사용하고 싶을때는 소괄호 내부에 디스트럭처링 코드를 작성한다.

```javascript
let one, two
({one, two} = {one:1, two:2})

console.log('one:',one, 'two:',two)
// one: 1 two: 2
```

