# TreeSet

```java
public class StudentVO implements Comparable<StudentVO>{

@Override
	public int compareTo(StudentVO o) {
		//return this.name.compareTo(o.name); //이름순 정렬(오름차순)
		//return this.tot - o.tot; //성적순 정렬(오름차순)
		return o.tot - this.tot; //성적순 정렬(내림차순)
	}
```
```java
//TreeSet으로 사용하려면 저장하는 데이터가 comparable이어야 함
TreeSet<StudentVO> set = new TreeSet<>();
```

# Map<K, V>

 **Map<K, V> 인터페이스**
 - 키(Key)-값(Value) 쌍으로 데이터 저장 관리
 - 순서가 없다.

- 키 key : 중복 X (중복값 없이 유일한 데이터)
- 값 Value : 중복 데이터 저장 가능

```java
HashMap<String, Integer> map = new HashMap<String, Integer>();
		
//입력

System.out.println("---입력 : put(key, value)---");
map.put("자바", 100);
map.put("파이썬", new Integer(95));
map.put("html", 88);
System.out.println(map);

//put() 리턴값 : 입력되는 key 중복X -> null
//key 중복 -> 기존 저장되어 있던 value값 리턴

System.out.println(map.put("css", 11)); //리턴값 null
System.out.println(map.put("자바", 16)); //리턴값 100
System.out.println(map);

System.out.println("---수정 : replace()---");

//map.put("자바2", 77); //없으면 입력, 있으면 수정
map.replace("자바2", 77); //없으면 입력 X, 있으면 수정
System.out.println("자바 점수 : " + map.get("자바"));
System.out.println(map);

System.out.println("---삭제 : remove()---");

System.out.println(">> map.remove(\"자바\") : " + map.remove("자바"));
System.out.println(">> map.remove(\"html\") : " + map.remove("html", 80));
System.out.println(map);
```



