# HashSet

- Set 인터페이스를 구현한 클래스(구현체)
- 순서가 없고 중복 데이터를 허용하지 않음 (동일 데이터는 하나만 저장) 
- Set에서 동일 데이터 여부 확인 : hashCode(), equals() 값 확인 
1. 해시코드 값 확인 : hashCode()
2. equals() 메서드 결과값이 일치하면 동일 데이터 처리


```java
	HashSet<String> set = new HashSet<String>();
		set.add("자바");
		set.add("파이썬");
		set.add("자바");
		set.add(new String("자바"));
		
		System.out.println(set);
		System.out.println("---");
		
		
		// 객체 비교시 같은 객체가 아니어도 hashCode()는 일치한다.
		
		System.out.println("자바" == "자바");
		System.out.println("자바" == new String("자바"));

		System.out.println("\"자바\".hashCode() : " + "자바".hashCode());
		System.out.println("\"자바\".hashCode() : " + "자바".hashCode());
		System.out.println("new String(\"자바\").hashCode() : " + new String("자바").hashCode());
		
		System.out.println("---");

		System.out.println("set.size() : " + set.size());
		System.out.println("set.contains(\"자바\") : " + set.contains("자바"));
		
		set.add("자바 스크립트");
		set.add("html");
		set.add("테스트");
		
		System.out.println(set); // 순서 X

		set.remove("테스트");
		System.out.println(set);
```
```java
[파이썬, 자바]
---
true
false
"자바".hashCode() : 1631876
"자바".hashCode() : 1631876
new String("자바").hashCode() : 1631876
---
set.size() : 2
set.contains("자바") : true
[파이썬, 자바 스크립트, html, 테스트, 자바]
[파이썬, 자바 스크립트, html, 자바]
```
```java
System.out.println("---파이썬 -> css (수정/변경) ---");
		/* 수정(변경) : 파이썬 -> css
		 파이썬 존재 여부 확인 이후 변경 (없을시 진행X)
		 */
		
		if (set.contains("파이썬")) {
			set.remove("파이썬");
			set.add("css");
		} else {
			System.out.println("파이썬이 존재하지 않습니다.");
		}
		
		System.out.println(set);
```
```java
--set 전체 데이터 조회---
파이썬
자바 스크립트
html
자바
---iterator() 사용 전체 데이터 조회---
파이썬
자바 스크립트
html
자바
---파이썬 -> css (수정/변경) ---
[css, 자바 스크립트, html, 자바]
```



