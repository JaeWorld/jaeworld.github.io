---
layout: post
title: (Vue.js) vue-cli로 프로젝트 생성
comments: true
tags:
- Vue.js
---



### vue-cli로 프로젝트 생성하기

---



Vue.js 는 손쉽게 프로젝트 생성을 지원하는 공식 CLI(Command Line Interface)를 제공한다. 



##### vue-cli 설치

우선 CLI를 설치한다. 터미널에 다음 명령어를 입력하여 설치할 수 있다.

```
npm install -g @vue/cli
# OR
yarn global add @vue/cli
```



> *참고: 기존 패키지 이름인 `vue-cli`가 `@vue/cli` 로 바뀌었다.* 



##### Vue.js 프로젝트 생성하기

설치된 CLI를 이용해 Vue.js 프로젝트를 생성한다. 

 ```
vue create [project-name]
 ```



##### 프로젝트 실행하기

프로젝트의 디렉토리로 이동하여 실행한다.

```
cd [project-name]
yarn serve
```



