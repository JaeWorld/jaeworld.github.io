---
layout: post
title: (Javascript) 콜백함수
comments: true
tags:
- Javascript
---

##### 콜백함수 (Callback function)

---

##### 콜백함수란

콜백함수란 call back, 말 그대로 '다시 불려져오는' 함수이다.

코드가 실행되면 여러 객체가 일을 하게된다. 

콜백함수는 이때 모든 객체가 일이 끝날때 까지 기다린 후 한번에 결과를 배출하는 대신

어떤 객체에게 일을 시키고, 그 객체의 일이 끝날때까지 다른 일을 하는 방식을 취한다.

비동기 (Asynchronous) 방식의 함수로 사용된다.



##### 동기(Synchronous), 비동기(Asynchronous)

여기서 동기, 비동기 방식의 차이점에 대해 알아보고 넘어가자.



* 동기(Synchronous)

동기 방식은 동시에 일어난다는 의미. 프로그램이 끝난 후 결과물이 한번에 반납된다.

* 비동기(Asynchronous)

비동기 방식은 동시에 일어나지 않는다는 의미. 한번에 결과물이 반납되지 않고 각각의 작업이 끝나는대로 결과물이 반납된다.



즉, 두 방식의 차이점은 결과물을 가져오는 시점이 다르다는 것이다.



##### 사용 방식

콜백함수는 특정 함수의 동작이 끝남과 동시에 다른 여러가지 함수를 호출해야 할 경우에 사용된다.

매개 변수를 통해 함수를 받고, 그 함수를 통해 결과값을 호출한다.

간단한 예시 코드로 알아보자.



```javascript
multiply = function(a, b, callback) {
    var result = a*b;
    callback(result);
}

multiply(3, 4, function(res){
    console.log(res);
})
```

곱셈연산을 하는 코드. 

multiply함수를 선언후 a, b, callback을 인자로 받아 a와 b의 곱셈값을 result에 넣고 result를 callback함수의 인자로 넣는다.

아래 부분에서 callback함수 인자 자리에 

```javascript
function(res) {
	console.log(res);
}
```

위 함수가 들어가 있으므로 multiply함수에서 전달받은 result값을 출력하게 된다.

그러므로 위 코드는 12를 출력한다.



이번에는 콜백함수 개념에 대해 알아보았다.

콜백개념은 아직까지 많이 헷갈린다. 완전히 이해하려면 시간이 걸릴듯 하다.
