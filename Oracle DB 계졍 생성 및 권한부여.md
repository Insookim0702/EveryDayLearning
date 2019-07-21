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

### 계정 접속
```
conn schfom/"schfom2019!!";
```

