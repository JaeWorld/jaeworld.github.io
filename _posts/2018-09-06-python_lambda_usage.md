---
layout: post
title: (Python) lambda 함수 활용
comments: true
toc: true
toc_sticky: true
use_math: true

categories:
  - Python
tags:
- Python
---



##### 람다함수 활용

---

파이썬에서 람다함수가 어떻게 활용되는지 알아보자.



##### 기본적 활용

---

```python
lambda x: int(x)
```

문자열 변수를 정수형으로 변환.

```python
lambda x,y: x>y
```

x, y 값을 비교.

```python
lambda x: x['key']
```

딕셔너리에서 key를 이용해 value를 얻음.



##### 다른 내장함수와의 활용

---

* ##### min, max

```python
# min, max 함수
names = ['Suh', 'Adrian', 'Bill', 'Jonathan']

# longest : 길이가 가장 긴 이름
longest = max(names, key= lambda n: len(n))

print(longest)
# Jonathan
```

`key` 를 `lambda n: len(n)` 로 부여해 가장 길이가 긴 이름을 리턴한다.



* ##### sort, filter, map

```python
keys = [{'key': 8}, {'key': 5}, {'key': 9}, {'key': 3}]
```



```python
# sort 함수
keys.sort(key = lambda x: x['key'])
# [{'key': 3}, {'key': 5}, {'key': 8}, {'key': 9}]
```

keys 리스트를 내부의 `'key'` 들의 value를 기준으로 정렬하였다.



```python
# filter 함수
filter(lambda x: x['key']<5, keys)
```

`'key'` 들의 value가 5보다 작은 요소들을 가져온다.



```python
# map 함수
map(lambda x: x['key']+5, keys)
```

모든 `'key'` 의 value에 5를 더한다.
