---
layout: post
title: (Python) 삼항 연산자
comments: true
toc: true
toc_sticky: true
use_math: true

categories:
  - Python
tags:
- Python
---



### 파이썬의 삼항 연산자

---

파이썬에서 삼항 연산자를 어떻게 사용할 수 있는지 알아보자.



##### 삼항 연산자

---

우선 삼항연산자에 대해 간단히 알아보자.

삼항 연산자는 if else 조건문의 단축형으로 사용할 수 있다.

if else 문에 비해 간결하기 때문에 조건문을 간단히 작성할때 유용하다. 



```java
int result = sum ? "Yes" : "No"
```

C, Java 등의 언어에서 삼항 연산자는 다음과 같이 `?` `:`로 표현된다. 

만약 sum 이면 `result`에 "Yes"를, 아니라면 "No"를 할당한다.



##### 파이썬에서의 삼항 연산자

------

파이썬의 삼항 연산자는 다른언어들과는 살짝 다르게 표현된다.



* **파이썬**

파이썬에서는 앞선 방법대신 `if` `else`를 이용한다.

```python
result = "Yes" if sum else "No"
```

마친가지로 sum 이면 `result`에 "Yes"를, 아니라면 "No"를 할당한다.

타 언어들이랑 순서가 다르니 주의해야한다.
