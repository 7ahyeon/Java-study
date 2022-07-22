# Scanner

**Scanner**
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

System.out.println("num1 : " + num1 + ", num2 : " + num2);
System.out.println("sum : " + (num1 + num2));
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
```


