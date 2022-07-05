# Java-study

**package 선언문**
- 자바 (class) 파일의 위치를 나타냄
- java 파일의 맨 첫 줄에 위치하며 한 번만 작성
- 일반적으로 회사의 도메인명을 반대로 사용하여 시작
- ex) com.naver.project, com.github.mystudy

```java
package edu.class1.basic;
```

**import 선언문**
- 여러개 선언 가능
- 선택 항목이지만 일반적으로 사용
- 대표문자(wild card) * 사용 가능
- java.lang 패키지 이외의 패키지에 있는 타입 사용시 사용
```java
import java.util.Scanner;
import java.util.*; 

```

**class 선언문** 
- 필수 항목
- 여러개 선언 가능 (public은 하나)
```java
public class Ex01_package_import_class {}
```

**변수 선언 영역**
1. 필드 변수 (인스턴스/멤버/전역 변수, 속성 property) 선언
```java
int num = 111;
```
2. 클래스 변수 (스태틱/인스턴스(객체)공통 변수)
```java
static int staticNum = 222;
```
**생성자 선언 영역**
기본 생성자 (default constructor) 
- 생략 가능
```java
Ex02_class(){}
```


**메소드(기능/동작) 선언 영역**
main method
```java
public static void main(String[] args){
  int num1 = 333;
  int num2 = 444;
  system.out.println("num1 : " + num1 + ", num2 : " + num2);
  
  int result = num1 + num2;
	System.out.println("result : " + result);
  }
```
- method 선언
- 전달 받은 데이터(값)(=parameter/파라미터) : int a, int b
```java
public static int add(int a, int b) {
		return a+b;
	}
```
- method 호출(부), 실행
- 전달하는 데이터(값)(=argument/인수) : num1, num2
```java
add(num1, num2);
```


