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
 * 조건문 conditional statement : if문, switch문
 * 반복문 loop : for문, while문, do-while
 
 #if문 (분기문/비교문)
 
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

