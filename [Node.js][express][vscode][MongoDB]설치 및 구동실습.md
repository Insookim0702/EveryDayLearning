## node.js & vscode & express  & MongoDB 설치하기
일단 별도의 설정 없이 설치만하면 node.js서버의 경우 그냥 세팅이 된다. 코드만 입력하면 된다. vscode도 홈페이지에서 다운받으면 되고, express와 MongoDB는 vscode 혹은 window cmd창에서 프로젝트 경로 안에 설치 명령어를 입력하여 설치한다.

### 설치하면서 느낀점.
eclipse나 spring처럼 WAS를 설정해주거나 설치해줘야 하는 번거로움이 사라졌고, 개발자가 개발에만 집중할 수 있도록 심플한 개발환경 세팅이 가능했다.


### 1. node.js 홈페이지에서 node.js 툴 [다운받기](https://nodejs.org/en/)
![](https://user-images.githubusercontent.com/42515875/61799507-34f6d680-ae66-11e9-9248-5efa2fcfa501.png)
node.js 다운로드 [홈페이지](https://nodejs.org/en/)에 접속하여 다운로드. (아무거나 상관없지만 안정화버전을 다운한다.)
경로설정 및 라이센스 동의를 확인 후 설치 진행한다.

### 2. vscode [다운받기](https://code.visualstudio.com/)
![](https://user-images.githubusercontent.com/42515875/61799774-aa62a700-ae66-11e9-87ae-0ef994b73494.png)

### 3. express.js 다운받기(vscode terminal에서 명령어로 다운받음.)
  1) 터미널창에서 ```npm init```명령어를 입력 => package.json 파일이 생성된다.
  2) ```npm install express --save```으로 node_modules를 설치한다.
  ![](https://user-images.githubusercontent.com/42515875/61801620-0b3fae80-ae6a-11e9-9966-02697e290086.png)
  3) 설치 후 server.js 파일을 생성하고 다음 코드를 작성하여 크롬에 글자를 출력해보는 서버 스크릡트를 짜본다.
    
 ``` 
    var express = require('express');
    var app = express();
    app.get('/servercheck', function(req, res){
      res.send('서버스크립트 동작 확인')ㅣ
    });
    app.listen(3000, function(){
      console.log('서버 정상 작동 중...');
    })   
 ```

### 4. 크롬으로 서버 작동확인하기
```node server.js```를 터미널창에서 실행하면 console로그로 ```'서버 정상 작동 중...'```이 출력된다.
![](https://user-images.githubusercontent.com/42515875/61801622-0bd84500-ae6a-11e9-9ff5-98e2e34c80b6.png)


### 4. MongoDB 설치하기
터미널(vscode) 또는 window cmd창에서 다음 명령어로 Mongoose 모듈을 설치할 수 있다.
```npm install -save mongodb mongoose```
![](https://user-images.githubusercontent.com/42515875/61801619-0b3fae80-ae6a-11e9-95f0-2c66c2579af1.png)


