---
layout: post
title: (Python) List Comprehension
tags:
- Python
---



##### List Comprehension

---



파이썬에서 원하는 조건으로 리스트를 생성할 수 있는 기능이다.

for 루프를 돌아 특정조건에 맞춘 리스트를 생성하는 코드를 간단한 문법으로 표현한 것이다.



`[출력표현식  for문  [if 조건식]]` 

위같이 사용한다.



몇가지 예제 코드를 통해 리스트를 생성해보자.

```python
# 20까지의 짝수 출력하는 리스트
evens = [x * 2 for x in range(11)]
# [0, 2, 4, 6, 8, 10, 12, 14, 16, 18, 20]

# 요소가 정수형이면 값을 제곱해서 저장하는 리스트
oldList = [2, 3, True, 'hi', 5,]

newList = [i * i for i in oldList if type(i) == int]
# [4, 9, 25]

# name과 grade를 조합하여 저장하는 리스트
names = ['Jay', 'Kim', 'Bob']
grade = [1, 2, 3]

info = [(n, g) for n in names for g in grade]
# [('Jay', 1), ('Jay', 2), ('Jay', 3), ('Kim', 1), ('Kim', 2), ('Kim', 3), ('Bob', 1), ('Bob', 2), ('Bob', 3)]
```



for문을 돌아 새로운 리스트를 생성하는 것보다 List Comprehension을 사용하는 것이 코드를 간결하게 해준다.
