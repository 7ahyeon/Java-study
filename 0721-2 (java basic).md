# TreeSet

```java
public class StudentVO implements Comparable<StudentVO>{

@Override
	public int compareTo(StudentVO o) { //Source -> Delegate Method
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

System.out.println("---조회 : get()---");
System.out.println("map.get(\"자바\")" + map.get("자바")); //없으면 null
System.out.println("map.get(\"파이썬\")" + map.get("파이썬")); //value : 95
System.out.println(map);
		
System.out.println("---전체 데이터 조회---");
System.out.println("---keySet() 사용---");
Set<String> KeySet = map.keySet();
System.out.println("map.keySet() : " + KeySet);

for (String key : KeySet) {
	System.out.println(key + " : " + map.get(key));
}

// iterator() 메서드 사용 : Iterator객체 사용 방식으로 전체 데이터 조회
System.out.println("---Iterator 사용---");
Iterator<String> ite2 = map.keySet().iterator();
while (ite2.hasNext()) {
	String key = ite2.next();
	System.out.println( key + " : " + map.get(key));
}

System.out.println("---values() 사용---");
Collection<Integer> values = map.values();
System.out.println("values : " + values);

for (Integer value : values) {
	System.out.println("점수 : " + values);
}

System.out.println("---점수 합계---");
int sum = 0;
for (Integer value : values) {
	sum += value;
}
System.out.println(">> 점수 합계 : " + sum);
System.out.println("map.size() : " + map.size());
```
```java
---입력 : put(key, value)---
{파이썬=95, html=88, 자바=100}
null
100
{css=11, 파이썬=95, html=88, 자바=16}
---수정 : replace()---
자바 점수 : 16
{css=11, 파이썬=95, html=88, 자바=16}
---삭제 : remove()---
>> map.remove("자바") : 16
>> map.remove("html") : false
{css=11, 파이썬=95, html=88}
---조회 : get()---
map.get("자바")null
map.get("파이썬")95
{css=11, 파이썬=95, html=88}
---전체 데이터 조회---
---keySet() 사용---
map.keySet() : [css, 파이썬, html]
css : 11
파이썬 : 95
html : 88
---Iterator 사용---
css : 11
파이썬 : 95
html : 88
---values() 사용---
values : [11, 95, 88]
점수 : [11, 95, 88]
점수 : [11, 95, 88]
점수 : [11, 95, 88]
---점수 합계---
>> 점수 합계 : 194
map.size() : 3

```
```java
System.out.println("---entrySet() : Map.Entry 타입---");
//Entry : Map.Entry<K,V>
Set<Entry<String, Integer>> entrySet = map.entrySet();
System.out.println("entrySet : " + entrySet);

Iterator<Entry<String, Integer>> ite = entrySet.iterator();
while (ite.hasNext()) {
	Entry<String, Integer> entry = ite.next();
	System.out.println("key : " + entry.getKey()
			+ ", value : " + entry.getValue());
```
```java
---entrySet() : Map.Entry 타입---
entrySet : [css=11, 파이썬=95, html=88]
key : css, value : 11
key : 파이썬, value : 95
key : html, value : 88
```
```java
//TreeMap : 키 key값 기준으로 정렬해서 데이터 저장
TreeMap<String, Integer> map = new TreeMap<String, Integer>();
```


