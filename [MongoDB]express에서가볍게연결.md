# express에서 가볍게 연결하는 코드를 작성해보자.
```
var mongoose = require('mogoose');
mongoose.connect('mongodb://localhost:27017/local');

```



# app.js에서 연결1
## on메소드
이벤트를 계속 연결
## once메서드
이벤트를 한번만 연결한 후 제거한다.

```

const mongoose = require('mongoose');
var promise = mongoose.connect('mongodb://localhost:27017/local',{
  useNewUrlParser : true
});

var db = mongoose.connection;
db.on('error', console.error.bind(console, 'connection error : '));
db.once('open', function(){
  console.log('데이터베이스가 연결되었습니다.');
});

```

# app.js에서 연결2

```
//몽고 데이터베이스 사용 모듈
var MongoClient = require('mongodb').MongoClient;
//데이터베이스 객체를 위한 변수 선언
var database;

var databaseUrl = 'mongoDB://localhost:27017/local';

//데이터베이스에 연결
MongoClient.connect(databaseUrl, function(err, db){
  if(err) throw err;
  console.log('데이터베이스에 연결되었습니다. : ' +databaseUrl);
  database = db;//datbase 변수에 할당
});

```
