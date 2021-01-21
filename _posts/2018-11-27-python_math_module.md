---
layout: post
title: (Python) Math 모듈
comments: true
toc: true
toc_sticky: true
use_math: true

categories:
  - Python
tags:
- Python
---



### 파이썬 Math 모듈

---



수학과 관련된 함수를 담고 있는 Math 모듈에 대해 공부해보자.



파이썬에서는 math 모듈에 담긴 다양한 수학 함수를 사용하여 간편하게 수학 계산을 할 수 있다. 



##### 모듈 import

---

math 모듈을 사용하기 위해서는 모듈을 import 한다.

```python
import math
```



##### Pi, e

---

원주율, 자연 상수

```python
math.pi
# 3.141592653589793

math.e
# 2.718281828459045
```





##### abs() 

---

절댓값 함수

```python
abs(-10)
# 10
```



##### round(), ceil(), floor()

---

반올림, 올림, 내림 함수

```python
round(3.2)
# 3

round(4.8)
# 5

math.ceil(1.2)
# 2

math.floor(1.2)
# 1
```



##### pow(), sqrt()

---

제곱, 제곱근 함수

```python
math.pow(3, 2)
# 9.0

math.pow(2, 5)
# 32.0

math.sqrt(4)
# 2.0

math.sqrt(144)
# 12.0
```



##### log()

---

로그 함수

```python
math.log(3)
#1.0986122886681098

math.log(4, 2)
# 2.0
```





