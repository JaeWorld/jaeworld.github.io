---
layout: post
title: (React) 'Hello world!'
tags:
- React
- Javascript
---

### React로 'Hello world!'

최근 학습중인 리액트에 대해 정리



리액트를 이용한 Hello world! 페이지를 만들어 보겠다.

```
/hello-world
	/js
		react.js
		react-dom.js
	index.html
```

프로젝트 폴더의 형태는 위와 같다.



```
<!DOCTYPE html>
<html>
    <head>
        <script src="js/react.js"></script>
        <script src="react-dom.js"></script>
    </head>
    <body>
        <div id="content"></div>
    </body>
</html>
```

index.html 파일을 위와 같이 생성한다. 

리액트를 사용하기 위해 head태그에 react.js, react-dom.js 두개의 파일을 추가한다. 

body태그에 div태그를 id를 content로 생성한다.



이제 리액트 엘리먼트를 생성하기 위한 자바스크립트 코드를 작성한다.

```
React.createElement(elementName, data, child)
```

위의 함수를 이용해 엘리먼트를 생성할 수 있다.

함수의 인자를 살펴보자.

- element : 'div', 'h1'과 같이 html태그를 문자열로 작성하거나 컴포넌트 클래스 객체를 넘겨줌
- data :  name, href 같은속성 데이터
- child : 태그 내부 또는 자식 엘리먼트의 내용

가령 

```
React.createElement('div', {id: 'content'}, 'Hello world')
```

위같은 함수는 id가 content인 div태그내에 Hello world을 가진 엘리먼트를 생성한 것이다.



```
var h1 = React.createElement('h1', null, 'Hello world!')
```

h1요소를 리액트 엘리먼트로 생성하여 h1변수에 담는다.

```
ReactDOM.render(
	h1,
	document.getElementById('content')
)
```

이후,ReactDOM.render() 함수를 사용하여 h1을 id가 content인 실제DOM 노드에 렌더링한다.



```
<!DOCTYPE html>
<html>
    <head>
        <script src="js/react.js"></script>
        <script src="react-dom.js"></script>
    </head>
    <body>
        <div id="content"></div>
        <script type="text/javascript">
            var h1 = React.createElement('h1', null, 'Hello world!')
            ReactDOM.render(
                h1,
                document.getElementById('content')
            )
        </script>
    </body>
</html>
```

자바스크립트를 적용시키면 

Hello world! 을 출력하는 페이지를 열 수 있다.
