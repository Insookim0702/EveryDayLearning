# MongoDB 뭐와 쓰면 좋은지
>*  MongoDB는 자바스크립트 객체를 그대로 저장할 수 있어서 자바스크립트 언어를 사용하는 노드에서 데이터를 저장하기 좋은 데이터베이스이다.
> * 특히 클라우드 서비스로 서버를 구성하는 경우가 많아지면서 많은 사용자를 수용하거나 시스템 자원을 적게 소모하는 NoSQL이 많이 사용된다.

# MongoDB 어떤 상황에 쓰면 좋은지
[참조 문서](https://sjh836.tistory.com/98)
> * 쌓아놓고 삭제가 없는 경우가 적합하다. (ex. 로그데이터, 세션)
> * Reda & Write 성능이 뛰어나다. 캐싱이나 많은 트래픽을 감당할 때 사용하면 좋다.
> * 트랜젝션이 필요하지 않은 경우 사용하면 좋다.(금융, 결제, 회원정보 수정 같은 빈번한 데이터 변경이 일어나는 경우에는 부적합.)

# MongoDB 어떻게 쓰는지

# Collection에서 명령문
## 생성
``` db.createCollection(name, [options])```

## 조회
``` show collections```

## 제거
``` db.컬렉션이름.drop()```

## 유틸
```db.변경할 컬렉션명.renameCollection("새로운 컬렉션명")```

# Document에서 명령문

## 생성
``` db.컬렉션명.insert(document)```

## 조회
~~~ db.컬렉션명.find([query, projection]).pretty~~~

.pretty 옵션은 출력결과를 한 줄이 아닌 JSON형식을 갖추어서 출력한다.

## 제거
```db.컬렉션명.remove(criteria[, justOne])```
* criteria : 
* justOne boolean



# 쿼리 연산자
## 비교연산자
* $eq  - 주어진 값과 같은 값.
* $gt - 주어진 값보다 큰 값.
* $gte - 주어진 값보다 크거나 같은 값.
* $lt - 주어진 값보다 작은 값.
* $lte - 주어진 값보다 작거나 같은 값.
* $ne - 주어진 값과 일치하지 않는 값.
* $in  - 주어진 배열 안에 속하는 값.
* $nin - 주어진 배열안에 속하지 않는 값.
## 논리연산자
* $or
* $and
* $not
* $nor

## $where 연산자
자바스크립트 표현식을 사용할 수 있다.

## $elemMatch 연산자

