---
layout: post
title: (Python) any, all함수
comments: true
tags:
- Python
---

### any, all 함수
---

파이썬의 내장 함수인 `any` `all` 함수를 공부해 보자

##### any
---
`any()` 함수는 인자 중에서 참인 값이 하나라도 있을 경우 True를 리턴하고 모든 값이 거짓인 경우에는 False를 리턴한다.

```python
x = [True, False, True]
print(any(x))
// True

x = [1, 2, 3, 0]
print(any(x))
// True

x = [False, 0]
print(any(x))
// False
```

##### all
---
`all()` 함수는 인자로 받은 값이 모두 참이면 True를 리턴하고 거짓인 값이 하나라도 있으면 False를 리턴한다.

```python
x = [True, False, True]
print(all(x))
// False

x = [1, 2, 3, 0]
print(all(x))
// False

x = [True, 1]
print(all(x))
// True
```
