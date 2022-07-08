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
