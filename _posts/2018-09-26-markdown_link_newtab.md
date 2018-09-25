---
layout: post
title: 마크다운 링크 새창으로 열기
comments: true
tags:
- Markdown
---



### 마크다운 에디터 링크

---



마크다운 에디터에서 링크를 넣는 방법을 알아보자.



##### 링크 넣기

---

```markdown
[링크이름](링크URL)
```

위 같은 방법으로 링크를 넣을 수 있다.



**예시**

* 구글 링크

  [Link to Google](https://www.google.com/)

  ```markdown
  [Link to Google](https://www.google.com/)
  ```

* 네이버 링크

  [네이버로 가자](https://www.naver.com/)

  ```markdown
  [네이버로 가자](https://www.naver.com/)
  ```




##### 링크 새창에서 열기

---

링크를 새창으로 띄우려면 다음과 같은 방법을 이용한다.

```markdown
[링크이름](링크URL){: target="_blank"}
```

링크 URL 뒤에 `{: target="_blank"}` 을 추가한다.



##### 예시

* 구글 링크(새창)

  [Link to Google](https://www.google.com/){: target="_blank"}

  ```markdown
  [Link to Google](https://www.google.com/){: target="_blank"}
  ```

* 네이버 링크(새창)

  [네이버로 가자](https://www.naver.com/){: target="_blank"}

  ```markdown
  [네이버로 가자](https://www.naver.com/){: target="_blank"}
  ```
