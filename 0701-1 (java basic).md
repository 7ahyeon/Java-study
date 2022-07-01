# Java-study


**삼항 연산자 ?:**
- (조건식) ? A : B (실행문1 : 실행문2) 
- 조건이 true이면 A를, false면 B를 산출함
- if문과 동일하지만 한 줄로 간단 작성 유리

```java
int score = 95; 
char grade = (score > 90) ? 'A' : 'B';
```

```java
int score = 95;
char grade;
if(score > 90){
  grade = 'A';
} else {
  grade ='B';
}
```

```java
int num1 = 95;
int num2 = 90
String str = (num1 > num2) ? "A등급" : "B등급";
```

```java
if (num1 > num2) {
  str = "A등급";
  } else { str = "B등급";
  }
  ```

**제어문 control statement**
- 실행 흐름을 제어할 수 있게 해주는 것
 * 조건문 conditional statement : if문, switch(case)문
 * 반복문 loop : for문, while문, do-while
 
 # if문 (분기문/비교문)
 
 **if (조건) {}**
 
 ```java
int num1 = 20;
int num2 = 10;
		
if (num1 < num2) {
	System.out.println("num1이 num2보다 작다");
}
if (num1 > num2) {
	System.out.println("num1이 num2보다 크다");
}
if (num1 == num2) {
	System.out.println("num1과 num2가 같다");
System.out.println(">>비교작업 끝");
 ```
 
 **예제1 성적처리**
 ```java

// 점수 평가 결과 출력 : A, B, C, 노력하세요
// 90~100 : A
// 80~89 : B
// 70~79 : C
// 0~69 : 노력하세요
// --------------
// <출력 형태>
// 점수 : 90
// 평과 결과 : A
		
System.out.println("---성적 처리---");
		
int jumsu = 99;

System.out.println("점수 : " + jumsu);
String message = "평가 결과 없음";

if (jumsu >= 90 && jumsu <= 100) {
	message = "A";
}
if (jumsu >= 80 && jumsu <= 89) {
	message = "B";
}
if (jumsu >= 70 && jumsu <= 79) {
	message = "C";
}
if (jumsu >= 0 && jumsu <= 69) {
	message = "노력하세요";
}
System.out.println("평가 결과 : " + message);
```

	---성적 처리---
	점수 : 99
	평가 결과 : A

**1. if (조건) {}**
 ```java
if (num1 > num2) {
	System.out.println("num1이 num2보다 크다");
}
if (num1 <= num2) {
	System.out.println("num1이 num2보다 작거나 같다");
}
```
		
**2. if (조건) {} else {}**
 ```java
if (num1 > num2) {
	System.out.println("num1이 num2보다 크다");
} else {
	System.out.println("num1이 num2보다 작거나 같다");
}
```
		
**3. if (조건) {} else if () {} else if () {} .... else {}**
 ```java
if (num1 > num2) {
	System.out.println("num1이 num2보다 크다");
} else if (num1 == num2) {
	System.out.println("num1이 num2와 같다");
} else {
	System.out.println("num1이 num2보다 작다");
}
```

# switch case문 (동등 비교 구문)

**switch case문 ( if문**
```java
switch (조건값) {
case 비교값1 :
	실행할 문장(들);
	break;
case 비교값2 :
	실행할 문장(들);
	break;
...
default :
		 	실행할 문장(들);
		 	break;
		 }
```

**예제1 날짜**
```java
switch (month) {
case 1 :
case 3 :
case 5 :
case 7 : case 8 : case 10 : case 12 :
	System.out.println(month + "월은 31일까지 있습니다");
	break;
case 2 :
	System.out.println(month + "월은 28일 또는 29일까지 있습니다");
	break;
case 4 : case 6 : case 9 : case 11 :
	System.out.println(month + "월은 30일까지 있습니다");
	break;
default :
	System.out.println(month + "은 잘못된 값입니다 (정상 : 1~12)");
	break;
```

**예제2 경품**

- 추첨 결과에 따라서 상품 지급
- 1등 : 냉장고, 2등 : 김치 냉장고, 3등 : 세탁기, 4등 청소기
- 등수 안에 들지 못한 경우 (꽝) : 휴지

`<출력 형태>
추첨 결과 : 냉장고 (1등 당첨)`

```java
String result = "5등";
String resultMsg = ""; // 빈 문자열
		
switch (result) {
case "1등" :
	resultMsg = "냉장고";
	break;
case "2등" :	
	resultMsg = "김치 냉장고";
	break;
case "3등" :	
	resultMsg = "세탁기";
	break;
case "4등" :
	resultMsg = "청소기";
	break;
default :	
	resultMsg = "휴지";
	break;
}
System.out.println("추첨 결과 : " + resultMsg + " (" + result + " 당첨)");
```

- 1등은 모든 경품, 차례대로 줄어들게 수정

```java
String result = "5등";
String resultMsg = ""; // 빈 문자열
		
switch (result) {
case "1등" :
	resultMsg += "냉장고 ";
case "2등" :	
	resultMsg += "김치 냉장고 ";
case "3등" :	
	resultMsg += "세탁기 ";
case "4등" :
	resultMsg += "청소기 ";
default :	
	resultMsg += "휴지 ";
}
System.out.println("추첨 결과 : " + resultMsg + "(" + result + " 당첨)");
```

**예제3 성적**

- 성적 처리
- 입력 : 국어(kor), 영어(eng), 수학(math) 점수
- 연산 처리
- 총점(tot) = 국 + 영 + 수
- 평균(avg) = 총점 / 과목수
- 평균 점수 구간별 평가(학점)
- 90-100 : A
80-89 : B
70-79 : C
60-69 : D
60 미만 (0-59) : F (재수강)

`<출력 형태> 결과 출력
국어 : 100 영어 : 90  수학 : 80`
`총점 : 270  
평균 : 90  
<평가 결과>
A`

```java
int kor = 10;
int eng = 20;
int math = 30;
		
int tot = (kor+eng+math);
int avg = tot / 3;
		
String h = "";
		
if (avg >= 90 && avg <= 100) {
	h = "A";
} else if (avg >= 80 && avg <= 89) {
	h = "B";
} else if (avg >= 70 && avg <= 79) {
	h = "C";
} else if (avg >= 60 && avg <= 69) {
	h = "D";
} else {
	h = "F(재수강)";
}
		
System.out.println("■ 결과 출력");
System.out.println("국어 : " + kor);
System.out.println("영어 : " + eng);
System.out.println("수학 : " + math);
System.out.println("----------");
System.out.println("총점 : " + tot);
System.out.println("평균 : " + avg);
System.out.println();
System.out.println("<평가 결과>");
System.out.println(h);





