# <Window에서 MySQL의 Charset을 UTF-8로 기본 설정>

## 1. charset 상태 확인
mysql CommandLine 실행 > ```status``` 명령어 입력

## 2. my.ini 찾기
```SHOW VARIABLES WHERE Variable_Name LIKE "%dir"```를 입력

## 3. 다음을 my.ini에 입력한다.
```
[client]
default-character-set=utf8

[mysqld]
character-set-client-handshake = FALSE
init_connect="SET collation_connection = utf8_general_ci"
init_connect="SET NAMES utf8"
character-set-server = utf8

[mysql]
default-character-set=utf8

[mysqldump]
default-character-set = utf8
```

## 4. 서비스에 들어가서 MySQL을 재시작.

## 5. cmd에서 MySQL을 켜서 status를 입력
