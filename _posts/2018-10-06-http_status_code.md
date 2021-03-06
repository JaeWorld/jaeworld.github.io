---
layout: post
title: HTTP 상태 코드(Status Code)
comments: true
tags:
- Web
---



### HTTP 상태 코드 (Status code)

---



##### HTTP란

---

HTTP(HyperText Transfer Protocol)는 웹에서 정보를 주고 받을때 사용되는 프로토콜이다. 서버와 클라이언트 사이에 이루어지는 요청,응답을 처리하는 역할을 수행한다.



##### HTTP 상태 코드

---

클라이언트가 서버에 접속하여 어떠한 요청을 하면 서버는 세자리의 HTTP 상태 코드와 함께 응답한다. 이를 통해 서버와 클라이언트간 통신 상태를 확인할 수 있다.

HTTP 상태 코드를 살펴보자. 여기서는 일반적으로 볼 일이 있을만한 코드를 살펴볼 것이다.



* **200** : "OK"

  클라이언트의 요청을 성공적으로 받아들였을때 사용된다.

* **400** : "Bad Request"

  잘못된 문법으로 인해 클라이언트의 요청이 실패했을때 사용된다. 

* **401** : "Unauthorized"

  인증이 필요한 페이지에서 인증 없이 접근시 사용된다. 클라이언트는 원하는 응답을 받기 위해 인증을 해야한다.

* **403** : "Forbidden"

  서버가 클라이언트의 요청을 거절할때 사용된다. 즉, 클라이언트가 컨텐츠에 접근할 권한을 가지고 있지 않을때이다.

* **404** : "Not Found"

  클라이언트가 요청한 리소스가 없을때 사용된다. 즉, 해당 페이지가 존재하지 않을때 나타난다.
