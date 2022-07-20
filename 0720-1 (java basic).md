# Vector

- List계열 : 순서 존재
- capacity() 기본 값 : 10

```java
// Vector 클래스 : List 계열

System.out.println("---Vector : List 계열---");
Vector<String> vector = new Vector<String>();
vector.add("1");
vector.add("2");
vector.add("3");

for (int i = 0; i < vector.size(); i++) {
  System.out.println(i + " : " + vector.get(i));
}

String temp = vector.toString();
System.out.println(temp); // 동일
System.out.println(vector); // 동일

System.out.println("vector.size() : " + vector.size());
System.out.println("vector.capacity() : " + vector.capacity());
System.out.println("---");

vector.remove(2);
System.out.println(vector); 
System.out.println("vector.size() : " + vector.size());
System.out.println("vector.capacity() : " + vector.capacity());

System.out.println("---vector.trimToSize()---");

vector.trimToSize();
System.out.println("vector.size() : " + vector.size());
System.out.println("vector.capacity() : " + vector.capacity()); // capacity=size

System.out.println("---");
vector.addElement("4문자열"); //맨 뒤에 추가
vector.add("5"); //맨 뒤에 추가
System.out.println(vector); 

System.out.println("---");
vector.add(2, "AAA"); //삽입 insert : 특정 위치에 입력
System.out.println(vector); 

System.out.println("---clone()---");
Vector<String> vector2 = (Vector) vector.clone();
System.out.println(vector); 
System.out.println(vector2); 

// 주소값 복사 vs 물리적 분리 복사본 확인

System.out.println("---물리적 분리 복사---");
vector.add("6");
System.out.println(vector); 
System.out.println(vector2); 
```
```java
System.out.println("---Enumeration 타입 사용---");
Enumeration<String> enu = vector.elements();
while (enu.hasMoreElements()) {
  System.out.println("enu.nextElement() : " + enu.nextElement());
}

System.out.println("---Iterator 사용 데이터 조회---");
Iterator<String> ite = vector.iterator();
while (ite.hasNext()) {
  System.out.println("ite.next() : " + ite.next());
}
System.out.println("---개선된 for문 사용 데이터 조회---");
		
for (String str : vector) {
  System.out.println(str);
}
```







