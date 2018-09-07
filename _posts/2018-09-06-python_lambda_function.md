---
layout: post
title: (Python) 람다 함수
comments: true
tags:
- Python
---


##### 람다(lambda) 함수

람다함수에 대해 가볍게 알아보고 가자.

람다함수의 형태는 다음과 같다.

```python
lambda 매개변수1, 매개변수2 ... : 매개변수를 이용한 표현식
```

덧셈을 수행하는 람다함수를 만들어보자.

```python
# 람다를 이용한 sum함수
sum = lambda a, b: a+b
sum(2,3)
# 5

# def를 이용한 sum함수, 위 람다함수와 같은 기능을 한다.
def sum(a, b):
    return a+b
```

람다함수는 일반함수보다 간결하게 사용될 수 있고 일반함수를 사용할 수 없는 위치에서도 사용할 수 있다.

예시 코드를 보자.

```python
numlist = [lambda a: a*2, lambda a: a*a]

numlist[0](3)
# 6
numlist[1](3)
# 9
```

`numlist` 리스트의 첫번째 요소, numlist[0] 은 입력받은 a값을 2배하여 리턴하는 람다함수이다. `numlist[0](3)` 3을 2배한 값인 6을 리턴한다.



`numlist` 리스트의 두번째 요소, numlist[1] 은 입력받은 a값을 제곱하여 리턴하는 람다함수이다. `numlist[1](3)` 은 3을 제곱한 값인 9를 리턴한다.



---

위와 같이 리스트처럼 일반 def함수가 들어갈 수 없는 곳에 람다함수를 넣어 사용할 수 있다. 
