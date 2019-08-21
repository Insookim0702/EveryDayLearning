1. database
2. collection
3. documents


# 1. database

## 1-1 데이터베이스 생성
```use 데이터베이스 명``` 으로 생성.
한 개 이상의 collection이 있어야 조회했을 때 보임.

## 1-2 조회
  * db : 현재 사용 중인 데이터베이스 확인
  * show dbs : 데이터베이스 리스트 확인
  * db.stats() : 데이터베이스 상태 확인

## 1-3 제거
``` db.dropDatabase()```로 데이터베이스를 제거한다.
제거 명령어 사용 전에 제거할 데이터 베이스에 스위치 한 후에 실행한다.
ex) 
```use 제거할 데이터베이스```
```db.dropDatabase()```

# 2. collection

## 1-1 생성
```db.createCollection(name, [options])```으로 컬렉션을 생성한다.
[options]객체의 속성들
* capped: Boolean타입. true로 하면 고전된 크기를 가진 컬렉션을 생성.
* autoIndex : Boolean 타입. true로 하면 _id 필드에 index를 자동으로 생성한다. 삭제될 예정이라고 한다.
* size : number타입. Capped collection 옵션 지정해 줄거면, 최대 사이즈를 지정해 준다. bytes
* max : number타입. 해당 collection을 추가할 수 있는 최대 document갯수를 설정한다.
## 2-2 죄회
```show collections```
## 2-3 제거
``` db.컬렉션명.drop()```
## 2-4 유틸
* ```db.OLD컬렉션명.renameCollection("NEW 컬렉션명")``` : 이름 변경


# 3. documents
## 3-1 생성
```db.컬렉션명.insert(document)```

```
db.movies.insert([
                  {"name" : "어벤저스", price : 13000},
                  {"name" : "존윅2", price : 12000} 
                ]);
```

## 3-2 조회
``` db.컬렉션명.find([query, projection]);```

* query : 조회 조건을 지정해 준다. where 개념.
* projection : 조회할 때 보여질 field를 설정한다. select 개념.
```ex> db.movies.find({},{"_id": false, "name": true, "price" : true})```

## 3-3 제거
```db.컬렉션명.remove(criteria, [justOne]);```
* criteria : document 타입, 아무것도 안넣으면 모든 document가 제거된다. 데이터의 기준 값으로서 일치하면 삭제한다.
* justOne : boolean 타입, true면 1개의 document를 삭제한다.




[참고 문서](https://docs.mongodb.com/v3.4/)
[참고 사이트](https://sjh836.tistory.com/100?category=680972)
