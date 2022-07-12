# 문자열 다루기 실습 ver.2 SpringTokenizer
**문자열 다루기**

```java
String str1 = "홍길동 이순신   이순신 Tom 홍길동";
String str2 = "    TOM    을지문덕 김유신 연개소문";
		
StringBuilder sb = new StringBuilder(str1);
sb.append(str2);
String sbS = sb.toString();
		
print("StringTokenizer");
		
StringTokenizer sbToken = new StringTokenizer(sbS, " ");
		
int TokenCnt = sbToken.countTokens();
String[] names = new String[TokenCnt];
		
for (int i = 0; i < TokenCnt; i++ ) {
	String Token = sbToken.nextToken();
	System.out.print(Token + " ");
	names[i] = Token;
}

		
String comma = ", ";
		
System.out.println();
print("3");
for (int i = 0; i < names.length; i++) {
	if (i != 0) {
	System.out.print(comma + names[i]);
	} else {
		System.out.print(names[i]);
	}
}
		
System.out.println();
print("4");
for (int i = 0; i < names.length; i++) {
	if (i != 0) {
		System.out.print(comma + names[i].charAt(0));
	} else {
	System.out.print(names[i]);
	}
}
		
System.out.println();
print("5");
		
for (int i = 0; i < names.length; i++) {
	if (names[i].length() >= 4) {
		System.out.print(i + ": " + names[i] + " ");
	}
}
```
