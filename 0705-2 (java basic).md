# Java-study

**while (반복문)**
- 반복인자의 선언 및 초기값 설정;
- while (실행(종결)조건식) {
- 반복인자값 증감설정
- 실행문(들); }

증감식과 break문의 위치에 따라 다른 결과
- 1~9

```java
int num = 1;
while (true) {
	System.out.print(num + " ");
	num++;
	if (num == 10) break;
}
 ```
- 1~10
```java
int num = 1;
while (true) {
	System.out.print(num + " ");
	if (num == 10) break;
	num++;
}
```

continue문
- 무한 루프를 피하기 위해서 증감식 뒤에 위치
- 1234678910
```java
num = 0;
while (num < 10) {
	num++;
	if (num == 5) continue;
	System.out.print(num);
}
```

**do ~ while**
- 무조건 한 번은 실행

-  반복인자의 선언 및 초기값 설정;
- do {
- 증감설정 (선택적)
- 실행문(들);
- } while (조건식);

- 1~10
```java
int doNum = 1;
do {
	System.out.println("do ~ while : " + doNum);
	doNum++;
} while(doNum <= 10);
```	

```java
doNum = 0;
do {
	doNum++;
	System.out.println("do ~ while : " + doNum);
} while (doNum <= 9);
```

**중첩 반복문 종료**

- out : 1, in : 1
- out : 1, in : 2
- out : 1, in : 3
- out : 2, in : 1
- out : 2, in : 2
- out : 2, in : 3
- out : 3, in : 1
- out : 3, in : 2
- out : 3, in : 3

```java
for (int out = 1; out <= 3; out++) {
	for (int in = 1; in <= 5; in++) {
		System.out.println("out : " + out + ", in : " + in);
		if (in ==3) break;
	}
}
```

- out : 1, in : 1
- out : 1, in : 2
- out : 1, in : 3

```java
outFor:
for (int out = 1; out <= 3; out++) {
	for (int in = 1; in <= 5; in++) {
		System.out.println("out : " + out + ", in : " + in);
		if (in ==3) break outFor; // 외부 for문 중단
	}
}
```

**명명 규칙**

- 영문 대소문자 / (숫자 / 특수문자(_/$) 사용 자제) 
- 대소문자 구분 사용 / 길이 제한 없음 / 숫자로 시작 불가
- 예약어 (keyword) **단독** 사용 불가 (ex: publicName O)
- **한글 사용 자제**

- 파스칼 표기법 (Pascal case) : 대문자로 시작 / 복합어 첫글자 대문자
- 낙타 표기법 (Camel case) : 

- 변수명 / 메소드명 - **첫 글자 : 소문자** (복합어 첫 글자 : 대문자)
- ex) personName, totalValue, computeTotal(), getPersonInfo()
- 클래스 / 인터페이스 - **첫 글자 : 대문자**
- ex) String, System, HelloWorld
- 상수 (상수화된 변수명) - **전체 : 대문자** (복합어 구분 : _ )
- ex) PI, MIN_VALUE, MAX_VALUE
- 패키지명 - **전체 : 소문자** (폴더(디렉토리) 구분 : . )
- ex) com.oracle.net, java.util, com.mystudy.작성모듈명



