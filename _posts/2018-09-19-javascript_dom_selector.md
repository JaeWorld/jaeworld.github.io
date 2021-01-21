---
layout: post
title: (Javascript) DOM 접근 메소드
comments: true
toc: true
toc_sticky: true
use_math: true

categories:
  - JavaScript
tags:
  - JavaScript
---



### DOM 접근 메소드

---

##### DOM 이란?

---

우선 DOM이 무엇인지 간단하게 살펴보고 넘어가자. 

DOM (Document Object Model) 은 HTML, XML 웹 문서를 구조화하여 표현하는 인터페이스이다. 웹 페이지를 브라우저가 해석할 수 있는 형태로 구조화해주고 프로그래밍 언어와 웹 페이지를 연결해주는 역할을 수행한다.

자바스크립트로 웹을 다루기 위해서는 DOM요소에 접근해야한다. 웹 페이지에서 특정 DOM요소에 접근하는 방법을 알아보자.



##### DOM 접근 메소드

---

* `document.getElementById( )`

```javascript
// id가 title인 객체 
var title = document.getElementById('title')
```

엘리먼트의 id 값을 이용해 접근 하는 메소드이다. 해당 id의 단일 객체를 리턴한다.



* `document.querySelector( )`

```javascript
// id가 name인 객체 
var name = document.querySelector('#name')

// class가 age인 객체
var age = document.querySelector('.age')
```

엘리먼트의 css선택자를 통해 접근하는 메소드이다. 해당 css 선택자를 가진 단일 객체를 리턴한다.



* `document.querySelectorAll( )`

```javascript
// id가 name인 객체
var names = document.querySelectorAll('#name')

// class가 age인 객체
var ages = document.querySelectorAll('.age')
```

`document.querySelector( )` 와 같이 css선택자를 통해 접근한다. 다만 단일 객체가 아닌 여러 객체가 담긴 리스트를 반환한다.



* `document.getElementByClassName( )`

```javascript
// class가 age인 객체
var age = document.getElementsByClassName('age')
```

엘리먼트의 class 값을 통해 접근하는 메소드이다. 해당 class 을 가지는 객체를 리턴한다. id와는 달리 class는 중복되는 객체가 존재할 수 있으므로 단일객체가 아닌 컬렉션(collection) 객체를 리턴한다.



* `document.getElementByTagName( )`

```javascript
// tag가 img인 객체
var images = document.getElementsByTagName('img')

// tag가 div인 객체
var tasks = document.getElementsByTagName('div')
```

엘리먼트의 tag 를 통해 접근하는 메소드이다. 해당 tag를 가진 객체를 리턴한다. 컬렉션 객체를 리턴한다.



