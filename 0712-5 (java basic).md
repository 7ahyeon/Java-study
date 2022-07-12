# 문자열 다루기 실습 해답 ver.2 SpringTokenizer
**문자열 다루기**

```java

		 String str1 = "홍길동 이순신   이순신 Tom 홍길동";
		 String str2 = "    TOM    을지문덕 김유신 연개소문";
//		 str1.concat(str2);
		 
		 StringBuilder sb = new StringBuilder();
		 sb.append(str1).append(str2);
		 
		 System.out.println(sb);
		 System.out.println("sb.toString() : " + sb.toString());
		 
		 print("StringTokenizer");
		 StringTokenizer stk = new StringTokenizer(sb.toString(), " ");
		 System.out.println("토큰의 개수 : " + stk.countTokens());
		 
		 while (stk.hasMoreTokens()) {
			 String name = stk.nextToken();
			 System.out.print(name + " ");
		 }
		 System.out.println();
		 System.out.println("사용 후 토큰 개수 : " + stk.countTokens());
		 
		 print("문제 2-2");
		 stk = new StringTokenizer(sb.toString(), " ");
		 String[] names = new String[stk.countTokens()]; // 토큰 개수로 배열 크기 지정
		 System.out.println("names : " + Arrays.toString(names));
		 System.out.println("토큰의 개수 : " + stk.countTokens());
		 System.out.println("배열 크기 : " + names.length);
		 
		 int idx = 0;
		 while (stk.hasMoreTokens()) {
			 names[idx++] = stk.nextToken();
//			 idx++;
		 }
		 System.out.println("names 배열 : " + Arrays.toString(names));
		 StringBuilder sbTemp = new StringBuilder();
		 
		 for (String name : names) {
//			 System.out.print(name + ", ");
		 sbTemp.append(name).append(",");
		 }
		 System.out.println("sbTemp : " + sbTemp.toString()); //쉼표 남음
		 
		 
		 // 첫번째 데이터 여부
		 
//		 sbTemp = new StringBuilder(); //새로운 객체(인스턴스) 생성해서 바꾸기
//		 sbTemp.delete(0, sbTemp.length()); // 기존 객체(인스턴스) 재사용 위한 초기화
		 sbTemp.setLength(0); // 기존 객체(인스턴스) 재사용 위한 초기화
		 boolean isFirst = true;
		 for (String name : names) {
			 if (isFirst) {
//				 System.out.print(name);
				 sbTemp.append(name);
				 isFirst = false; //두번째부터 실행X
			 } else {
//				 System.out.print(", " + name);
				 sbTemp.append(", ").append(name);
			 }
		 }
		 System.out.println("sbTemp : " + sbTemp);
		 System.out.println(">>>");
		 
		 sbTemp.setLength(0);
		 if (names.length > 0) {
			 sbTemp.append(names[0]);
		 }
		 for (int i = 1; i < names.length; i++) {
			 sbTemp.append(", ").append(names[i]);
		 }
		 System.out.println("sbTemp : " + sbTemp);
		 
		 System.out.println();
		 print("문제 4");
		 
//		 sbTemp.delete(0, sbTemp.length()); // 전체 데이터 삭제
		 sbTemp.setLength(0); // 전체 데이터 삭제
		 if (names.length > 0) {
			 sbTemp.append(names[0].charAt(0));
		 }
		 for (int i = 1; i < names.length; i++) {
			 sbTemp.append(", ").append(names[i].charAt(0));
		 }
		 System.out.println("sbTemp : " + sbTemp);
		 
		 System.out.println();
		 print("문제 5");
		 
		 sbTemp.setLength(0); // 전체 데이터 삭제
		
		 for (int i = 0; i < names.length; i++) {
			 if (names[i].length() >= 4) {
				 System.out.println(i + ": " + names[i]);
				 }
			 }		 
```
