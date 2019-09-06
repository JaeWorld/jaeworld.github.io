---
layout: post
title: (Javascript) static 메소드 및 프로퍼티
comments: true
tags:
- Javascript
---



### prototype/static method

---



##### static

자바스크립트에서 클래스에는 여러가지 프로퍼티가 있는데 그중 prototype 프로퍼티에 할당되지 않는 것들을 static 프로퍼티라고 한다.

static 메소드, 프로퍼티는 1급 객체[^1]인 함수로서 호출되는 값들이다.

prototype 프로퍼티에 할당된 메소드들을 prototype method 라 하고 메소드(methods)라고 부른다.



즉, 클래스는 다음과 같은 요소를 가진다.

- static methods, static properties
- (prototype) methods



그렇다면 클래스와 인스턴스간의 관계를 살펴보자.

클래스에는 static methods 와 prototype methods 의 두가지가 있다.

이 두가지 메소드는 인스턴스가 접근할 수 있는 방법이 다르다.



우선 prototype methods 는 인스턴스와 `__proto__`[^2]로 연결되어있다.

그러므로 인스턴스에서 직접 접근이 가능하다.



반면 static methods는 직접 접근이 불가능하다.

접근하기 위해서는 인스턴스가 아니라 생성자 함수에서 접근해야 한다.



---

##### 예제



```javascript
function Person(name, age) {
    this.name = name
    this.age = age
}

Person.getInformations = function(instance) {
  return {
    name: instance.name,
    age: instance.age
  }
}

Person.prototype.getName = function() {
  return this.name
}
 
Person.prototype.getAge = function() {
  return this.age
}
```

`getInformations` 는 static으로 선언했고,

`getName`,`getAge`는 prototype method로 선언했다.



인스턴스를 생성해 보자.

```javascript
var son = new Person('Son', 26)
```

생성한 인스턴스를 가지고 놀아보자.

```javascript
son.getName()
// "Son"

son.getAge()
// 26

son.getInformation(son)
// "son.getInformations is not a function"
```

`getName()`,`getAge()` 메소드를 이용해 son 인스턴스의 이름, 나이를 출력할 수 있다.

하지만 `getInformation`메소드는 오류를 출력하는 걸 확인할 수 있다. 이는 `getInformation` 메소드가 static으로 선언되어 인스턴스에서 직접 접근이 불가하기 때문이다.

그러므로 다음과 같이 클래스에 직접 접근하여 사용해야 한다.

```javascript
Person.getInformation(son)
/* [object Object] {
  		age: 24,
  		name: "Son"
	}
*/
```



___

[^1]: 1급 객체란? [위키백과](https://ko.wikipedia.org/wiki/%EC%9D%BC%EA%B8%89_%EA%B0%9D%EC%B2%B4)
[^2]: `__proto__`는 부모객체의 prototype 프로퍼티를 가리킨다. [이전 포스팅](https://jaeworld.github.io/Javascript-Flow-7/) 참고
