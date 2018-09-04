---
layout: post
title: (Javascript) 프로토타입
tags:
- Javascript
---



##### Prototype

---

프로토타입 개념은 자바스크립트에서 객체지향프로그래밍을 구현하기 위해 필요한 중대한 개념이다.

자바스크립트에는 클래스가 존재하지 않으므로 프로토타입을 이용해 객체지향프로그래밍을 할 수 있다.



프로토타입은 객체의 원형이다. 

크롬 개발자 콘솔에서 Person 객체를 생성해보자.

![prototype1 2](https://user-images.githubusercontent.com/28145780/44890546-ad681c80-ad15-11e8-8118-38024a339d92.png)

그리고 생성한 Person객체를 열어보자.

![prototype_person](https://user-images.githubusercontent.com/28145780/44890463-58c4a180-ad15-11e8-930b-caf4ffb80a94.png)

객체 내부에는 prototype 과 \_\_proto\__ 의 두가지 속성이 존재한다.

* prototype 속성

prototype 속성은 어원 그대로 자기 자신을 가리킨다. 객체 **자신의 원형**을 가리키는 속성이다.

이 속성 내부에 있는 constructor은 함수가 생성될때 함수 자신과 연결된 프로토타입 객체를 생성하면서 prototype 속성에 연결된다.

* \_\_proto\__ 속성

 \_\_proto\__속성은 **부모객체의 prototype**을 가리킨다. 여기서의 부모객체는 자바스크립트의 최상위 객체인 Object이다. 

그러므로 이 속성은 Object의 prototype을 가리킨다.





---

이제 Person을 이용해 son 객체를 생성해보자.

![prototype1 3](https://user-images.githubusercontent.com/28145780/44890570-c4a70a00-ad15-11e8-9c56-75193e63e212.png)

그리고 객체를 열어 속성을 확인해 보자.

![prototype_son](https://user-images.githubusercontent.com/28145780/44890593-d7b9da00-ad15-11e8-8bf9-d8f6c9e8bdf1.png)

son의  \_\_proto\__속성을 보면  constructor이 Person객체를 가리키고 있다.

그렇기 때문에 son객체는 Person객체의 속성을 모두 사용 할 수 있다.

정리하자면, son객체의 \_\_proto\__ 속성이 부모객체인 Person의 prototype 속성을 가리키고 있으므로 Person 객체의 속성을 모두 사용 할 수 있는 것이다.



---

이와 같이 객체가  \_\_proto\__ 속성을 통해 상위객체에 접근이 가능토록 하는 것을 **프로토타입 체이닝**이라고 한다.

