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

