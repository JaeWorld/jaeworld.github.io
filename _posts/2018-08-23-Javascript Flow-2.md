---
layout: post
title: (Javascript) 호이스팅
comments: true
tags:
- Javascript
---
### 호이스팅(Hoisting)

자바스크립트에서 호이스팅이란 무엇일까? Hoisting은 들어올려 나르기라는 뜻을 가지고 있다.

호이스팅은 자바스크립트에서 변수와 함수를 끌어 올리는 것이다.



```
console.log(a());
console.log(b());
console.log(c());

function a() {
    return 'a';
}
var b = function bb() {
    return 'bb';
}
var c = function() {
    return 'c';
}
```

위 코드는 자바스크립트가 아닌 다른 언어의 방식대로라면 선언하지도 않은 변수/함수를 호출하고 있기에 오류가 발생할 것이다.

하지만 자바스크립트에서는 호이스팅이 있기 때문에 뒤에 선언, 초기화한 변수를 끌어올려 가져온다.

그렇기 때문에 위 코드는 자바스크립트에서 아래와 같은 흐름으로 작동한다.



```
function a() {
    return 'a';
}
var b;
var c;
console.log(a());
console.log(b());
console.log(c());

b = function bb() {
    return 'bb';
}
c = function() {
    return 'c';
}
```



즉 위처럼 함수,변수가 끌어올려 진다.

이때 함수선언식은 함수 통째로 올라가 있는 반면,

함수표현식은 선언만 올라가 있고 이후에 초기화가 이루어 지는 것을 확인할 수 있다.
