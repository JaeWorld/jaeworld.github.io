---
layout: post
title: (Bootstrap) Grid
comments: true
tags:
- Bootstrap
---



### (Bootstrap) Grid

---



웹 분야에서 활발히 사용되고 있는 디자인 프레임워크인 부트스트랩을 공부해보자. 이번 포스팅에서는 부트스트랩의 그리드 시스템에 대해 작성한다.



##### 그리드 시스템

---

부트스트랩의 그리드 시스템은 페이지를 12개의 column으로 분할한다. 분할된 12개 column을 사용해 페이지 내 요소들의 크기, 배치를 지정할 수 있다. 

그리드 시스템은 반응적이다. 페이지가 출력되는 화면의 크기에 맞추어 알맞은 화면 배치를 출력한다.



##### 그리드 클래스

---

그리드는 다음 4가지 종류의 클래스를 가진다.

* `.col-xs-*` : 768px 미만의 화면 (항상 가로로 표시됨)
* `.col-sm-*` : 768px 이상의 화면 (768px 미만의 화면에서 세로로 표시됨)
* `.col-md-*` : 992px 이상의 화면 (992px 미만의 화면에서 세로로 표시됨)
* `.col-lg-*` : 1200px 이상의 화면 (1200px 미만의 화면에서 세로로 표시됨)



`*` 자리에 12개의 칼럼 중 몇개를 사용할 것인지 작성한다.



##### 사용하기

---

그리드 시스템의 구조는 아래와 같다. 

```html
<div class="row">
    <div class="col-*-*"></div>
    <div class="col-*-*"></div>
    <div class="col-*-*"></div>
</div>
```



`<div class="row">` 로 row를 생성한 다음, row 내부에 `col-*-*` 클래스를 가지는 태그를 넣는다. 이때 row내의 `col-*-*` 클래스의 숫자들의 합이 12가 되어야 한다.



##### 예제

---

예제를 통해 살펴보자.



```html
<div class="container">
    <div class="row">
      <div class="col-md-4" style="background-color: skyblue">1</div>
      <div class="col-md-4" style="background-color: lightgreen">1</div>
      <div class="col-md-4" style="background-color: orange">1</div>
    </div>
</div>
```





![bootstrap1](https://user-images.githubusercontent.com/28145780/48601999-20983b00-e9b5-11e8-83af-c57bf22b9bb6.png)



`.col-*-*` 의 숫자를 모두 4로 지정하였으므로 4 : 4 : 4 비율에 맞추어 각각의 태그들이 페이지를 3등분하였다.

---



```html
<div class="container">
	<div class="row">
  		<div class="col-md-2" style="background-color: lightgreen">1</div>
  		<div class="col-md-10" style="background-color: orange">1</div>
	</div>
</div>
```





![bootstrap2](https://user-images.githubusercontent.com/28145780/48602195-a74d1800-e9b5-11e8-9a7b-8313e09a13a2.png)



`.col-*-*` 의 숫자를 2, 10 으로 지정하였으므로 2 : 10 비율에 맞추어 각각의 태그가 배치되었다.