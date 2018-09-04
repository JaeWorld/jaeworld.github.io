---
layout: post
title: (Javascript) 스코프, 실행컨텍스트
tags:
- Javascript
---

##### 함수 스코프, 실행 컨텍스트

---



##### 스코프(Scope)



스코프(Scope)는 변수가 가지고 있는 참조범위이다. 

변수 선언시, 어떤 위치에서 선언했는지에 따른 스코프가 생성된다.

스코프의 종류는 아래와 같다.



* 전역 스코프 (Global scope) : 코드내 어디서든 변수를 사용할 수 있다. 즉, 전역 변수가 가지는 스코프.
* 지역 스코프  (Local scope) : 코드내 일부분에서만 변수를 사용할 수 있다. 지역 변수가 가지는 스코프.



##### 실행 컨텍스트



실행컨텍스트는 추상적인 개념으로, 코드가 실행되는 부분을 나타낸다.

함수가 실행될때 작동하는 부분이라고 이해하면 된다.

호이스팅, this바인딩에 대한 정보가 담긴다.



##### 코드로 연습

```
var a = 1;
function outer() {
    console.log(a);
    
    function inner() {
        console.log(a);
        var a = 3;
    }
    
    inner();
    
    console.log(a);
}

outer();
console.log(a);
```

위의 코드를 분석해보자.



코드가 실행되면서 어떤 과정을 거치는지 살펴보면



>0. 전역 실행컨텍스트 생성 (Global)
>
>> 1. 변수 a 선언
>> 2. 함수 outer 선언 (Global > outer)
>> 3. 변수 a에 1 할당
>> 4. outer 함수 호출 -> outer 실행컨텍스트 생성
>>
>> > 5. 함수 inner 선언 (Global > outer > inner)
>> > 6. outer scope에서 a 탐색 -> global scope에서 a 탐색 -> 1 출력
>> > 7. inner 함수 호출 -> inner 실행컨텍스트 생성
>> >
>> > > 8. 변수 a 선언
>> > > 9. inner scope 에서 a 탐색 -> undefined 출력
>> > > 10. 10. 변수 a에 3 할당
>> >
>> > 11. inner 실행컨텍스트 종료
>> > 12. outer scope에서 a 탐색 -> global scope에서 a 탐색 -> 1 출력
>>
>> 13. outer 실행컨텍스트 종료
>> 14. global scope에서 a 탐색 -> 1 출력
>
>15. 전역 실행컨텍스트 종료



위 와 같은 과정으로 진행된다.

위 과정에 대한 대략적인 설명은

>코드가 작동하면서, 
>
>함수에 대한 실행컨텍스트가 생성됨에 따라,
>
>함수 스코프를 통해 변수를 찾아 값을 가져와
>
>결과를 출력하는 과정

이라고 할 수 있겠다.



##### 추가

나는 이 부분을 공부하면서 윗 설명의 9번에서 undefined가 출력되는 부분이 이해가 되지 않았었다.

하지만 호이스팅 개념을 통해 이해하게 되었다.

윗 코드의 inner함수는 다음과 같다.

```
function inner() {
    console.log(a);
    var a = 3;
}
```

여기서 inner컨텍스트가 생성된 후, 내부에서 호이스팅에 의한 끌어올림이 이루어진다. 

그 결과 inner 함수는

```
function inner() {
	var a;
    console.log(a);
    a = 3;
}
```

위 같은 상태가 되며, inner 컨텍스트 내부의 console.log 이 실행될때 변수 a는 선언만 되어있을 뿐 초기화가 되지 않았기에 undefined의 값을 가지게 되는 것이다.

console.log이 실행된 이후에야 a는 3의 값을 할당받게 된다.



함수스코프와 실행컨텍스트에 대해 공부해보았다.
