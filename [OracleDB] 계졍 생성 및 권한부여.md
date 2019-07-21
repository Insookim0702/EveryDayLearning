### TableSpace(테이블스페이스)란?
> 오라클 내부에서는 데이터 블록, 익스텐트(extent), 세그먼트(segment), 테이블스페이스(TableSpace)라는 논리적인 개념으로 데이터를 관리한다.
> 오라클에서 데이터를 저장하는 가장 최소의 논리적인 단위가 **데이터 블록**이며, 데이터블록이 모이면 익스텐트가 되고, 익스텐트가 모여 세그멘트, 세그멘트가 모여 테이블스페이스가 된다. 실제로 물리적인 데이터 파일(확장자가 dbf나 ora인 파일)은 테이블스페이스와 대응된다.

> 하나의 테이블 스페이스는 최소 1개의 데이터파일로 구성된다.


### 테이블스페이스 생성하기
```
create tablespace 테이블스페이스 datafile '경로/파일명'
```


### 현제 OracleDB에 만들어진 테이블 스페이스 보기
```
SELECT * FROM dba_tablespaces;
```

### OracleDB에 접근하는 방법
1. window cmd에서 sqlplus id/pw@ip:port/sid
2. ORACLE SQL Developer(OracleDB Client Tool)로 접근

### Oracle 관리자 권한으로 접속
```
su -oracle
sqlplus '/as sysdba'
```

### DB에 있는 계정 확인
```
SELECT * FROM DBA_USERS;
```
![SELECT * FROM DBA_USERS;](https://user-images.githubusercontent.com/42515875/61592006-493d9800-ac08-11e9-9f91-7a07a8cf7b3d.png)

### 계정 생성
```
CREATE USER 아이디 IDENTIFIED BY "비밀번호" default TABLESPACE 테이블스페이스이름;
```
![CREATE USER schfom IDENTIFIED BY "schfom2019!!" default TABLESPACE TS_SEARCH_DAT;]()
### 계정에 권한 부여
* 테이블 생성, 세션,  부여
```
grant create table, create session to 계정이름;
```
![grant create table, create session to schfom;](https://user-images.githubusercontent.com/42515875/61592426-0252a100-ac0e-11e9-8cec-3d70131c3014.png)

* 계정 접근 권한 부여
```
grant connect, resouce to 계정이름;
```
![grant connect, resource to schfom;](https://user-images.githubusercontent.com/42515875/61591992-23b08e80-ac08-11e9-894b-cd08ab54ea7d.png)


### 계정 접속
```
conn id/"pw";
```
![conn schfom/"schfom2019!!";](https://user-images.githubusercontent.com/42515875/61591975-ed730f00-ac07-11e9-8e1d-8341c6db89fb.png)


### 계정이 소유한 테이블 확인
```
SELECT 테이블명 FROM USER_TABLES;
```
