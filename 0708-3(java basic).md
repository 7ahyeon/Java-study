# String method

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
- 문자열.startsWith("시작하는 말")
- 문자열.endsWith("끝내는 말")
```java
String str4 = "Java World";
		
System.out.println("str4.startsWith(\"Java\") : " + str4.startsWith("Java")); // true
System.out.println("str4.endsWith(\"Java\") : " + str4.endsWith("Java")); // false
```

5. **indexOf()**
- 문자열.indexOf('a')/배열.indexOf("a") : a의 index위치
- 같은 문자가 두개일시 가장 앞부터 찾음
- 문자열.indexOf('a', 시작 위치) : 시작 위치부터 찾음
- 존재하지 않을시 -1 / 문자열의 경우 가장 처음 문자의 위치 출력
```java
String str4 = "Java World";

System.out.println("str4.indexOf('J') : " + str4.indexOf('J')); // 0
System.out.println("str4.indexOf(\"a\") : " + str4.indexOf("a")); // 1
System.out.println("str4.indexOf(\"a\", 2) : " + str4.indexOf("a", 2)); // 3

System.out.println("str4.indexOf(\"M\") : " + str4.indexOf("M")); // -1
System.out.println("str4.indexOf(\"a\", 5) : " + str4.indexOf("a", 5)); // -1
System.out.println("str4.indexOf(\"World\") : " + str4.indexOf("World")); // 5
```	

6. **isEmpty()**
- 문자열.isEmpty() = ( 배열.length() == 0 )
```java
System.out.println("str4.isEmpty() : " + str4.isEmpty()); // false
System.out.println("\"\".isEmpty() : " + "".isEmpty()); // true

System.out.println("str4.length() : " + (str4.length() == 0));
```		

7. **replace()**
- 문자열.replace("수정 전 문자", "수정 후 문자")
- 문자열 자체 수정 X
```java
String result = str5.replace("a", "b");
System.out.println("str5.replace(\"a\", \"b\") : " + result);
System.out.println("str5 : " + str5 );
```
```java
str5.replace("a", "b") : Jbvb World
str5 : Java World
```

8. **replaceAll()**
- 문자열.replaceAll("수정 전 문자", "수정 후 문자")
- 문자열 내 해당 문자 전부 수정
```java
String str6 = "java java";
System.out.println("str6.replaceAll(\"ja\", \"JA\") : " + str6.replaceAll("ja", "JA"));
```
```java
str6 : java java
str6.replaceAll("ja", "JA") : JAva JAva
```

9. **substring(beginIndex)**
- 문자열.substring(시작 위치) / 배열.substring(시작 위치, 끝 위치)
- 시작 위치(beginIndex)부터 끝 위치 전(endIndex)까지 출력
- beginIndex : 시작 위치 값부터
- endIndex : 끝 위치 이전까지 (불포함)
```java
System.out.println("str.substring(5) : " + str.substring(5));
System.out.println("str.substring(0, str.length()) : " + str.substring(0, str.length()));

System.out.println("str.substring(0, str.length()-3) : " + str.substring(0, str.length()-3));
```
```java
str.substring(5) : World //5부터 끝까지
str.substring(0, str.length()) : Java World //처음부터 끝까지
str.substring(0, str.length()-3) : Java Wo // 뒤에서 3개 문자 제외
```

10. **toCharArray()**
- char[] 변수명 = 문자열.toCharArray()
- 문자열을 문자 배열로 변환
```java
char[] ch4 = str.toCharArray();
System.out.println("ch4 : " + ch4);
System.out.println(Arrays.toString(ch4));
```
```java
ch4 : [C@153f5a29
[J, a, v, a,  , W, o, r, l, d]
```

11. **toUpperCase() / toLowerCase()**
- 문자열.toUpperCase() : 대문자 변환
- 문자열.toLowerCase() : 소문자 변환
```java
System.out.println("str.toUpperCase() : " + str.toUpperCase());
System.out.println("str.toLowerCase() : " + str.toLowerCase());
```
```java
str.toUpperCase() : JAVA WORLD
str.toLowerCase() : java world
```

12. **trim()**
- 문자열.trim()
- 공백 제거
```java
str = "  Java World  ";
System.out.println("str : -" + str + "-");
System.out.println("str.trim() : -" + str.trim() + "-");
```
```java
str : -  Java World  -
str.trim() : -Java World-
```










