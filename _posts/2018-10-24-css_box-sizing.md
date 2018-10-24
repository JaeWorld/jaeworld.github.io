---
layout: post
title: (CSS) box-sizing
comments: true
tags:
- CSS
---



### box-sizing

---

CSS의 box-sizing 속성에 대해 공부해보자.



##### box-sizing 속성이란

---

box-sizing 속성은 요소의 height 와 width의 값이 어떻게 계산될지를 정해주는 속성이다. height, width 값을 측청할때 padding 과 border를 포함하여 측정할지 배제하여 측정할지를 정할 수 있다.



box-sizing 속성은 다음 값들을 가질 수 있다.

* content-box

  오직 콘텐츠를 기준으로 height, width값을 측정한다. border, padding은 포함하지 않는다. default 값이다.

* border-box

  border, padding, 콘텐츠 모두를 포함하여 height, width값을 측정한다.



##### 예제

---

예제를 통해 살펴보자.



* content-box

```html
<!DOCTYPE html>
<html>
<head>
  <style>
    * {
      margin: 10px;
      box-sizing: content-box
    }
    
    #content {
      border: 10px solid;
      width: 150px;
    }
    
    #border {
      border: 30px solid;
      width: 150px;
    }
  </style>
</head>
<body>
  <div id="content">box</div>
  <div id="border">box</div>
</body>
</html>
```

![20181024_212341](https://user-images.githubusercontent.com/28145780/47430074-3f028080-d7d3-11e8-8259-ae35447e65be.png)

width값을 모두 150px으로 설정했지만 border 크기 차이로 인해 두 박스의 크기가 다름을 볼 수 있다. content-box는 padding, border를 제외한 콘텐츠의 크기만 측정하도록 하기 때문이다.

* border-box

```html
<!DOCTYPE html>
<html>
<head>
  <style>
    * {
      margin: 10px;
      box-sizing: border-box
    }
    
    #content {
      border: 10px solid;
      width: 150px;
    }
    
    #border {
      border: 30px solid;
      width: 150px;
    }
  </style>
</head>
<body>
  <div id="content">box</div>
  <div id="border">box</div>
</body>
</html>
```

![20181024_212408](https://user-images.githubusercontent.com/28145780/47430085-49bd1580-d7d3-11e8-9c37-303a940af207.png)

width값을 모두 150px으로 설정했다. border-box는 padding, border를 포함하여 크기를 측정하므로 border 크기에 관계없이 두 박스의 크기가 같게 출력된다.