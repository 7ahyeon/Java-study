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
  

**제어문 control statement**
- 실행 흐름을 제어할 수 있게 해주는 것
 * 조건문 conditional statement : if문, switch문
 * 반복문 loop : for문, while문, do-while
 
 **if문 (분기문/비교문)**
 ```java
    int num1 = 20;
		int num2 = 10;
		
		if (num1 < num2) {
			System.out.println("num1이 num2보다 작다");
		}
		if (num1 >= num2) {
			System.out.println("num1이 num2보다 크거나 같다");
		}
		System.out.println(">>비교작업 끝");
 ```
 
 
 
 
