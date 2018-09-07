---
layout: post
title: (Python) while문
tags:
- Python
---



##### while 문

---

파이썬에서의 while문을 알아보자.

while문의 구조는 다음과 같다.

```python
while 조건문:
    수행할 문장
    수행할 문장
    ...
```



조건문이 참인 동안 while문을 돌면서 아래의 문장들을 수행한다.



```python
i = 0
while i < 10:
    i += 1
    print(i,"이 출력되었습니다.")
    
'''
1이 출력되었습니다.
2이 출력되었습니다.
3이 출력되었습니다.
4이 출력되었습니다.
5이 출력되었습니다.
6이 출력되었습니다.
7이 출력되었습니다.
8이 출력되었습니다.
9이 출력되었습니다.
10이 출력되었습니다.
'''
```

while문으로 1부터 10까지 정수를 출력하는 예제이다.

i 가 초기값이 0으로 설정되어 있고, i < 10 일때 까지 while문을 돈다. while문 내에서는 i를 1증가시키고 출력하는 작업을 반복한다.



##### while문 빠져나가기. 

##### break

---

while문을 실행하는 도중 강제로 빠져나가고 싶은 경우가 있다. 그럴때는 `break` 를 이용한다.

```python
// 티켓을 구매하자~!
cost = 200
tickets = 10

while cost:
    print("Selling Tickets!!!")
    tickets = tickets - 1
    if (tickets == 0):
        print("Sold Out...")
        break
        
    
'''
Selling Tickets!!!
Selling Tickets!!!
Selling Tickets!!!
Selling Tickets!!!
Selling Tickets!!!
Selling Tickets!!!
Selling Tickets!!!
Selling Tickets!!!
Selling Tickets!!!
Selling Tickets!!!
Sold Out...
'''

```

티켓을 판매하는 while문 코드이다.

`while cost` 에서 cost는 200으로, 0이 아니므로 참이다. 그러므로 무한루프를 돌게 된다.

ticket 이 10개가 있고, while문을 돌면서 ticket을 하나씩 줄여나간다. (`tickets = tickets - 1`) 그러다가 티켓의 개수가 0이 되면 (티켓이 다 팔리면) 'Sold Out'을 출력하고 `break`로 while문을 탈출한다.

