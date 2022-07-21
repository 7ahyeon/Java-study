**Collection**

- 객체들을 모아 놓은 것(객체를 모아서 관리)
- Collection<E> => List<E>(index / 순서 O / 데이터 중복 O), Set<E>( 순서X / 데이터 중복 X), Queue<E>, 
- key-value : Map<K,V>( key-value 쌍으로 저장 / 순서 X / 데이터(value) 중복 O / Key값 중복 X / Key - 번호 / value - 데이터 )

# 컬렉션 프레임워크  Collection Framework

**1. List 인터페이스 : Collection 인터페이스 확장(extends)**
- 순서가 있는 데이터의 집합 처리(index)
- 데이터의 중복 허용 : index가 다르면 저장된 값은 동일해도 관계없다
- 예) 출석리스트, 대기자 명단 등
- 구현클래스 : ArrayList, LinkedList, Stack, Vector 등

- ArrayList vs LinkedList 비교
	
|  |ArrayList|LinkedList|
|:---:|:---:|:---:|
|맨뒤에 추가|빠름|느림|
|중간CUD|느림|빠름|
|데이터조회|빠름|느림|
	
**2. Set 인터페이스 : Collection 인터페이스 확장(extends)**
- 순서를 유지하지 않는 데이터의 집합.
- 데이터의 중복을 허용하지 않음
- 예) 양의 정수 집합, 소수의 집합
- 구현클래스 : HashSet, TreeSet 등

**3. Map 인터페이스**
- 키(key)와 값(value)을 쌍으로 가지는 데이터의 집합(key-value, key:value)
- 순서는 유지되지 않으며, 키는 중복허용 안함, 값은 중복허용함
- 예) 우편번호, 지역번호(전화번호)
- 구현클래스 : HashMap, TreeMap, HashTable, Properties 등

- 클래스명 앞에 Tree가 붙은 클래스는 데이터를 저장할 때 오름차순 정렬하여 저장함
- TreeSet, TreeMap - 정렬되어 저장
  
**CRUD ; 데이터 제공시 기본 기능**
- Creat : 생성 / 입력 / 추가 
- Read : 읽기 / 조회 / 검색
- Update : 수정 / 변경
- Delete : 삭제
  
```java
// ArrayList : Array(배열)의 속성을 가진 List(목록)
		
//		ArrayList<Integer> list1 = new ArrayList<Integer>();
		ArrayList<Integer> list1 = new ArrayList<>();
		
		System.out.println("list1.size() : " + list1.size());
		
		// 입력(C) : 맨 뒤에 입력(추가)
		list1.add(new Integer(500)); // Integer 저장
		list1.add(100); // int -> Integer 자동 형변환되어 입력(추가)
		list1.add(500);
		list1.add(600);
		list1.add(700);
		System.out.println(list1.toString());
		
		// 입력(C) : 지정된 특정 위치에 입력(추가)
		list1.add(0, 777);
		System.out.println("0번 인덱스에 777 추가 후 : " + list1);
		
		
		// 수정(U) : 지정된 위치의 데이터 수정(변경)
		int returnValue = list1.set(0, 888);
		System.out.println("0번 인덱스에 888 set 후 : " + list1);
		System.out.println("리턴값 : " + returnValue);
		
		
		// 삭제(D) : 특정 위치 데이터 삭제
		returnValue = list1.remove(0); // 0번 인덱스 번호 데이터 삭제
		System.out.println("0번 인덱스 remove : " + list1);
		System.out.println("리턴값 : " + returnValue);
		
		
		// 조회, 선택, 읽기(R) : 특정 위치 데이터 읽기
		int firstData = list1.get(0); // 0qjs dlseprtm epdlxj
		System.out.println("list1.get(0) : " + firstData);
		System.out.println("list1.get(1) : " + list1.get(1));
		System.out.println("list1.get(2) : " + list1.get(2));
		
		// add, set, get, remove 사용시 접근할 수 없는 인덱스 사용시 예외 발생
		//List1.add(100,999); //IndexOutOfException
		//List1.set(100,999); //IndexOutOfException
//		list1.remove(100);
		
//		list1.remove(500); // 500번째 인덱스 데이터 삭제 시도
		boolean removeSuccess = list1.remove(new Integer(500));
		System.out.println("500  remove : " + list1);
		System.out.println("remove(obj) 리턴값 : " + removeSuccess);
		System.out.println("----------------------------------");
```  
```java
System.out.println("Collections.reverse(list1) 전 : " + list1);
	Collections.reverse(list1);
	System.out.println("Collections.reverse(list1) 후 : " + list1);

	System.out.println("------------------list2-----------------");

	List<Integer> subList = list1.subList(1, 4);
	System.out.println(subList);

	ArrayList<Integer> list2 = new ArrayList<>(list1.subList(1, 4));
	System.out.println("list2 : " + list2);

	System.out.println(">> Collections.sort()");
	Collections.sort(list2);
	System.out.println("Collections.sort(list2) 후 : " + list2);
```
```java
System.out.println("---반복문 사용 전체 데이터 조회---");
	System.out.println("list1 : " + list1);

	for(int i = 0; i < list1.size(); i++) {
		System.out.println(i  + " : " + list1.get(i));
	}

	System.out.println("---");

	for (Integer num : list1) {
		System.out.println(num);
	}

	System.out.println("---");

	int idx = 0;
	for (Integer num : list1) {
		System.out.println(idx++ + " : " + num);
	}
```
```java
System.out.println("list1.contains(700) : " + list1.contains(700));
```
