# 문자열 다루기 실습 ver.1 Split 해답
**문자열 다루기**
```java
String str1 = "홍길동 이순신   이순신 Tom 홍길동";
		 String str2 = "    TOM    을지문덕 김유신 연개소문";
		 
		 StringBuilder sb = new StringBuilder(str1);
		 sb.append(str2);
		 
		 print("String split() method");
		 String[] names = sb.toString().split(" ");
		 
		 System.out.println("names : " + Arrays.toString(names));
		 for (int i = 0; i < names.length; i++) {
			 System.out.print(names[i] + " ");
		 }

		 System.out.println();
		 print("");
		 
		 System.out.println(">>이름만 출력");
		 for (int i = 0; i < names.length; i++) {
//			 if (names[i].length() > 0) { // 빈 문자열 제외	 
//			 if (!names[i].equals("")) { // 빈 문자열 제외	 
			 if (!names[i].isEmpty()) { // 빈 문자열 제외
				 System.out.print(names[i] + " ");			 
			 }
		 }
```
```java
	 
		 /* 이름만 담긴 배열 만들기
		 1. 이름이 있는 데이터의 개수 확인
		 2. 배열 선언시 1번 개수 크기로 생성
		 3. names 데이터 중 이름 데이터만 새로운 배열에 저장
		 */
		 int num = 0;
		for (int i = 0; i < names.length; i++)
			if(names[i].length() > 0) {
				num++;
			}
		System.out.println(num);
		 StringBuilder names2 = new StringBuilder(num); 
		 for (int i = 0; i < names.length; i++)
				if(names[i].length() > 0) {
					names2.append(names[i]);
				}
		 System.out.println(names2);
```
