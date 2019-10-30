---
layout: post 
title: (Python) sorted, sort 함수 
---

  

파이썬에서 정렬할 때 쓰이는 `sorted` 함수와 `sort` 함수에 대해 알아보자. 



### sorted 함수 

---



> ` sorted(리스트) ` 



* `sorted` 함수는 정렬된 새로운 리스트를 리턴시킨다. 
* 원래의 리스트에 영향을 주지 않고, **새로운 리스트**를 만들어 리턴한다. 



```python 
num_list = [4, 3, 7, 5, 2] 
print(sorted(num_list)) 

# [2, 3, 4, 5, 7] 
```



### sort 함수 

---



> `리스트.sort()`

* `sort` 함수는 **아무것도 리턴시키지 않는다**. (None 리턴) 
* 원래의 리스트 자체를 정렬한다. 
* `sorted` 와 달리 복사본을 만들지 않기 때문에 비교적 빠르다.



```python 
num_list = [4, 3, 7, 5, 2] 
print(num_list.sort())

# None
```