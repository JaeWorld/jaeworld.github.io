---
layout: post
title: (Javascript) 클로저
comments: true
tags:
- Javascript
---



##### 클로저 (Closure)

---



클로저란 함수와 그 함수가 선언될 당시의 환경정보를 저장하는 객체이다. 

클로저를 통해 **함수 최초 선언시의 정보를 유지**할 수 있다.

다음과 같은 이점이 있다.

- 접근 권한 제어
- 지역변수 보호
- 데이터 보존 및 활용



```javascript
// ex1
function a() {
    var x = 1
    function b() {
        return x
    }
    b()
}
a()
console.log(x)
```

위 코드에서 a 스코프 내부에 있는 변수 x는 함수a, 함수b에서는 접근이 가능하지만 함수a 외부에서는 접근이 불가능하다.

그 점을 보완하기 위해 다음과 같은 코드를 작성한다.

```javascript
//ex2
function a() {
    var x = 1
    return function b() {
        return x
    }
}
var c = a()
c()
```

함수a 에서 b함수를 리턴하게 하였고, a를 변수c에 담았다.

이제 변수c를 이용하여 외부에서 x값을 출력할 수 있게 된다.

ex2코드의 변수c는 함수a의 환경정보를 가지고 있으며 a스코프 내에 있는 변수x에 접근이 가능하다.





##### 클로저로 Private member 만들기

---

자바에서는 private 변수를 선언해 외부의 접근으로부터 보호할 수 있다.

자바스크립트에서도 클로저를 이용해 비슷하게 구현해보자.



```javascript
//ex3
var car = {
	fuel: 10,
    power: 2,
    total: 0,
    run: function(km) {
    	var wasteFuel = km / this.power
    	if(this.fuel < wasteFuel) {
    	document.write('이동 불가')
        return
    	}
    	this.fuel -= wasteFuel
    	this.total += km
    }
}
```

위 코드는 자동차의 연료량, 연비를 받아 일정거리를 이동했을때 더 갈 수 있는지, 이동 불가인지 판단하는 코드이다.

이 코드는 car객체가 가지는 fuel, power 요소들이 외부 접근에 노출되어 있다는 문제가 있다. 외부에서 연료량과 연비 조작이 가능하다면 문제가 있을 것이다.

아래와 같이 코드를 개선하면 그 문제를 해결 할 수 있다.

```javascript
//ex4
var createCar = function(f, p) {
    var fuel = f
    var power = p
    var total = 0
    return {
        run: function(km) {
            var wasteFuel = km / power
            if(fuel < wastefuel) {
                console.log('이동 불가')
                return
            }
            fuel -= wasteFuel
            total += km
        }
    }
}
var car = createCar(10, 2)
```

fuel, power, total변수를 내부로 감추고, run이란 메소드만을 외부로 노출했다.

클로저를 이용해 createCar을 통한 car객체를 생성하도록하여 fuel, power, total의 값이 외부에 의해 침범당하지 않도록 개선했다.





즉, 클로저를 이용해 private member만들기는 아래와 같이 이루어 진다.

>1. 함수에서 지역변수 및 내부함수등을 생성한다.
>
>2. 외부에 노출시키고자 하는 멤버들로 구성된 객체를 리턴한다.

-> 리턴한 객체의 멤버들은 public, 리턴한 객체에 포함되지 않은 멤버들은 private하다.
