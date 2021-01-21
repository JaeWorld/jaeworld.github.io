---
layout: post
title: (Javascript) 클래스(Class)
comments: true
toc: true
toc_sticky: true
use_math: true

categories:
  - JavaScript
tags:
  - JavaScript
---



### 클래스(Class)

---



ES6에서부터 `class`가 추가되었다. 기존 자바스크립트에서는 객체지향을 구현하기 위해서 `prototype`이라는 고유의 방법을 사용해야 했다. ES6에서 `class`를 도입하면서 다른 언어들과 유사한 방식으로 상속을 구현할 수 있게되었다.



##### 클래스 선언

---

클래스를 선언하는 방법은 타 언어와 유사하다.

```javascript
class Person {
    constructor(firstName, lastName) {
        this.firstName = firstName
        this.lastName = lastName
    }
}
```



클래스를 선언하고 생성자(Constructor) 메소드로 초기화 해준다. 클래스 내에서 생성자 메소드는 하나만 존재해야 한다.

 

##### 메소드 정의

---

클래스 내부에서 메소드를 정의 할 수 있다.

```javascript
class Person {
    constructor(firstName, lastName) {
        this.firstName = firstName
        this.lastName = lastName
    }
    
    // 메소드 선언
    sayHello() {
        return `Hello ${this.firstName} ${this.lastName}`
    }
}
```



##### 정적 메소드

---

클래스의 프로퍼티를 사용하지 않는 단독적인 메소드를 정적(static) 메소드로 정의한다.

```javascript
class Person {
    constructor(firstName, lastName) {
        this.firstName = firstName
        this.lastName = lastName
    }
    
    // 정적 메소드 정의
    static sumNumbers(x, y) {
        return x + y
    }
}
```

정적 메소드는 인스턴스에서 호출할 수 없다. 클래스를 통해서 호출할 수 있다.

```javascript
// 인스턴스 생성
const jae = new Person('Hyunjae', 'Suh')

console.log(jae.sumNumbers(3, 4)) // TypeError
console.log(Person.sumNumbers(3, 4)) // 7
```

