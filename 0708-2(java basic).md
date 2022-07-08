# String

**String class**
1. String str = "자바";
- 기본 데이터 타입처럼 사용
- 동일 객체 (true)
```java
String str1 = "Java";
String str11 = "Java";
System.out.println("str1 == str11 : " + (str1 == str11));
```

2. String str = new String("자바"); 
- 새로운 객체 생성 방식
- 다른 객체 (false)
```java
String str1 = "Java";
String strObj1 = new String("Java");
System.out.println("str1 == strObj1 : " + (str1 == strObj1));
```

**==**
- 동일한 객체 여부 확인
```java
System.out.println("str1 == str11 : " + (str1 == str11));
System.out.println("str1 == strObj1 : " + (str1 == strObj1));
```
```java
str1 == str11 : true
str1 == strObj1 : false
```

**equals()**
- 동일한 문자열 여부 확인
- 대소문자 구분 O
```java
System.out.println("str1.equals(str11) : " + str1.equals(str11));
System.out.println("str1.equals(strObj1) : " + str1.equals(strObj1));
```
```java
str1.equals(str11) : true
str1.equals(strObj1) : true
```

**equalsIgnoreCase()**
- 동일한 문자열 여부 확인
- 대소문자 구분 X
```java
String str1 = "Java";
String str12 = "JAVA";

System.out.println("str1.equals(str12) : " + str1.equals(str12));
System.out.println("str1.equalsIgnoreCase(str12) : " + str1.equalsIgnoreCase(str12));
```
```java
str1.equals(str12) : false
str1.equalsIgnoreCase(str12) : true
```

**concat()**
- chainning 기법
```java
String a = "Java ";
String b = "World";
String c = "~~~";
	
String result = a.concat(b);

System.out.println("a + b : " + (a + b));
System.out.println("a.concat(b) : " + result);
```
```java
a + b : Java World
a.concat(b) : Java World
```
```java
result = a.concat(b).concat(c);

System.out.println("a + b + c : " + (a + b + c));
System.out.println("a.concat(b).concat(c) : " + result);
```
```java
a + b + c : Java World~~~
a.concat(b).concat(c) : Java World~~~
```

**""출력법**
-\"출력\"
```java
result = a.concat(b).concat(c).concat("!!");
System.out.println("a.concat(b).concat(c).concat(\"!!\") : " + result);
```		






