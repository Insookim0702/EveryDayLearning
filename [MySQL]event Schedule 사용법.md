# event Schedule 생성 전 db 설정 변경
## 1. 이벤트 유무 확인 
```sql
-- event scheduler 상태 확인
SHOW VARIABLES LIKE 'event%';
```
## 2. 이벤트 스케줄 생성을 위한 설정 변경

```sql
-- event scheduler ON/OFF
SET GLOBAL event_scheduler =ON;
SET GLOBAL event_scheduler =1;
SET @@global.event_scheduler =ON;
SET @@global.event_scheduler =1;
```

## 3. 이벤트 스케줄 생성하기
* 조건 | 시점 : 2019-09-09 일부터 매일 09:30:00에 스케줄 시작.
* 프로시저 extractFromExtdata_content()를 실행.


```sql
CREATE
   EVENT 이벤트 스케줄 이름
   ON 실행 조건
   DO
   CALL 프로시저 명 || SQL 쿼리문
```

ex)

```
CREATE
	EVENT evt_AUTOScheduler 
    ON SCHEDULE EVERY 1 DAY
    STARTS '2019-09-09 09:30:00'
    DO
    CALL extractFromExtdata_content();
```


## 스케줄 삭제하기
```DROP EVENT 스케줄 이름;```

ex)
```sql    
-- event scheduler 삭제하기
DROP EVENT evt_AUTOScheduler; 
```

## 스케줄 존재 유무 및 정보 확인 쿼리
```sql
-- event scheduler 확인 Query
SELECT * FROM information_schema.events;
``` 
