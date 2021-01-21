---
layout: post
title: (Javascript) class 상속
comments: true
toc: true
toc_sticky: true
use_math: true

categories:
  - JavaScript
tags:
  - JavaScript
---



##### class 상속

---



이제는 앞서 배운 개념들을 토대로 클래스 상속을 구현해 보자.

전에 공부했던 **프로토타입 체이닝** 을 이용한다.



다음과 같은 구조를 구현할 것이다.

```
// 구조 설명

// Person 객체, getName() getAge() 메소드를 가짐
Person 
	prototype methods
		- getName()
		- getAge()
		
// Employee 객체, Person을 상속받음, getName() getAge() getPosition() 메소드를 가짐
Employee
	prototype methods
		- getName()
		- getAge()
		- getPosition()
```



Person과 Employee를 구현해보자.

```javascript
// Person
function Person(name, age) {
    this.name = name
    this.age = age
}

Person.prototype.getName = function() {
    return this.name
}
Person.prototype.getAge = function() {
    return this.age
}

// Employee
function Employee(name, age, position) {
    this.name = name
    this.age = age
    this.position = position
}

Employee.prototype.getName = function() {
    return this.name
}
Employee.prototype.getAge = function() {
    return this.age
}
Employee.prototype.getPosition = function() {
    return this.position
}
```



Person 객체와 Employee 객체는 공통적으로 `getName()`  `getAge()` 메소드를 가지고 있다. 즉, 메소드가 겹친다.

상속구조를 만들어 Person의 메소드를 Employee에서 사용할 수 있도록 하자.

그러기 위해서는 어떻게 해야할까?



우선 Employee 인스턴스의 `prototype` 에 Person 객체를 할당하자.

```javascript
Employee.prototype = Object.create(Person.prototype)
```

다만, 이렇게만 하면 Employee.prototype 객체를 완전히 Person 객체로 대체해 버린다.

그러므로 Employee 본래의 기능 즉, 정체성을 다시 부여해 줘야 한다. 

```javascript
Employee.prototype.constructor = Employee
```

위와같이 Employee.prototype 의 constructor 을 Employee로 부여해 준다.



결과적으로 다음과 같이 상속을 구현할 수 있다.

```javascript
// Person
function Person(name, age) {
    this.name = name
    this.age = age
}

Person.prototype.getName = function() {
    return this.name
}
Person.prototype.getAge = function() {
    return this.age
}

// Employee
function Employee(name, age, position) {
    this.name = name
    this.age = age
    this.position = position
}


// 부모 자식 연결
Employee.prototype = Object.create(Person.prototype)
Employee.prototype.constructor = Employee

Employee.prototype.getPosition = function() {
    return this.position
}

// Employee 인스턴스를 생성해보자.
var son = new Employee('Son', 26, 'FW')
console.dir(son)
```



다음과 같은 결과를 얻게된다.



![class_inheritance](https://user-images.githubusercontent.com/28145780/45065889-a2870080-b0f6-11e8-88c9-41fab4dd2775.png)

결과를 보면 순서대로

- son

  Employee의 인스턴스

- son.\__proto__

  Employee.prototype

  Person의 인스턴스

- son.\__proto__. \__proto__

  Person.prototype

  Object의 인스턴스

이런 상속구조를 확인 할 수 있다.



오늘의 핵심은 ...

상속할때는 다음과 같이 이루어진다.

- 자식 인스턴스의 `prototype` 프로퍼티에 부모 객체를 할당
- 자식 인스턴스의 `prototype.constructor` 에 자식의 생성자를 다시 부여



