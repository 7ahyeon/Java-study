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
```java
System.out.println("str1.equals(str11) : " + str1.equals(str11));
System.out.println("str1.equals(strObj1) : " + str1.equals(strObj1));
```
```java
str1.equals(str11) : true
str1.equals(strObj1) : true
```

**equalsIgnoreCase()**
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











