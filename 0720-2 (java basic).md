# Linked_List

- List계열 : 순서 존재

```java
// LinkedList : List 계열
LinkedList<String> list = new LinkedList<String>();
list.add("자바"); //0번 인덱스
list.add("자바"); //1번 인덱스
list.add("파이썬"); //2번 인덱스
System.out.println("list : " + list );
System.out.println(list.get(2));

String str = "자바, 파이썬, html, 자바스크립트, 매트랩, 파이썬, 자바";
String[] names = str.split(", ");
System.out.println("names : " + Arrays.toString(names));

// 배열 데이터를 리스트에 넣기(추가)

for (int i = 0; i < names.length; i++) {
  list.add(names[i]);
}
System.out.println("list : " + list );
```

# 리스트에 있는 데이터 변경하기 실습
1. 파이썬 모두 삭제 (Delete)
2. 자바 -> 자바2 모두 수정 (Update)

```java
// 1. 파이썬 모두 삭제 (Delete)
StringBuilder sb = new StringBuilder();
for (int i = 0; i < list.size(); i++) {
  if (!list.get(i).equals("파이썬")) {
    sb.append(list.get(i));
  }
}
System.out.println(sb.toString());

// 2. 자바 -> 자바2 모두 수정 (Update)  
sb.setLength(0);

for (int i = 0; i < list.size(); i++) {
  if (list.get(i).equals("자바")) {
    sb.append("자바2");
  } else {
    sb.append(list.get(i));
  }
}
System.out.println(sb.toString());
 ```











