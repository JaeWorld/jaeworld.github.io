---
layout: post
title: (Python) ord(), chr() 메소드
comments: true
toc: true
toc_sticky: true
use_math: true

categories:
  - Python
tags:
- Python
---



### ord(), chr() 메소드

---



파이썬에서 문자열의 유니코드를 다루는 내장 메소드인 `ord()` , `chr()` 메소드를 공부해보자.



##### `ord()` 메소드

---

`ord()` 메소드는 하나의 유니코드 문자를 가진 문자열을 인자로 받아 문자의 유니코드 값을 정수로 반환한다. 

##### 예제

```python
print(ord('a')) # 97

print(ord('ㄱ')) # 12593

print(ord('8')) # 56
```





##### `chr()` 메소드

---

`chr()` 메소드는 정수형의 유니코드 값을 인자로 받아 해당 코드가 가리키는 문자를 반환한다.

##### 예제

```python
print(chr(97)) # a

print(chr(97)) # 1

print(chr(92)) # \
```



'P y t h o n'을 출력하고 싶다면 아래와 같이 사용할 수 있다.

```python
print(chr(80),chr(121), chr(116), chr(104), chr(111), chr(110))

# P y t h o n
```

