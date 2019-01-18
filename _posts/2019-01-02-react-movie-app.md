---
layout: post
title: "make web service using react js"
excerpt: ""
categories: [dev-front]
date: 2019-01-02 19:00:00
comments: true
---

[web pack](http://webpack.github.io/)
[face book: create-react-app](https://github.com/facebook/create-react-app)

- 트랜스파일러: 리액트 코드를 자바스크립트로 바꿔주는 툴의 명칭 중 하나.
- 웹팩: 리액트 코드를 브라우저가 이해할 수 있는 코드로 변경.

> 리액트로 작업하기 위해서는 웹팩과 같은 모듈 번들러가 필요.

- create react app: 페이스북이 초보자를 위해 제공하는 툴로 웹팩과 같은 툴을 사용할 필요 없이 손쉽게 리액트 앱을 제작해주는 툴(대신 작업)

```
npn install -g create-react-app
create-react-app movie_app
cd movie_app/
npm start

cd movie_app
yarn start // js의 모든 코드를 가져와 html 파일에 담음(movie_app/public/imdex.html)

// usning pre-built development server.
// Edit src/App.js and save to reload.
```

component design for movie_app 
- first, movie list component
- second, movie card component
- third, movie cover component

jsx
- html이 자바스크립트 안에 있는 구조 
- 리액트 컴포넌트 만들때 사용하는 언어




