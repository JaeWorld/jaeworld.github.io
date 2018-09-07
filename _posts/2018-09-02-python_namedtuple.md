---
layout: post
title: (Python) namedtuple
comments: true
tags:
- Python
---

##### [Python] namedtuple

---

해커랭크를 풀다가 새로운 기능이 나와서 따로 포스팅을 해보았다. 

namedtuple 에 대한 자세한 정보는 [파이썬 공식문서](https://docs.python.org/2/library/collections.html#collections.namedtuple)에서 확인할 수 있다.



##### Tuple

우선 튜플(Tuple)에 대해 알아보자.

파이썬에는 튜플이라는 자료구조형태가 존재한다.

튜플은 리스트랑 같은 기능을 하지만 몇가지 차이점이 존재한다.

- 리스트는 [ ]로 둘러싸이는 반면, 튜플은 ( )로 둘러 싸인다.
- 리스트는 값의 생성, 삭제, 추가가 가능하지만 튜플은 값을 바꿀 수 없다 (불변성)



튜플은 값을 변경할 수 없는 불변성을 가지므로 

다뤄야 할 요소의 개수를 아는 상태에서 사용하면 용이하다.

---



##### namedtuple

파이썬에서는 namedtuple을 사용할 수 있다.

namedtuple을 사용하면 튜플의 값을 참조할 때 정수형의 인덱스 대신 key값으로 접근이 가능하다.

이는 참조를 더 명시적으로 할 수 있도록 해준다.



```python
collections.namedtuple(typename, field_names)
```

위와 같이 생성할 수 있다.

typename 이라는 이름을 가진 튜플을 생성한다.

field_names 는 튜플내에서 키값으로 사용되는 필드명을 의미한다.

field name은 빈칸이나콤마(,) 로 구분한다.

즉, 'x y' 또는 'x, y' 형태로 입력된다.



학생의 정보를 담는 namedtuple 을 생성해보자.

```python
student = collections.namedtuple('student', 'name, gender, grade, class')
# student라는 이름을 가진 튜플 생성, 이 튜플은 name, gender, grade, class의 필드를 가진다.

student1 = student(name = Jay, gender = male, grade = 2, class = 4)
```

튜플의 값을 참조할때는 다음과 같다.

```python
print(student1.name)
# Jay
print(student1.grade)
# 2
```



명시적이지 못했던 정수형의 index 값에 의한 참조를 보완해주는

namedtuple 에 대해 알아보았다! 

