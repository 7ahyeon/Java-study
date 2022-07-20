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

```java

class Person {
	String name; //이름
	String id; //주민등록번호
	int age; //나이
	public Person(String name, String id, int age) {
		super();
		this.name = name;
		this.id = id;
		this.age = age;
	}
	
	@Override
	public int hashCode() {
		System.out.println(">> hashCode() 실행");
		final int prime = 31;
		int result = 1;
		result = prime * result + ((id == null) ? 0 : id.hashCode());
		return result;
	}

	@Override
	public boolean equals(Object obj) {
		System.out.println(">> equals() 실행");
		if (this == obj)
			return true;
		if (obj == null)
			return false;
		if (getClass() != obj.getClass())
			return false;
		Person other = (Person) obj;
		if (id == null) {
			if (other.id != null)
				return false;
		} else if (!id.equals(other.id))
			return false;
		return true;
	}
	
	@Override
	public String toString() {
		return "person [name=" + name + ", id=" + id + ", age=" + age + "]";
	}
}

public class HashSet_equals {

	public static void main(String[] args) {
		
		Person p1 = new Person("자바1", "980116-1234567", 25);
		Person p2 = new Person("자바2", "980717-1234567", 25);
		Person p3 = new Person("자바3", "980116-1234567", 25);
		
		System.out.println("p1.hashCode() : " + p1.hashCode());
		System.out.println("p2.hashCode() : " + p2.hashCode());
		System.out.println("p3.hashCode() : " + p3.hashCode());

		System.out.println("---Set에 저장---");
		HashSet<Person> set = new HashSet<>();
		set.add(p1);
		System.out.println(">> 1번째 데이터 입력 후");
		set.add(p2);
		System.out.println(">> 2번째 데이터 입력 후");
		set.add(p3);
		System.out.println(">> 3번째 데이터 입력 후"); 
		
		System.out.println(set);
		
	}

}

```




