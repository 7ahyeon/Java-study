# Java-study

**출력 규칙**
```java
int num = 100;

System.out.println("num + 1 : " + num + 1); 
System.out.println("(num + 1) : " + (num + 1));
```
```java
num + 1 : 1001
(num + 1) : 101
```

**String.valueOf()**
- 숫자 타입 -> 문자열로 변환
```java
String snum = String.valueOf(100);
System.out.println("String.valueOf(100) : " + snum);
```
```java
String.valueOf(100) : 100
```

**Integer.parseInt()**
- 문자열 -> 숫자 타입 변환
```java
int num2 = Integer.parseInt("100");
System.out.println("Integer.parseInt(\"100\") : " + num2 );
```	
```java
Integer.parseInt("100") : 100
```
