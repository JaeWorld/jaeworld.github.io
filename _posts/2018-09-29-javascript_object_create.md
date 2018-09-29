---
layout: post
title: (Javascript) Object.create()
comments: true
tags:
- Javascript
---



### Object.create()

---



자바스크립트 메소드 `Object.create()`에 대해 알아보자.

`Object.create()` 는 지정된 프로토타입 객체 및 지정된 속성을 가지는 새로운 객체를 생성하는 메소드이다. 자바스크립트에서 상속구조를 구현할때 사용된다.



##### 문법

---

> Object.create(prototypeObject, propertiesObject)



* `prototypeObject` :  새로 생성된 객체가 가질 프로토타입 객체
* `propertiesObject` : 새로 생성된 객체의 자신의 속성. 선택사항.



##### 예제 코드

---

  예제 코드를 통해 자세히 알아보자.



```javascript
// 상위 클래스 Person
function Person(firstName, lastName) {
  this.firstName = firstName
  this.lastName = lastName
}  

// Person 클래스 메소드
Person.prototype.getFullName = function() {
  return`Hello ${this.firstName} ${this.lastName}!`
}

// 하위 클래스 Student
function Student(firstName, lastName, score) {
  // Person 클래스 생성자 호출
  Person.call(this, firstName, lastName)
  // Student 클래스 score 속성 지정
  this.score = score
}

// Object.create()을 이용해 Person와 Student의 프로토타입 연결.
// Student가 Person을 상속받게됨
Student.prototype = Object.create(Person.prototype)
Student.prototype.constructor = Student

// Student 객체 생성
const student1 = new Student('Hyunjae', 'Suh', 85)

console.log(student1 instanceof Person)  // true
console.log(student1 instanceof Student)  // true
console.log(student1.getFullName())  // 'Hello Hyunjae Suh'
```



위 예제에서는 Student 클래스가 Person 클래스를 상속받고있다. 

`Object.create()` 메소드를 사용해 `Student.prototype` 과 `Person.prototype` 을 연결하여 상속구조를 만들었다. 