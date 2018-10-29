---
layout: post
title: (CSS) CSS 우선순위
comments: true
tags:
- CSS
---



### CSS 우선순위

---



CSS의 우선순위에 대해 공부해보자.



##### 우선순위라니?

---

웹페이지를 로딩하면 브라우저는 HTML과 CSS를 파싱한 후 렌더링 과정을 거쳐 유저에게 보여준다. CSS 코드 내에는 서로 충돌하는 속성들이 존재할 수 있다. 이때 브라우저는 CSS를 파싱하는 과정에서 웹페이지의 CSS 내에 겹치는 속성들에 대해 우선순위를 매겨 어떤 속성값을 적용할지 선정한다. 

브라우저가 어떤 방식으로 우선순위를 매기는지 알아야 원하는 결과가 출력되도록 CSS 코드를 작성할 수 있다.



##### 우선순위

---

CSS의 우선순위는 다음과 같다.

1. `!important` 
2. **Inline styles**
3. **ID**
4. **class**
5. **Elements**
6. 순서 (가장 뒤에 선언된 값이 적용됨)



##### 예제

---

예제를 보며 살펴보자.



```css
.button {
    background-color: red !important;
}

.button #nav {
    background-color: blue;
}
```



![css_priority_1](https://user-images.githubusercontent.com/28145780/47654220-b10d0800-dbcd-11e8-9a6e-740bd26cb9eb.png)

`!important` 값이 부여된 속성값은 최우선적으로 적용된다. 그러므로 배경색이 red이 되었다.

---



```css
.button {
    background-color: red;
}

.button ,div{
    background-color: blue;
}
```



![css_priority_3](https://user-images.githubusercontent.com/28145780/47654678-b7e84a80-dbce-11e8-99e5-693a160ea8c0.png)



`.button` 클래스가 공통으로 존재하지만 아래 선언부에 `div` 엘리먼트가 있으므로 배경색이 blue가 된다.

---

```css
.button {
    background-color: red;
}

.button ,div{
    background-color: blue;
}

#nav {
  	background-color: purple;
}
```



![css_priority_2](https://user-images.githubusercontent.com/28145780/47654516-52945980-dbce-11e8-94ed-f1fc7ac6a820.png)



ID의 우선순위가 가장 높으므로 배경색이 purple이 된다.

---



