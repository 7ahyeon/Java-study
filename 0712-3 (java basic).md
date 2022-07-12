# 문자열 다루기 실습
**문자열 다루기**

- String str1 = "홍길동 이순신   이순신 Tom 홍길동";
- String str2 = "    TOM    을지문덕 김유신 연개소문";
1. 위의 문자열을 StringBuilder 변수 sb를 이용해서 하나의 문자열로 만들고,
2-1. sb의 문자열을 빈칸(" ")을 구분자로 잘라서(이름만 추출) 화면 출력(데이터확인)
- (String.split() 또는 StringTokenizer 클래스 사용)
- 예) 홍길동 이순신 이순신 Tom 홍길동 TOM...
2-2. 문자열을 저장할 수 있는 배열변수(names)에 저장
3. 배열에 있는 값을 구분자 콤마(,)로 구분하여 한라인에 출력(StringBuilder 사용)
- 예) 홍길동,이순신,이순신,Tom,홍길동,TOM...   
4. 데이터의 첫글자만 추출해서 콤마(,)로 구분하여 한라인에 출력(StringBuilder 사용)
- 예) 홍,이,이,T,홍,T,을... 
5. 배열의 문자열중 이름의 글자수가 4 이상인 값을 "인덱스번호:이름" 출력
- 예) 인덱스번호:을지문덕

```java

		 String str1 = "홍길동 이순신   이순신 Tom 홍길동";
		 String str2 = "    TOM    을지문덕 김유신 연개소문";
		 
//		 1. 위의 문자열을 StringBuilder 변수 sb를 이용해서 하나의 문자열로 만들고,
		 StringBuilder sb = new StringBuilder(str1);
		 sb.append(str2);
		 String sbString = sb.toString();
		 
		 print("split()");
		 
//		 2-2. 문자열을 저장할 수 있는 배열변수(names)에 저장
		 String[] names = sbString.split(" ");

//		 2-1. sb의 문자열을 빈칸(" ")을 구분자로 잘라서(이름만 추출) 화면 출력(데이터확인)
		 for (int i = 0; i < names.length; i++) {
			 System.out.print(names[i] + " ");
		 }

		
		
//		 3. 배열에 있는 값을 구분자 콤마(,)로 구분하여 한라인에 출력(StringBuilder 사용)
		
		 System.out.println();
		 print("");
		 
		 for (int i = 0; i < names.length; i++) {
			 if (i != 0 && names[i].length() != 0) {
			 System.out.print( ", " + names[i]);
			 
			 } else {
				 System.out.print(names[i]);
			 }
		 }
		 
//		 4. 데이터의 첫글자만 추출해서 콤마(,)로 구분하여 한라인에 출력(StringBuilder 사용)
		
		 System.out.println();
		 
		 
		 print("");
		if (names.length > 0) {
			System.out.print(names[0].charAt(0));
			for(int i = 1; i <names.length; i++) {
				if (names[i].length() >0 ) {
				System.out.print(", " + names[i].charAt(0));
				}
			}
		}

//		5. 배열의 문자열중 이름의 글자수가 4 이상인 값을 "인덱스번호:이름" 출력
		System.out.println();
		print("");
		for(int i = 0; i < names.length; i++) {
			String name = names[i];
			if (name.length() >= 4) {
				System.out.print(i + " : " + name + " ");
			}
		}
		
	}
  ```
