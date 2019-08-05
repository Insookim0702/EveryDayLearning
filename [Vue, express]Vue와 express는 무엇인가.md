# 시작하며
스터디를 진행하면서, 프론트로 Vue를 사용하기로 했다. 그런데 처음 이것저것 서버를 node.js사용하는 app을 간단하게 만들면서 프론트는 ejs도 쓰고 express는 설치했는데 어디에 쓰인건지 모르겠고, 
ejs가 express인거 같기도 싶고 정말 헷갈렸다. 어디 블로그에서는 Vue와 express를 프론트에 동시에 사용하기도 하고, express였던 것을 Vue로 바꿔가면서 개발을 해나가는 글을 봐왔다.

# Vue, express, ejs 개념 확인하기
## Vue

## express
> Express는 Node.js를 위한 웹 프레임워크이다. 
> Express.js는 Node.js의 핵심 모듈인 http와 Connect 컴포넌트를 기반으로 하는 웹 프레임워크이다.
> express를 통해서 빠른 웹 어플리케이션 개발을 할 수 있다.(express generator)를 수행하면 된다.

npm을 사용해서 express generator를 생성해보자. 
1. express-generator를 생성한다.
```
npm install -g express-generator
```
2. express 프레임워크를 만든다.
```
express --view=ejs [express 프레임워크가 생성될 파일이름]
```
ex) > express -view=ejs expressTest <br>
![express-framework-construct](https://user-images.githubusercontent.com/42515875/62298242-9d206a80-b4ad-11e9-8abc-64b3423a0d93.png)
## express framework 프레임워크 구조

> 
> ```javascript
>├── app.js    //서버의 설정을 담아놓은 파일 웹 어플리케이션 서버에 설정할 모듈을 포함시키는 곳.
>├── bin
>│   └── www   //main 함수가 포함된 곳이다. www에서 프로젝트를 실행한다.
>├── package.json //프로젝트가 어떤 모듈에 의존성을 가지는지 모듈 설치시 자동으로 입력된다.
>├── public    //정적 파일(이미지, css,html 등..) 을 저장하는 곳이다.
>│   ├── images
>│   ├── javascripts
>│   └── stylesheets
>│       └── style.css
>├── routes    //서버가 라우팅 할 url path에 대한 로직들을 저장해 놓은 곳이다.
>│   ├── index.js
>│   └── users.js
>└── views     //서버가 렌더링하는 템플릿들을 저장해놓는 디렉토리이다.
>    ├── error.ejs
>   └── index.ejs
> ```

express framework를 설치하고 난 다음에는 
```javascript
npm install   
```
 ```npm install```을 실행하면 디렉토리 상에 ```package-lock.json```이 생성된다.
 
 4. 웹 실행하기
 ```
 node bin/www
 ```
 위의 명령을 입력하고 localhost:3000을 입력하면 express 화면이 정상 출력된다.
 ![greenlight](https://t1.daumcdn.net/cfile/tistory/9923E9355A94DB4313)
 다음이 출력되는 페이지는 routes/index.js이다.

## ejs
