---
layout: post
title: (Javascript) JSON
comments: true
tags:
- Javascript
---



### JSON

---



JSON에 대해 공부해 보자.



##### JSON이란

---

JSON (JavaScript Object Notation)은 key - value 형태의 데이터 오브젝트를 전달하기 위해 사용되는 개방형 표준 포맷이다. 인터넷 상에서 데이터를 주고 받을때 사용된다. 



##### 문법

---

```json
// SON의 정보를 담은 JSON 객체
{
    "name": "Son",
    "age": 26,
    "nationality": "Korea",
    "team": "Tottenham",
    "hobby": ["soccer", "reading"]
}
```



JSON은 자바스크립트 오브젝트와 같이` { }` 로 감싼다.  `:` 로 key, value를 구분하며 `,` 로 각 쌍들을 구분한다. 배열은 `[ ]` 로 나타낸다.

주의할 점은 문자열을 반드시 `" "` (큰 따옴표)로 묶어야 한다는 점이다. 



##### 장점

---

* 텍스트로 작성되어 있어 사람이 읽고 해석할 수 있다.

* 언어 독립형 데이터 포맷이다. 다시말해, 사용하는 언어와 관계없이 데이터를 주고 받기가 가능하다.

