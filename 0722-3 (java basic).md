# Scanner

**Scanner**
- nextInt() / nextLine() 연속 사용시 줄바꿈 
1. nextInt() / nextLine() 사이에 scan.nextLine() 삽입
2. nextInt() 대신 int num = Integer.parseInt(scan.nextLine()) 사용

```java
//Scanner 사용 값 읽기
Scanner scan = new Scanner(System.in);

System.out.print("문자열 입력1 : ");
String str1 = scan.nextLine();
System.out.println(">> " + str1);

System.out.println("---");

System.out.print("문자열 입력2 : ");
String str2 = scan.nextLine();
System.out.println(">> " + str2);

System.out.println("---");

System.out.println("정수값 2개 입력 -> 덧셈 연산 결과 출력");
		
System.out.print("숫자 입력1 : ");
int num1 = scan.nextInt();

System.out.print("숫자 입력2 : ");
int num2 = scan.nextInt();
//scan.nextLine(); //줄바꿈
int num2 = Integer.parseInt(scan.nextLine()); //줄바꿈

System.out.println("num1 : " + num1 + ", num2 : " + num2);
System.out.println("sum : " + (num1 + num2));

System.out.println("---");
System.out.print("문자열 입력 : ");
String temp = scan.nextLine();
System.out.println(">> " + temp);
```
```java
문자열 입력1 : Hello
>> Hello
---
문자열 입력2 : _World
>> _World
---
정수값 2개 입력 -> 덧셈 연산 결과 출력
숫자 입력1 : 10
숫자 입력2 : 16
num1 : 10, num2 : 16
sum : 26
---
문자열 입력 : blue
>> blue
```

# Scanner 사용 성적 처리
- 입력 : 성명, 국어, 영어, 수학 점수
- 처리 : 총점, 평균 계산
- 출력 : 결과 화면 출력

|성명||
|:---:|:---:|
|국어|100|
|영어|90|
|수학|81|
|총점|271|
|평균|90.33|

```java
Scanner scan = new Scanner(System.in);

System.out.println("----------");
System.out.print("성명 : ");
String name = scan.nextLine();

System.out.print("국어 : ");
int kor = scan.nextInt();

System.out.print("영어 : ");
int eng = scan.nextInt();

System.out.print("수학 : ");
int math = scan.nextInt();

System.out.println("----------");

int tot = kor + eng + math;
double avg = tot * 100 / 3 / 100.0;
System.out.println("평균 : " + tot);
System.out.println("총점 : " + avg);
```
```java
----------
성명 : 자바
국어 : 100
영어 : 90
수학 : 81
----------
평균 : 271
총점 : 90.33
```













