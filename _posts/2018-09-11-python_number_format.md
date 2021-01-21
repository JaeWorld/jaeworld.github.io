---
layout: post
title: (Python) 숫자 포맷팅
comments: true
toc: true
toc_sticky: true
use_math: true

categories:
  - Python
tags:
- Python
---



### 숫자 포맷팅 (format)

---

파이썬에서 숫자를 포맷팅하는 방법을 알아보자.



##### 숫자

---

* int 형

```python
'{:d}'.format(42)

# 42
```



* float 형

```python
'{:f}'.format(3.141592)

# 3.141592
```



##### 숫자에 공백

---

예제를 통해 살펴보자.



* int형

```python
(ex1)
'{:4d}'.format(23)
#   23

(ex2)
'{:6d}'.format(17)
#     17

(ex3)
'{:04d}'.format(25)
# 0025
```

(ex1) : `{:4d}` 는 숫자를 4자리로 포맷팅. 즉, 23 앞에 2자리 공백을 넣음.

(ex2) : `{:6d}` 는 숫자를 6자리로 포맷팅. 6자리로 맞추기 위해 17앞 네자리에 공백 넣음.

(ex3) : `{:04d}` 는 숫자를 4자리로 포맷팅하고 빈 자리에 0을 넣음



* float 형

```python
(ex1)
'{:4.3f}'.format(3.145352)
# 3.142

(ex2)
'{:06.2f}'.format(3.141592)
# 003.14
```

(ex1) : `{:4.3f}` 는 최소 4자리, 소수점 아래 3자리 수로 포맷팅.

(ex2) : `{:06.2f}` 는 최소 자리수(소수점 포함)가 6이 되고, 소수점 아래 2자리 수로 포맷팅. 공백에는 0을 넣음.
