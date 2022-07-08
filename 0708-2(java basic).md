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
- 비교대상1.equals(비교대상2)
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
- 비교대상1.equalsIgnoreCase(비교대상2)
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
- 시작말.concat(중간말).concat(끝말)
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

**" " 출력법**
- \"출력\"
```java
result = a.concat(b).concat(c).concat("!!");
System.out.println("a.concat(b).concat(c).concat(\"!!\") : " + result);
```		

**String method**
1. **charAt()**
- 문자열.chartAt(위치)
- 특정 위치의 문자 확인
```java
String str = "Java World";
char ch = str.charAt(0);
System.out.println("str.charAt(0) : " + ch);
```
```java
str.charAt(0) : J
```
```java
char[] ch2 = new char[4];
for (int i = 0; i < ch2.length; i++) {
	ch2[i] = str.charAt(i);
}
System.out.println("ch2 : " + Arrays.toString(ch2));
```
```java
ch2 : [J, a, v, a]
```

2. **compareTo()**
- "a".compareTo("b") : a - b
- 동일 위치 동일 문자열 무시
```java
System.out.println("A vs A : " + "A".compareTo("A")); // 0
System.out.println("A vs B : " + "A".compareTo("B")); // -1
System.out.println("B vs A : " + "B".compareTo("A")); // 1
```
```java
System.out.println("AA vs AB : " + "AA".compareTo("AB")); // -1
System.out.println("ABCA vs ABCB : " + "ABCA".compareTo("ABCB")); // -1
System.out.println("abcA vs abcB : " + "abcA".compareTo("abcB")); // -1
System.out.println("BA vs AB : " + "BA".compareTo("AB")); // -1
```

3. **copyValueOf()**
- copyValueOf(배열, 시작, 끝)
- 배열을 문자열로 만듦
```java
char[] ch3 = {'a', 'b', 'c', 'd'};
String str2 = String.copyValueOf(ch3);
System.out.println("String.copyValueOf(ch3) : " + str2); // abcd
```
```java
String str3 = String.copyValueOf(ch3, 0, 2);
System.out.println("String.copyValueOf(ch3, 0, 2) : " + str3); // ab
```		

4. **startsWith()/endsWith()**
- 배열.startsWith("시작하는 말")
- 배열.endsWith("끝내는 말")
```java
String str4 = "Java World";
		
System.out.println("str4.startsWith(\"Java\") : " + str4.startsWith("Java")); // true
System.out.println("str4.endsWith(\"Java\") : " + str4.endsWith("Java")); // false
```


















		







