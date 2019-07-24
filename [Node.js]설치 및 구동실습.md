### node.js & vscode & express 설치하기
1. node.js 홈페이지에서 node.js 툴 [다운받기](https://nodejs.org/en/)
node.js 다운로드 [홈페이지](https://nodejs.org/en/)에 접속하여 다운로드. (아무거나 상관없지만 안정화버전을 다운한다.)
경로설정 및 라이센스 동의를 확인 후 설치 진행한다.
2. vscode [다운받기](https://code.visualstudio.com/)

3. express.js 다운받기(vscode terminal에서 명령어로 다운받음.)
  1) 터미널창에서 ```npm init```명령어를 입력 => package.json 파일이 생성된다.
  2) ```npm install express --save```으로 node_modules를 설치한다.
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
4. 크롬으로 서버 작동확인하기
```node server.js```를 터미널창에서 실행하면 console로그로 ```'서버 정상 작동 중...'```이 출력된다.

