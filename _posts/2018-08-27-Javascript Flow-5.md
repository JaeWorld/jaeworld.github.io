---
layout: post
title: (Javascript) this
comments: true
toc: true
toc_sticky: true
use_math: true

categories:
  - JavaScript
tags:
  - JavaScript
---

##### this

---



자바스크립트의 this는 매우 헷갈리는 개념이다.

상황별로 this가 가리키는 것이 무엇인지 알아보자.



* 전역공간에서

전역공간에서 this는 전역 객체를 가리킨다.

```javascript
console.log(this); // Window(전역)를 가리킨다.
```



* 함수 내부에서

함수 내부에서의 this는 기본적으로 전역 객체를 가리킨다. 

디폴트값으로 전역 객체를 가리킨다.

```javascript
function a() {
    console.log(this);
}
a(); // Window를 가리킨다.

function b() {
    function c() {
        console.log(this);
    }
    c();
}
b(); // Window를 가리킨다.
```



* 메소드 호출시

메소드 호출시에는 메소드를 호출하는 주체를 가리킨다. 

메소드명 앞에 있는 객체를 가리킨다.

```javascript
var a = {
    b: function() {
        console.log(this);
    }
}

a.b(); // this는 b메소드 앞에 있는 객체인 a를 가리킨다.
```



* 생성자 함수에서

생성자 함수에서는 인스턴스를 가리킨다.

```javascript
function Animal(name, legs) {
    this.name = n;
    this.legs = l;
    // 생성자의 this는 인스턴스를 가리킨다.
}
var cat = new Animal('Cat', 4);
console.log(cat);
```





상황별로 this가 가리키는 대상에 대해 알아보았다. 

무엇보다 this가 가리키는 것을 찾기 위해서는 코드의 문맥을 파악하는게 중요할 것 같다.
