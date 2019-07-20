### tar.gz 다루기

#### 1. tar.gz 압축 풀기
```
$ tar xvfz jdk-8u211-linux-x64.tar.gz
```

#### 2. zip 압축 풀기
```
$ unzip 압푹파일.zip -d 
```


#### 3. jdk 설치하기
* 방법 1. apt-get install oracle-java8-installer (패키지 후보에 없다는 오류 떠서 실패)
* 방법 2. [오라클 홈페이지 접속](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) > jdk1.8.0.tar.gz 다운로드 > tar xvgf ..(잘 됨)

#### 4. jdk 환경 설정
1) jdk1.8.0 **디렉토리** 설치 경로 확인
``` /usr/lib/jvm/jdk.1.8.0.221 ```
2) ``` $ vi /etc/profile ```
가장 아래 줄에 다음 코드를 작성하고 저장.. => JAVA_HOME은 내가 jdk 디렉터리를 둔 경로이다.
```
export JAVA_HOME=/usr/lib/jvm/jdk1.8.0.221
export PATH=$PATH:$JAVA_HOME/bin
export CLASSPATH=.:$JAVA_HOME/lib/tools.jar
```

3) 변경 저장하기
``` source /etc/profile ```
가끔은 source 명령어가 없다는 예의없는 linux가 있을 수 있다.
``` . /etc/profile ``` 로 위기를 모면한다.


#### port PID 찾아서 Kill 로 죽이기
우리 회사 솔루션은 솔루션 서버가 사용하는 port가 많다. port가 가끔 중복으로 잡히면 오류난다.
* port를 사용하는 프로세스 ID(PID)를 찾기
``` $ ps -ef | grep 프로세스명 ```


