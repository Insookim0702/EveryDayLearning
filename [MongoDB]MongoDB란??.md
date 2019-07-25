## NoSQL과 RDB의 차이점
학부시절, 데이터베이스 수업시간에 NoSQL에 대한 유튜브 강의를 듣고 보고서를 작성하는 과제가 있었었다. 그때는 영어로 된 강의여서 듣기가 참 어렵고 이해할 수 없었다.
그래서 도서관에서 한글로 된 NoSQL 책을 빌려서 읽어가며 내용을 이해해나갔던 기억이 있었다. 
그 당시 게임 듀랑고를 가끔 하고 있었는데, 듀랑고에 사용하고 있는 DB가 NoSQL인 Couchbase를 사용하고 있어서 흥미를 가지고 과제를 해나갈 수 있었다.

![DURANGO](https://post-phinf.pstatic.net/MjAxODAyMTRfMTk1/MDAxNTE4NTg5MDYwOTQ0.D-EipNR53jECsXD_vqZHcunhDljxd7v9evSzjlbwLvsg.z-pQ5x0jjKBTa7OgRAPYgazjqV74mX2KAsB8CfP32hsg.JPEG/000%ED%83%80%EC%9D%B4%ED%8B%80.jpg?type=w1200)
![DifferentIsMongoAndRdb](https://thepracticaldev.s3.amazonaws.com/i/xwccz9hq6adxiplvb32b.png)
## MongoDB가 뭔가
MongoDB는 스키마가 없는 schema-less NoSQL이다. 관계형 데이터베이스와는 다른 이론을 가지며, 데이터 저장방식 또한 저장문서(Document)에 JSON형식으로 저장한다.

## MongoDB 왜 사용하는지
> This is one of the advantages of using NoSQL as it speeds up application development and reduces the complexity of deployments.

위의 인용구 대로라면, NoSQL을 사용하는데 있어서의 장점은 **빠른 애플리케이션 개발**과 **배치 복잡성을 감소** 시킨다는 내용이다.



## MongoDB와 Mongoose의 차이는 뭔지
Mongoose는 MongoDB와 Node.js에서 사용하는 ODM(Object Data Mapping) 라이브러리이다. Mongoose가 하는 일은 데이터와의 관계를 관리하는 일, 스키마의 확인(Validation)을 제공하는 일
그리고 코드 안에 객체들과 MongoDB에서 객체참조를 변환하는 역할을 하고 있다.
![RelationOfNodeMongoDBMongoose](https://cdn-images-1.medium.com/max/1024/0*b5piDNW1dqlkJWKe.)


## MongoDB 뭐와 쓰면 좋은지

## MongoDB 어디에 쓰면 좋은지

## MongoDB 어떻게 쓰는지

## MongoDB 




[공부 참조 글](https://www.codementor.io/theoutlander/introduction-to-mongoose-for-mongodb-gw9xw34el)
