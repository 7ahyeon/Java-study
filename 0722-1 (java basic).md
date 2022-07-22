# List Set Map

**실습**

```java
public static void main(String[] args) {
		//1. List 사용
		//이름등록 : 홍길동, 강감찬, 홍경래, 이순신
		//저장된 데이터를 조회해서 화면에 출력(index:데이터 / 이름오름차순)
		//---------------------------------
		
		System.out.println("---list 사용---");
		
		ArrayList<String> list = new ArrayList<String>();
		list.add("홍길동");
		list.add("강감찬");
		list.add("홍경래");
		list.add("이순신");
		
		Collections.sort(list);
		for (int i = 0; i < list.size(); i++) {
			System.out.println(i + " : " + list.get(i));
		}
		
		
		//2. Set 사용
		//이름등록 : 홍길동, 강감찬, 홍경래, 이순신
		//저장된 데이터를 조회해서 화면에 출력(오름차순으로 출력)
		//---------------------------------------

		System.out.println("---set 사용---");
		
		HashSet<String> set = new HashSet<>();
		set.add("홍길동");
		set.add("강감찬");
		set.add("홍경래");
		set.add("이순신");
		
		ArrayList<String> setList = new ArrayList<>(set);
		Collections.sort(setList);
		for (int i = 0; i < setList.size(); i++) {
			System.out.println(i + " : " + setList.get(i));
		}
		
	
		//3. Map 사용
		//k-v: 1111-홍길동, 2222-강감찬, 3333-홍경래, 4444-이순신
		//저장된 데이터를 조회해서 화면에 출력(key-value형태, key 기준 오름차순으로 출력)
		//----------------------------------------------

		System.out.println("---set 사용---");
		TreeMap<Integer, String> map = new TreeMap<>();
		map.put(1111, "홍길동");
		map.put(2222, "강감찬");
		map.put(3333, "홍경래");
		map.put(4444, "이순신");
		
		
		Set<Integer> key = map.keySet();
		for (Integer name : key) {
			System.out.println(name + " : " + map.get(name));
		}
```
