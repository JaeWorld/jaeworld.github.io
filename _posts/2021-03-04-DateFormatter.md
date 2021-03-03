---
layout: post
title: (Matplotlib) DateFormatter 사용하여 날짜 포맷팅하기
comments: true
categories: Visualization
tags: 
- Matplotlib
---



### DateFormatter 사용하여 날짜 포맷팅하기

---

Matplotlib. Seaborn으로 x축이 datetime 타입인 시계열 그래프를 그릴때, 원하는 날짜 포맷으로 표기하기 위해서는 추가 작업이 필요하다. 이때 DateFormatter을 사용하여 날짜를 포맷팅하는 방법을 알아보자.



### Base Code

실습에 사용할 환경과 데이터셋은 아래와 같다.

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# 실습에 사용할 예시 데이터
date = ['1975-12-03', '1988-08-15', '1998-01-17', '2002-06-30', '2008-08-20', '2011-03-16']
value = [1,4,5,9,10,12]
df = pd.DataFrame({
    'date': date,
    'value': value
})

df['date'] = pd.to_datetime(df['date'])
df
```

![dateformatter0](https://i.ibb.co/Fwjv5RW/dateformatter0.jpg)

### 문제점

우선 별도의 작업 없이 Matplotlib으로 그래프를 그려보자. 

```python
fig, ax = plt.subplots(figsize=(10, 7))
ax.scatter(x=df['date'], y=df['value'])
plt.grid()
plt.show()
```

![dateformatter1](https://i.ibb.co/wdQsW2d/dateformatter1.jpg)

x축에 **연도만 표시**된 것을 확인할 수 있다. 만약 연도와 월, 일 등을 표기하고 싶다면 추가 작업이 필요할 것이다. DateFormatter을 이용하여 문제를 해결할 수 있다.



### DateFormatter 사용하여 날짜 포맷팅

`matplotlib.dates` 모듈의 `DateFormatter`을 사용하여 그래프의 **날짜를 원하는 형식으로 포맷팅**할 수 있다. 

방법은 다음과 같다.

1. 데이터를 사용해 그래프를 그린다.
2. `DateFormatter `객체를 생성한다. 이때 날짜를 표기하고자 하는 형식을 지정한다.
3. `set_major_formatter()` 메서드를 사용해 x축 레이블을 포맷팅한다.



#### Code

```python
import matplotlib.dates as mdates

fig, ax = plt.subplots(figsize=(10, 7))

# 1. 그래프를 그린다.
ax.scatter(x=df['date'], y=df['value'])
# 2. DateFormatter 객체를 생성한다. 포맷팅할 형식도 함께 지정한다.
dateFmt = mdates.DateFormatter('%Y-%m-%d')
# 3. x축 레이블을 포맷팅한다.
ax.xaxis.set_major_formatter(dateFmt)

plt.xticks(rotation=45)
plt.show()
```

![dateformatter2](https://i.ibb.co/C1F74ZV/dateformatter2.jpg)



### 사용 예시

포맷팅 형식을 '%Y.%m.%d', '%Y-%m' 와 같이 다양하게 지정할 수도 있다.

```python
import matplotlib.dates as mdates

fig, ax = plt.subplots(figsize=(10, 7))
ax.plot(df['date'], df['value'], marker='o', markersize=10)
dateFmt = mdates.DateFormatter('%Y.%m.%d')
ax.xaxis.set_major_formatter(dateFmt)
plt.xticks(rotation=45)
plt.grid()
plt.show()
```

![dateformatter4](https://i.ibb.co/GHy6G1n/dateformatter4.jpg)



 ```python
import matplotlib.dates as mdates

fig, ax = plt.subplots(figsize=(10, 7))
ax.plot(df['date'], df['value'], marker='o', markersize=10)
dateFmt = mdates.DateFormatter('%Y-%m')
ax.xaxis.set_major_formatter(dateFmt)
plt.xticks(rotation=45)
plt.grid()
plt.show()
 ```

![dateformatter5](https://i.ibb.co/XkcXFL4/dateformatter5.jpg)