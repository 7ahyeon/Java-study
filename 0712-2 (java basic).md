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















