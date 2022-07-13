# Java Bean

**캡슐화 Encapsulation**
- 정보 은닉 (Information Hiding)
- 주로 속성은 숨기고 속성에 접근시 기능(method)를 통해 접근 처리

**자바 빈 Java Bean**
- 데이터를 저장하고 접근을 제어하여 데이터를 관리하는 클래스
- 특정 정보를 가지고 있는 클래스를 표현하는 하나의 규칙
- 데이터를 저장 · 조회시 기능(method)를 통해서 접근하게 만들어둔 것

- 멤버 변수(property)의 접근 제한자(제어자) : private으로 선언
- 멤버 변수(property)마다 get/set method(public으로 선언) 제공 (선택적으로 get만 제공) 
- set method : 하나 이상의 파라미터 O
- get method : 파라미터 X 
- 멤버 변수(property)가 boolean 타입이면 get 대신 is method 사용 가능

- 외부에서 멤버 변수(property) 접근시에는 get/set method 통해 접근

# 2차원 배열을 사용한 성적 처리 실습
1. 국어, 영어, 수학 점수 3개를 저장한 2차원 배열(sungjuk) 생성
2. 3명 성적을 입력하고 개인별 총점과 평균을 계산하여 화면에 데이터 출력
-








