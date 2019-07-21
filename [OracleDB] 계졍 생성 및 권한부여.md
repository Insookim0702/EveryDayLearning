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

### 계정에 권한 부여
* 테이블 생성, 세션,  부여
```
grant create table, create session to 계정이름;
```

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
