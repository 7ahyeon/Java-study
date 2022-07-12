# Java-study

**Character class**
- char 타입의 Wrapper 클래스
```java
char ch = 'a'; //"a" : String
System.out.println(Character.isAlphabetic(ch)); //true
System.out.println(Character.isAlphabetic('한')); //true
		
System.out.println(Character.isDigit('0')); //true
		
System.out.println(Character.isLetter('0')); //false
System.out.println(Character.isLetter('A')); //true

System.out.println(Character.isUpperCase('A')); //true
System.out.println(Character.isLowerCase('a')); //true

System.out.println(Character.isWhitespace('a')); //false	
System.out.println(Character.isWhitespace(' ')); //true		
System.out.println(Character.isWhitespace('\t')); //true
```
```java
char[] chs = {'한', 'A', 'a', '0', '+', ' ', '\t'};
for (int i = 0; i < chs.length; i++) {
	System.out.print(chs[i] + ": ");
	if (Character.isDigit(chs[i])) {
		System.out.print("숫자 ");
	}
	if (Character.isWhitespace(chs[i])) {
		System.out.print("공백 (제어문자)");
	}
	if (Character.isUpperCase(chs[i])) {
		System.out.print("대문자 ");
	}
	if (Character.isLowerCase(chs[i])) {
		System.out.print("소문자 ");
	}
	if (Character.isLetter(chs[i])) {
		System.out.print("문자 ");
	}
	if (Character.isDefined(chs[i])) {
		System.out.print("유니코드 ");
	}
				
	System.out.println();
}
```
```java
한: 문자 유니코드 
A: 대문자 문자 유니코드 
a: 소문자 문자 유니코드 
0: 숫자 유니코드 
+: 유니코드 
 : 공백 (제어문자)유니코드 
	: 공백 (제어문자)유니코드 
```

**String 클래스 split vs StringTokenizer 클래스**

1. 문자열.Split("기본 구분자")
```java
print("String split() method");
String str = "사과,배,복숭아,,포도";
		
System.out.println("str : " + str);

String[] strSplit = str.split(",");
System.out.println("strSplit.length : " + strSplit.length);
		
print("str.split(\",\") 결과 데이터");
for (int i = 0; i < strSplit.length; i++) {
	System.out.println(i + " : -" + strSplit[i] + "-");
}

```
```java
-----String split() method-----
str : 사과,배,복숭아,,포도
strSplit.length : 5
-----str.split(",") 결과 데이터-----
0 : -사과-
1 : -배-
2 : -복숭아-
3 : --
4 : -포도-
```
```java
System.out.println();
print("개선된 for문으로");
for (String str2 : strSplit) {
	System.out.println(str2);
}
int idx = 0;
for (String str2 : strSplit) {
	System.out.println(idx++ + " : " + str2);
}
```
```java
-----개선된 for문으로-----
사과
배
복숭아

포도
----------
0 : 사과
1 : 배
2 : 복숭아
3 : 
4 : 포도
```














