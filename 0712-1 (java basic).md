# Java-study

**Integer.parseInt()**
- **원시 데이터**인 int 타입 반환

**Integer.valueOf()**
- **Wrapper 객체**인 Integer 반환

**String.valueOf()**
- String <- int
- 파라미터가 null일시 문자열 "null"로 반환 
```java
String str = String.valueOf(9999);
```

**Boolean**
- 대소문자 구분 없이 true 문자열만 true
- 그 외 문자열 모두 false

```java
boolean bool = true;
bool = new Boolean(true);
bool = new Boolean("true"); //true
bool = new Boolean("TRUE"); //true
bool = new Boolean("TRue"); /true
```
```java
bool = false;
bool = new Boolean("false");
bool = new Boolean("FALSE");
bool = new Boolean("FALse");
bool = new Boolean("true1"); //true가 아닌 문자열 -> false
bool = new Boolean("false2"); 
bool = new Boolean("asasdf"); //true/false가 아닌 문자열 -> false
```
```java
System.out.println("Boolean.TRUE : " + Boolean.TRUE);
System.out.println("Boolean.FALSE : " + Boolean.FALSE);
```		

**Boolean.valueOf()**
- Boolean <- String
```java
bool = Boolean.valueOf("true");
```

**Boolean.parseBoolean()**
- boolean <- String
```java
boolean bool2 = Boolean.parseBoolean("true");
```

**Float**
- Float.valueOf("String") Float <- String
```java
Float f = 10.5f; // Float <- float
f = new Float(12.5f); //Float <- float
f = new Float(12.5); //Float <- double
f = new Float("12.5f"); //Float <- String
f = new Float("12.5"); //Float <- String
 ```
```java
f = Float.valueOf("999.9f"); //float 타입 문자열
f = Float.valueOf("999.9F"); //float 타입 문자열
f = Float.valueOf("999.9d"); //double 타입 문자열
f = Float.valueOf("999.9D"); //double 타입 문자열
System.out.println("f : " + f);
```

**Double**
```java
Double d = 10.5D; // Double <- double
d = new Double (12.5d);
d = new Double ("15.8d");
System.out.println("Double d : " + d);
```
```java
String str2 = String.valueOf(d); //String <- Double
str2 = String.valueOf(12.5); //String <- Double
System.out.println("String str2 : " + str2);

//d = "12.5"; // Type mismatch : cannot convert from String to Double
d = Double.valueOf("12.5"); // Double <- String
d = Double.valueOf("12.5d"); // Double <- String
d = Double.valueOf("12.5f"); // Double <- String
System.out.println("Double d : " + d);
```
**Overloading**
- 하나의 클래스에서 같은 이름의 메소드를 여러개 가질 수 있음
- 같은 이름의 메소드를 여러개 정의하는 것
- 매개변수의 타입이 다르거나 개수가 달라야 한다.
- return type과 접근 제어자는 영향을 주지 않음.














