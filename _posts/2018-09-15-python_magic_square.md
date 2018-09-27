---
layout: post
title: 마방진 (Magic square)
comments: true
tags:
- Mathematics
- Python
---



### 마방진 (Magic square)

---

해커랭크를 풀다가 마방진 문제가 있어 마방진에 대해 포스팅을 해보려 한다. 살~짝 뜬금없긴 하지만 이해하면 흥미로운 소재이므로 다뤄보겠다.



##### 마방진

---

마방진은 자연수를 정사각형 모양으로 나열했을때 가로, 세로, 대각선의 합이 전부 같은 형태의 배열이다.



아래는 3*3 마방진이다. 가로, 세로, 대각선 수들의 합이 같음을 확인 할 수 있다.

![default](https://user-images.githubusercontent.com/28145780/45587278-ca6c3480-b93e-11e8-834d-e37f6c6f939e.png)



##### 마방진 알고리즘

---

마방진이 무엇인지 알았다면 마방진을 그리는 알고리즘을 살펴보자. 여기서는 행의 길이가 홀수인 마방진을 다룰 것이다.

우선 행의 길이를 n이라 하면, 마방진은

* n * n 행렬이다.
* 가로, 세로, 대각선 수들의 결과값은 n(n*n + 1)/2 이다.
* 1 부터 n*n 까지의 수가 들어간다.

그렇다면 이제 마방진을 그리는 방법을 알아보자. 다음과 같은 방법을 이용한다.



1. 첫번째 숫자인 1을 맨윗 행 중간열에 배치한다.
2. 두번째 수부터는 오른쪽 대각선 위로 이동하며 숫자를 배치한다. 행렬의 범위를 넘어가면 반대쪽 끝으로 돌아온다.
3. 만약 숫자를 놓아야하는 자리에 이미 다른 숫자가 배치되어 있다면 현재 위치에서 행을 하나 내린 같은 열의 위치에 숫자를 놓는다. 다음 숫자는 다시 2번을 수행한다.



마방진 작성과정을 파이썬 코드로 작성해 보았다.

```python
# 마방진의 행의 길이를 입력
n = int(input("마방진 행의 길이를 입력해주세요.(홀수)"))

# n*n 크기의 빈 배열 생성
arr = [[0]*n for i in range(n)]

r = 0
c = n//2

# 맨윗행 중간열에 1 배치
arr[r][c] = 1

# 2부터 n*n까지 배치합시다.
for i in range(2, n*n+1):

    # 위치가 비어있을때
    if arr[n-1 if r-1<0 else r-1][0 if c+1>n-1 else c+1] == 0:
        r = n-1 if r-1<0 else r-1
        c = 0 if c+1>n-1 else c+1
        arr[r][c] = i

    # 위치가 차있을때
    else:
        r = 0 if r+1>n-1 else r+1
        arr[r][c] = i

for l in arr:
    print(l)
```



결과값은 아래와 같다.

```python
# 3 입력시
[8, 1, 6]
[3, 5, 7]
[4, 9, 2]

# 5 입력시
[17, 24, 1, 8, 15]
[23, 5, 7, 14, 16]
[4, 6, 13, 20, 22]
[10, 12, 19, 21, 3]
[11, 18, 25, 2, 9]
```


