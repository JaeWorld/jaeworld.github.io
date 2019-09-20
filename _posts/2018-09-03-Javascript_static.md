---
layout: post
title: (Javascript) static 메소드
comments: true
tags:
- Javascript
---



# static method

---

### static method

자바스크립트의 클래스에서 prototype에 할당되지 않고 클래스 자체에 할당된 함수를 static 메소드라고 한다.

클래스 자체에 할당되었기 때문에 클래스의 인스턴스를 통해서는 호출될 수 없으며 클래스를 통해 호출해야 한다.

클래스가 가지고 있지만 클래스의 인스턴스에 바인딩되지 않은 기능을 구현하고자 할때 사용된다.


---

### 예제


```javascript
function Person(name, age) {
    this.name = name
    this.age = age
}

Person.getInformation = function(instance) {
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

`getInformation` 는 static 메소드

`getName`,`getAge`는 prototype 메소드로 선언했다.



인스턴스를 생성해 보자.

```javascript
var son = new Person('Son', 26)
```

생성한 인스턴스를 가지고 놀아보자.

```javascript
son.getInformation(son)
// "son.getInformations is not a function"

son.getName()
// "Son"

son.getAge()
// 26
```

`getName` , `getAge` 메소드를 이용해 son 인스턴스의 이름, 나이를 출력할 수 있다.

하지만 `getInformation` 메소드는 오류를 출력하는데 이는 `getInformation` 가 static 메소드이므로 인스턴스에서 접근이 불가하기 때문이다.

그러므로 다음과 같이 클래스에 직접 접근하여 사용해야 한다.

```javascript
Person.getInformation(son)
/* [object Object] {
  		age: 24,
  		name: "Son"
	}
*/
```



