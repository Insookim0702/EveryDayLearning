# 1. AWS 회원가입은 다른 인터넷 글 참조한다.
# 2. 로그인 후... AWS RDS 콘솔로 이동
RDS 옵션을 찾다. (그림은 내가 최근에 사용해서 RDS가 바로 있는 것...)

![ConsolePage](https://user-images.githubusercontent.com/42515875/62833299-8c26e480-bc77-11e9-808f-5d29c3be6649.png)

# 3. 데이터베이스 생성
데이터베이스 생성 버튼을 누른다.

![ClickButton](https://user-images.githubusercontent.com/42515875/62832835-be344880-bc6f-11e9-97cd-585914e8846a.png)

# 4. Enterprice프리티어 적용

AWS는 기본적으로 유료이다. 프리티어로 RDS 인스턴스를 생성해서 무료로 이용하자.

![](https://user-images.githubusercontent.com/42515875/62833372-aad9ab00-bc78-11e9-87cf-6f61966e2fa7.png)


프리티어 스팩 확인

![](https://user-images.githubusercontent.com/42515875/62833441-a5c92b80-bc79-11e9-9b23-82dd557be520.png)

# 5. 외부에서 접근 연결 설정

추가 연결 구성을 눌러서 **퍼블릭 엑세스 가능**을 **예**로 체크한다.

VPC보안그룹은 인스턴스를 생성한 후에 보안그룹을 새로 생성해서 수정해준다. => 기존 항목 선택 그대로..

![](https://user-images.githubusercontent.com/42515875/62832838-c2606600-bc6f-11e9-9f83-0aa951cd5108.png)

# 6.가장 하단에 데이터베이스 생성버튼 클릭
# 7.RDS 생성될 때까지 기다린다.
# 8.보안그룹 설정하기

VPC 보안그룹 클릭
보안그룹을 새로 생성해도 되고, 기존 VPC 보안그룹을 편집해도 된다. 

![ClickVPC](https://user-images.githubusercontent.com/42515875/62833628-f1c99f80-bc7c-11e9-9087-f0e5c2d7c730.png)

**Oracle RDB**, **위치 무관**로 선택하고 저장
![](https://user-images.githubusercontent.com/42515875/62833671-90560080-bc7d-11e9-94db-3f79a9138f36.png)


마지막으로 보안그룹 ID가 생성한 인스턴스의 보안그룹으로 설정되어 있는지 확인한다.

# 9.'사용가능'으로 상태표시가 뜨면 클릭해서 DB 접근 정보 확인

# 10. SQL Developer를 사용한다.
처음 사용법은 기타 구글 검색을 활용하고,

여기서는 DB 접근 정보를 입력하는 것 부터 시작한다.

[테스트] 버튼 눌러서 **상태 : 정상**으로 뜬다면... [접속] 버튼 누르면 되나.

![](https://user-images.githubusercontent.com/42515875/62833909-be890f80-bc80-11e9-812e-10c36e332736.png)


