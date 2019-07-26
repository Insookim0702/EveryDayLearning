 학부시절, 데이터베이스 수업시간에 NoSQL에 대한 유튜브 강의를 듣고 보고서를 작성하는 과제가 있었었다. 그때는 영어로 된 강의여서 듣기가 참 어렵고 이해할 수 없었다.
그래서 도서관에서 한글로 된 NoSQL 책을 빌려서 읽어가며 내용을 이해해나갔던 기억이 있었다. 
그 당시 게임 듀랑고를 가끔 하고 있었는데, 듀랑고에 사용하고 있는 DB가 NoSQL인 Couchbase를 사용하고 있어서 흥미를 가지고 과제를 해나갈 수 있었다.

![DURANGO](https://post-phinf.pstatic.net/MjAxODAyMTRfMTk1/MDAxNTE4NTg5MDYwOTQ0.D-EipNR53jECsXD_vqZHcunhDljxd7v9evSzjlbwLvsg.z-pQ5x0jjKBTa7OgRAPYgazjqV74mX2KAsB8CfP32hsg.JPEG/000%ED%83%80%EC%9D%B4%ED%8B%80.jpg?type=w1200)

# NoSQL과 RDB의 차이점
* NoSQL은 관계형 데이터베이스와 다르게 데이터를 저장한 객체간에 관계가 없다. 관계가 없으니 join을 하기가 힘들다. 애초에 NoSQL은 Join이나 객체간의 관계를 맺는데 초점을 둔 DB가 아니다. 관계가 없다보니, 기존의 RDB보다 제약이 없다. 필드가 없다. 그래서 성능적인 면에서 RDB보다 뛰어나다. NoSQL이 들고 있는게 적기 때문이다.
* RDB의 스키마가 NoSQL에는 존재하지 않는다. 


|id|name|price|
---|---|---
|int(auto_increment) primary key|varchar(20)|varchar(30)|

위의 표가 바로 RDB의 스키마이다. 데이터 입력의 형식을 미리 정해놓은 것인데, MongoDB에는 이처럼 데이터 입력 타입과 제약을 정하는 스키마가 없다.

```
db.createCollection("product");
db.product.insert({name:1000,price:"숫자아니여도 입력됨(-_ㅡ);"});
db.product.insert({name:"자몽허니블랙티",price:5600,maker:"starbuks"});
```
위의 코드가 가능하다.


![DifferentIsMongoAndRdb](https://thepracticaldev.s3.amazonaws.com/i/xwccz9hq6adxiplvb32b.png)

# MongoDB 특징

## Collection == Table

MongoDB에서 'Collections'이란 용어는 관계형 데이터베이스에서 테이블과 동일하다. MongoDB는 Collections에 JSON형식의 데이터를 가질수 있다.

## Documents에 데이터를 저장한다.

'Documents'는 관계형 데이터베이스에서 SQL의 데이터줄들, 레코드(열들과 동일하다. 
키 : 값들의 집합인 JSON형태로 저장된다.

하지만, 관계형 데이터베이스는 테이블 간에 데이터 참조가 가능하지만, MongoDB는 Documents(문서)에서 결합한다.

## * Fields

SQL 테이블의 컬럼과 유사하다.

## * Schema less-NoSQL

MongoDB는 스키마가 없다. 테이블 정의를 통해서 스키마를 정의한다. 
Mongoose에서 스키마는 document data structure(문서 데이터 구조)이다.

## * Model

## * MongoDB는 단일 인스턴스를 가지고 여러 데이터베이스를 호스팅할 수 있다.
Mysql과 마찬가지로 하나의 인스턴스(계정??)으로 데이터베이스를 여러 개 생성할 수 있다는 말과 동일하게 이해하면 된다.

# MongoDB가 뭔가
MongoDB는 스키마가 없는 schema-less NoSQL이다. 관계형 데이터베이스와는 다른 이론을 가지며, 데이터 저장방식 또한 저장문서(Document)에 JSON형식으로 저장한다.

# MongoDB 왜 사용하는지
> This is one of the advantages of using NoSQL as it speeds up application development and reduces the complexity of deployments.

위의 인용구 대로라면, NoSQL을 사용하는데 있어서의 장점은 **빠른 애플리케이션 개발**과 **배치 복잡성을 감소** 시킨다는 내용이다.
또한, MongoDB는 RDB보다 읽고 쓰는 성능이 뛰어나다고 한다. 
사용이 간편하고, API 레퍼런스를 찾기가 쉽다. 많이 알려져있으며 진입장벽이 낮다.


# MongoDB와 Mongoose의 차이는 뭔지
Mongoose는 MongoDB와 Node.js에서 사용하는 ODM(Object Data Mapping) 라이브러리이다. Mongoose가 하는 일은 데이터와의 관계를 관리하는 일, 스키마의 확인(Validation)을 제공하는 일
그리고 코드 안에 객체들과 MongoDB에서 객체참조를 변환하는 역할을 하고 있다.
![RelationOfNodeMongoDBMongoose](https://cdn-images-1.medium.com/max/1024/0*b5piDNW1dqlkJWKe.)


# MongoDB 뭐와 쓰면 좋은지

# MongoDB 어디에 쓰면 좋은지

# MongoDB 어떻게 쓰는지

# MongoDB 




[공부 참조 글](https://www.codementor.io/theoutlander/introduction-to-mongoose-for-mongodb-gw9xw34el)
