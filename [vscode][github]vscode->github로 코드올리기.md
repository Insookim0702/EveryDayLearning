# vscode에서 github remote repository로 코드 올리는 법


## 1. vscode에서 git 초기화버튼을 누른다.(해당 프로젝트 파일에 .git이 생성되었을 것이다.
![init](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fk.kakaocdn.net%2Fdn%2Fb7fLVY%2FbtqxZSQce7c%2F1rGWOdqgEANbKDokNMQDpK%2Fimg.png)
## 2. gitignore를 작성한다.

## 3. 프로젝트 코드를 커밋한다.
![commit](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fk.kakaocdn.net%2Fdn%2Fbvb1j7%2Fbtqx1gC11Al%2FxaLELklHSXvUwo659e18YK%2Fimg.png)
## 4. github repository를 생성한다.

## 5. 생성된 repository에서 다음 부분을 복사한다.
![copy](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fk.kakaocdn.net%2Fdn%2FlgSxM%2FbtqxXKr4UXw%2FapdqsjkTiPIZyyahPckdpk%2Fimg.png)
## 6. 복사한 코드를 vscode 터미널에 입력한다.
![input](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fk.kakaocdn.net%2Fdn%2FbTeGhd%2FbtqxXbJ8zRs%2FQfLmnwW6mkJzeBEvdpOFrK%2Fimg.png)
## 7. 저절로 코드가 remote repository에 올라간다.


## 이미 지정된 원격지 주소 변경하기

## 1. 원격 저장소 지우기
``` 
git remote remove origin
```

## 2. 다시 원격저장소 추가하기

``` 
git remote add origin https://github.com/Insookim0702/Node-vue-cli-Wedpack-BoardAndSignup.git
```


