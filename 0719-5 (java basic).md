# List중 ArrayList<String> 사용 실습

- 문자열 : "홍길동","이순신","이순신","을지문덕"
1. 위의 문자열 값을 저장할 수 있는 ArrayList 타입 names 변수를 선언하고 입력
2. List에 있는 값을 구분자 콤마(,)로 구분하여 한 라인에 출력
- 출력 예) 홍길동,이순신,이순신,을지문덕
3. List에 있는 데이터의 첫 글자만 출력-구분자 콤마(,) 사용 한 라인에 출력
- 출력 예) 홍,이,이,을
4. 이름이 을지문덕인 데이터를 찾아서 "인덱스번호:이름" 형태로 출력
- 예) 3:을지문덕
5. 이름이 이순신인 데이터를 찾아서 "인덱스번호:이름" 형태로 출력
- 예) 1:이순신 2:이순신

```java
//		1. 위의 문자열 값을 저장할 수 있는 ArrayList 타입 names 변수를 선언하고 입력
	
		ArrayList<String> names = new ArrayList<>();
		names.add("홍길동");
		names.add("이순신");
		names.add("이순신");
		names.add(new String("을지문덕"));
		
	
//		2. List에 있는 값을 구분자 콤마(,)로 구분하여 한 라인에 출력
	
		StringBuilder sb = new StringBuilder();
		if (names.size() > 0) {
			sb.append(names.get(0));
		} for (int i = 1; i < names.size(); i++) {
			sb.append(", ").append(names.get(i));
		}
		System.out.println(sb);
		
		sb.setLength(0);
								      
		for (String name : names) {
			sb.append(name).append(", ");
		}
		sb.deleteCharAt(sb.length()-2);
		System.out.println(sb.toString());
		
		sb.setLength(0);
		
//		3. List에 있는 데이터의 첫 글자만 출력-구분자 콤마(,) 사용 한 라인에 출력
		
		for (String name : names) {
			sb.append(name.charAt(0)).append(", ");
		}
		sb.deleteCharAt(sb.length()-2);
		System.out.println(sb.toString());
		
		sb.setLength(0);
								      
		if (names.size() > 0) {
			sb.append(names.get(0).charAt(0));
		} for (int i = 1; i < names.size(); i++) {
			sb.append(", ").append(names.get(i).charAt(0));
		}
		System.out.println(sb.toString());

		
//		4. 이름이 을지문덕인 데이터를 찾아서 "인덱스번호:이름" 형태로 출력
						   
		// == or contains 보다 equals가 정확하다.
		// names.add(new String("을지문덕"));의 경우 ==에서는 오류 발생
					
		for (int i = 0; i < names.size(); i++) {
			if (names.get(i).equals("을지문덕")) {
				System.out.println(i + " : " + names.get(i));
			} 
		}
	
		String nameData = "을지문덕";
		
		if (names.contains(nameData)) {
			int idx = names.indexOf(nameData);
			System.out.println(idx + " : " + names.get(idx) );
		}
	
//		for (int i = 0; i < names.size(); i++) {
//			if (names.get(i).contains("을지문덕")) {
//				System.out.println(i + " : " + names.get(i));
//			}
//		}
	
//		5. 이름이 이순신인 데이터를 찾아서 "인덱스번호:이름" 형태로 출력
						 
		for (int i = 0; i < names.size(); i++) {
			if (names.get(i).equals("이순신")) {
				System.out.println(i + " : " + names.get(i));
			} 
		}
//		for (int i = 0; i < names.size(); i++) {
//			if (names.get(i).contains("이순신")) {
//				System.out.println(i + " : " + names.get(i));
//			}
//		}
```
