## 튜플 최신순부터 출력하기.
select 문으로 출력하면 테이블에 입력된 순서대로 출력된다. 가장 최신에 입력된 결과물부터 보고싶다면?
```sql
ORDER BY 열 번호 DESC
```

만약 1번 열이 auto_increment로 1부터 자동 증가값을 가지는 열의 테이블을 최신부터 출력하려면,
```sql
SELECT * FROM 테이블이름 ORDER BY 1 DESC
```
